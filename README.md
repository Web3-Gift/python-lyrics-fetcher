# python-lyrics-fetcher
一个简单的Python程序，用于根据用户输入的歌曲名称获取歌词。该代码库使用 Lyrics.ovh API 发送请求并处理响应，帮助用户方便地获取所需歌曲的歌词。这个代码库适用于音乐爱好者、开发人员和学习者，可以作为学习如何使用API和处理HTTP请求的示例。
import requests

def get_lyrics(song_name):
    base_url = "https://api.lyrics.ovh/v1/"
    url = base_url + song_name
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        lyrics = data.get("lyrics", "Lyrics not found.")
        return lyrics
    else:
        return "Error: Failed to fetch lyrics."

song_name = input("请输入歌曲名称：")
lyrics = get_lyrics(song_name)
print(lyrics)
