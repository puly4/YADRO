import discord
from discord.ext import commands

client = commands.bot(command_prefix = '.')

@client.event
async def on_ready():
  print('bot id ready.')
  
client.run('NjQ5OTY2MTQ3MzQwNDY4MjM2.XeNvhA.2hPF_IuJEsS9zUzhE0E7ISMuRSk
')
