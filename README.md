# telegram_member_scraper.py
from telethon.sync import TelegramClient
from telethon.tl.functions.channels import GetParticipantsRequest
from telethon.tl.types import ChannelParticipantsSearch

import csv

# Replace with your API credentials from https://my.telegram.org
api_id = 123456
api_hash = 'your_api_hash'
phone = '+1234567890'  # Your Telegram number

client = TelegramClient('session_name', api_id, api_hash)

async def main():
    await client.start(phone)
    
    # Ask user for channel/group username or ID
    target = input("Enter channel/group username (with @) or ID: ")
    channel = await client.get_entity(target)

    # Get all participants
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
    with open("members.csv", "w", encoding="utf-8", newline='') as f:
        writer = csv.writer(f)
        writer.writerow(["ID", "Username", "First Name", "Last Name", "Phone"])
        for user in all_participants:
            writer.writerow([
                user.id,
                user.username or "",
                user.first_name or "",
                user.last_name or "",
                user.phone or ""
            ])

    print(f"✅ Saved {len(all_participants)} members to members.csv")

with client:
    client.loop.run_until_complete(main())
