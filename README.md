## Welcome To My Rest Api Example Pages

Website ini saya buat untuk contoh fitur dari [Rest Api Rara](https://ramra.herokuapp.com)

Disini saya hanya akan membuat contoh script dari javascript saja.

### List Api

Dibawah ini adalah list ďari rest api website saya

Media Api | Url Api
------------ | -----------
Youtube Downloader Mp3 | [Get Api](https://ramra.herokuapp.com/api/yutub/audio?url=https://youtu.be/xYJzwcZWJ0I)
Youtube Downloader Mp4 | [Get Api](https://ramra.herokuapp.com/api/yutub/video?url=https://youtu.be/xYJzwcZWJ0I)
Pinterest Search | [Get Api](https://ramra.herokuapp.com/api/pinterest/search?search=loli)

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
await client.sendMessage(from, ini_audio, audio,{mimetype: 'video/mp4', filename: `${get_result.title}.mp4`, quoted: raa })
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

### Notice

Saya buat pages ini hanya untuk pemula, dan bagi yang sudah profesional/mastah kalo cuma buat ngehina mending diem aja ok (sungkem mastah)

### Thanks To

Allah SWT

My Perents

All My Friends

All Creator Bot

All Developed Rest Api
