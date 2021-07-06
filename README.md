import discord
from discord.ext import commands

bot=commands.Bot(command_prefix='?')

@bot.event
async def on_ready():
   print(">>Bot is online<<")

@bot.event
async def on_member_join(member):
   channel=bot.get_chanel(861737106018402314)
   await channel.send(f'{member} join!')

@bot.event
async def on_member_remove(member):
   channel=bot.get_chanel(861737162903126036)
   await channel.send(f'{member} leave!')

@bot.command()
async def ping(ctx): 
   await ctx.send(f'{round(bot.latency*1000)} (ms)')

bot.run('ODYxNzEzMjcxNjAxNjI3MTU2.YONzBQ.iu3IN9g99vf3vMlyTUkcZsLn2MI')