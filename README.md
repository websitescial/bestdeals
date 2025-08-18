import csv
import asyncio
from telethon.sync import TelegramClient
from telethon.tl.functions.channels import GetParticipantsRequest
from telethon.tl.types import ChannelParticipantsSearch
from telegram import Update
from telegram.ext import Application, CommandHandler, ContextTypes

# --- TELEGRAM API (User Account for scraping) ---
api_id = 123456     # from my.telegram.org
api_hash = "your_api_hash"
phone = "+1234567890"  # your Telegram number
session_name = "scraper_session"

# --- BOT TOKEN (from @BotFather) ---
BOT_TOKEN = "your_bot_token"

# Telethon client
client = TelegramClient(session_name, api_id, api_hash)

async def scrape_members(channel_username: str):
    """Scrape members from channel/group"""
    await client.start(phone)
    channel = await client.get_entity(channel_username)

    offset = 0
    limit = 100
    all_participants = []

    while True:
        participants = await client(GetParticipantsRequest(
            channel,
            ChannelParticipantsSearch(''),
            offset,
            limit,
            hash=0
        ))
        if not participants.users:
            break
        all_participants.extend(participants.users)
        offset += len(participants.users)

    # Save to CSV
    file_name = f"{channel_username.strip('@')}_members.csv"
    with open(file_name, "w", encoding="utf-8", newline='') as f:
        writer = csv.writer(f)
        writer.writerow(["ID", "Username"])
        for user in all_participants:
            writer.writerow([user.id, user.username or ""])

    return file_name, len(all_participants)

# --- BOT HANDLER ---
async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("👋 Send /scrape <channel_username> to fetch member IDs.")

async def scrape(update: Update, context: ContextTypes.DEFAULT_TYPE):
    if len(context.args) == 0:
        await update.message.reply_text("❌ Usage: /scrape <channel_username>")
        return

    channel_username = context.args[0]
    await update.message.reply_text(f"⏳ Scraping members from {channel_username}...")

    file_name, count = await scrape_members(channel_username)

    await update.message.reply_document(document=open(file_name, "rb"),
                                        filename=file_name,
                                        caption=f"✅ Scraped {count} members from {channel_username}")

# --- MAIN BOT ---
def main():
    app = Application.builder().token(BOT_TOKEN).build()

    app.add_handler(CommandHandler("start", start))
    app.add_handler(CommandHandler("scrape", scrape))

    print("🤖 Bot is running...")
    app.run_polling()

if __name__ == "__main__":
    asyncio.run(main())
