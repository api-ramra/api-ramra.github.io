## Welcome To My Rest Api Example Pages

Website ini saya buat untuk contoh fitur dari [Rest Api Rara](https://ramra.herokuapp.com)

Disini saya hanya akan membuat contoh script dari javascript saja.

### List Api

Dibawah ini adalah list ďari rest api website saya

Media Api | Url Api
------------ | -----------
Youtube Downloader Mp3 | [Get Api](https://ramra.herokuapp.com/api/yutub/audio?url=https://youtu.be/xYJzwcZWJ0I)
Youtube Downloader Mp4 | [Get Api](https://ramra.herokuapp.com/api/yutub/video?url=https://youtu.be/xYJzwcZWJ0I)
Youtube Search | [Get Api](https://ramra.herokuapp.com/api/yutub/search?video=hanbunko%20hanabi%20kotori%20remix)
Pinterest Search | [Get Api](https://ramra.herokuapp.com/api/pinterest/search?search=loli)
Facebook Downloader | [Get Api](https://ramra.herokuapp.com/api/facebook/downloader?url=https://www.facebook.com/197394889304/posts/10160272795609305/?app=fbl)
Instagram Stalk | [Get Api](https://ramra.herokuapp.com/api/instagram/stalk?username=jessicajane99)

* EXAMPLE CASE MEDIA API

#### Youtube Downloader Mp3
```javascript
case 'ytmp3':
if (args.length == 0) return reply(`Example: ${prefix + command} https://youtu.be/xYJzwcZWJ0I`)
ini_link = args[0]
get_result = await fetchJson(`https://ramra.herokuapp.com/api/yutub/audio?url=${ini_link}`)
ini_result = get_result.result
ini_txt = `❏ *Title :* ${ini_result.title}\n`
ini_txt += `❏ *Zise :* ${ini_result.filesize}\n`
ini_txt += `❏ *Type :* ${ini_result.ext}\n`
ini_buffer = await getBuffer(ini_result.thumb)
client.sendMessage(from, ini_buffer, image,{quoted: mek, caption: ini_txt})
ini_audio = await getBuffer(ini_result.result)
await client.sendMessage(from, ini_audio, audio,{mimetype: 'video/mp4', filename: `${ini_result.title}.mp4`, quoted: mek })
break
```

#### Youtube Downloader Mp4
```javascript
case 'ytmp4' :
if (args.length == 0) return reply(`Example: ${prefix + command} https://youtu.be/xYJzwcZWJ0I`)
ini_link = args[0]
get_result = await fetchJson(`https://ramra.herokuapp.com/api/yutub/video?url=${ini_link}&apikey=${apikeyrara}`)
ini_result = get_result.result
ini_txt = `❏ *Title :* ${ini_result.title}\n`
ini_txt += `❏ *Zise :* ${ini_result.filesize}\n`
ini_txt += `❏ *Type :* ${ini_result.ext}\n`
ini_txt += `❏ *Resolution :* ${ini_result.resolution}\n\n`
ini_buffer = await getBuffer(ini_result.thumb)
client.sendMessage(from, ini_buffer, image,{quoted: mek, caption: ini_txt})
ini_video = await getBuffer(ini_result.result)
await client.sendMessage(from, ini_video, video, { mimetype: 'video/mp4', filename: `${ini_result.title}.mp4`, quoted: mek})
break
```

#### Youtube Search
```javascript
case 'ytsearch' :
if (args.length == 0) return reply(`Example: ${prefix + command} hanbunko hanabi kotori remix`)
query = args.join(" ")
ini_result = await fetchJson(`https://ramra.herokuapp.com/api/yutub/search?video=${query}`)
get_result = ini_result.result
ini_txt = " "
for (var x of get_result) {
    ini_txt += `❏ *Title :* ${x.title}\n`
    ini_txt += `❏ *Id :* ${x.id}\n`
    ini_txt += `❏ *Channel :* ${x.channel.name}\n`
    ini_txt += `❏ *Upload :* ${x.uploadDate}\n`
    ini_txt += `❏ *Thumbnail :* ${x.thumbnail}\n`
    ini_txt += `❏ *Views :* ${x.viewCount}\n`
    ini_txt += `❏ *Link :* https://www.youtube.com/watch?v=${x.id}\n`
    ini_txt += `\n*-------------------*\n`
}
client.sendMessage(from, ini_txt, text,{quoted: mek})
break
```

#### Instagram Stalk
```javascript
case 'igstalk' :
if (args.length == 0) return reply(`Example: ${prefix + command} jessicajane99`)
username = args[0]
inii_result = await fetchJson(`https://ramra.herokuapp.com/api/instagram/stalk?username=${username}`)
ini_result = inii_result.result
ini_buffer = await getBuffer(ini_result.Profile_pic)
ini_txt += `*Username :* ${ini_result.Username}\n`
ini_txt += `*Full Name :* ${ini_result.Name}\n`
ini_txt += `*Posts :* ${ini_result.Jumlah_Post}\n`
ini_txt += `*Followers :* ${ini_result.Jumlah_Followers}\n`
ini_txt += `*Following :* ${ini_result.Jumlah_Following}\n`
ini_txt += `*Bio :* ${ini_result.Biodata}`
client.sendMessage(from, ini_buffer, image,{quoted: mek, caption: ini_txt})
break
```

#### Pinterest Search
```javascript
case 'pinterest':
if (args.length == 0) return reply(`Example: ${prefix + command} Loli`)
query = args.join(" ")
get_result = await fetchJson(`https://ramra.herokuapp.com/api/pinterest/search?search=${query}`)
get_buffer = get_result.result
ini_buffer = await getBuffer(get_buffer)
client.sendMessage(from, ini_buffer, image,{quoted: mek})
break      
```

#### Facebook Downloader
```javascript
case 'fbdl' :
if (args.length == 0) return reply(`Example: ${prefix + command} https://www.facebook.com/197394889304/posts/10160272795609305/?app=fbl`)
ini_url = args[0]
ini_url = await fetchJson(`https://ramra.herokuapp.com/api/fbdown/?url=${ini_url}`)
ini_url = ini_url.result.url
ini_buffer = await getBuffer(ini_url)
await client.sendMessage(from, ini_buffer, video,{quoted: mek})
break
```

### Notice

Saya buat pages ini hanya untuk pemula, dan bagi yang sudah profesional/mastah kalo cuma buat ngehina mending diem aja ok (sungkem mastah)

### Thanks To

Allah SWT

My Perents

All My Friends

All Creator Bot

All Developed Rest Api
