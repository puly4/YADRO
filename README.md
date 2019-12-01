# YADRO

import discord
from discord.ext import commands

client = commands.bot(command_prefix = '.')

@client.event
async def on_ready():
  print('bot id ready.')
  
client.run('NjQ5OTY2MTQ3MzQwNDY4MjM2.XeNsxQ.Nard7QPoj1-kKpTlKy_GxPY5t7M')
