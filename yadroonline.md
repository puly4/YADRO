import discord
from discord.ext import commands
import numpy as np

TOKEN ='NjQ5OTY2MTQ3MzQwNDY4MjM2.XePs8g.tEmdXXxqobh3FhrQ8L_nAl7M9ws'

client= commands.Bot(command_prefix ='.')

@client.event
async def on_ready():
    print('Bot is ready :D ')

#name=['art1','art2','art3','art4','art5','art6','art7','art8','art9','art10']
name=['เบส','สอง','พูม','หมอ','อารี','เหี้ยทัก','เฉา','น้ำพุ','จ่า',' ยาโดร']
word=['1 Top','2  Mid','3  Jungle', '4  ADC' , '5  Support']
word2=[' (Top)',' (Mid)',' (Jungle)', ' (ADC)' , ' (Support)']

@client.event
async def on_message(message):
    if message.author == client.user:
        return

    if message.content.startswith('$hello'):
        await message.channel.send('Hello!')

    if message.content.startswith('!team1'):
        np.random.shuffle(name)
        a= (' Team A | ')
        b= (' Team B  | ')
        r=  (' Role       | ')
        c= ' | '
        for i in range(5):
            a= a+ str(i+1)+name[i]+c
            r= r+word[i]+c
        for i in range(5,10):
            b=b+ str(i-4)+name[i]+c

        await message.channel.send(r)
        await message.channel.send(a)
        await message.channel.send(b)

    if message.content.startswith('!team2'):
        np.random.shuffle(name)

        a= (' Team A | ')
        b= (' Team B  | ')
        c= ' | '
        np.random.shuffle(word2)
        for i in range(5):
            a= a+name[i]+word2[i] +c

        np.random.shuffle(word2)
        for i in range(5,10):
            b=b+name[i]+ word2[i-5]+c

        await message.channel.send(a)
        await message.channel.send(b)

client.run(TOKEN)
