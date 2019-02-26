### webtorrent
---
https://github.com/webtorrent/webtorrent

```
npm install webtorrent
npm install webtorrent-cli -g

npm install webtorrent-cli -g
webtorrent --help

webtorrent magnet_uri
webtorrent magnet_uri --airplay

DEBUG=* webtorrent
localStorage.debug = '*'
localStorage.removeItem('debug')
```

```js
var WebTorrent = require('webtorrent')

var client = new WebTorrent()
var magnetURI = '...'

client.add(magnetURI, function (torrent) {
  
  console.log('Client is downloading', torrent.infoHash)
  
  torrent.files.forEach(function (file) {
    
    file.appendTo('body')
  })
})


var dragDrop = require('drag-drop')
var WebTorrent = require('webtorrent')

var client = new WebTorrent()

dragDrop('body', function (files) {
  client.seed(files, function (torrent) {
    console.log('Client is seeding:', torrent.infoHash)
  })
})

var WebTorrent = require('webtorrent')

var client = new WebTorrent()

var torrentId = ;magnet:?
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'

client.add(torrentId, function (torrent) {
  
  var file = torrent.files.find(function (file) {
    return file.name.endWith('.mp4')
  })
  
  file.appendTo('body')
})
```

```
{
  target: 'web',
  node: {
    fs: 'empty'
  }
}

{
  module: {
    loaders: [
      
      {
        test: /\.json$/,
        loader: 'json'
      }
    ]
  }
}
```


