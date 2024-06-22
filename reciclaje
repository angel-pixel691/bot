import discord
from discord.ext import commands
import os, random
import requests

intents = discord.Intents.default()
intents.message_content = True
print(os.listdir('m2l1\imagenes'))
bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'Ha iniciado sesión como {bot.user}')

def get_duck_image_url():    
    url = 'https://random-d.uk/api/random'
    res = requests.get(url)
    data = res.json()
    return data['url']

@bot.command('duck')
async def duck(ctx):
    image_url = get_duck_image_url()
    await ctx.send(image_url)

@bot.command()
async def mem(ctx):
    img_name = random.choice(os.listdir('m2l1\imagenes'))
    with open(f'm2l1\imagenes/{img_name}', 'rb') as f:
        picture = discord.File(f)
 
    await ctx.send(file=picture)

@bot.command()
async def importante(ctx):
    video_url = "https://youtu.be/mCdA4bJAGGk?si=3PW2b5oCzjsKnskK"
    await ctx.send(video_url)

@bot.command()
async def recicla(ctx):
    video_url = "https://www.youtube.com/shorts/lPYyg73Q-1g"
    await ctx.send(video_url)


bot.run("")
