## Welcome To My Rest Api Example Pages

Website ini saya buat untuk contoh fitur dari [Rest Api Rara](https://ramra.herokuapp.com)

Disini saya hanya akan membuat contoh script dari javascript saja.

### List Api

Dibawah ini adalah list ďari rest api website saya

Media Api | Url Api
------------ | -----------
Pinterest Search | [Get](https://ramra.herokuapp.com/api/pinterest/search?search=loli)

* EXAMPLE CASE MEDIA API

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
