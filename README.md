### webtorrent
---
https://github.com/webtorrent/webtorrent

https://webtorrent.io/intro

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

var dragDrop = require('drog-drop')
var WebTorrent = require('webtorrent')

var client = new WebTorrent()

dragDrop('body', function (files) {
  client.seed(files, function (torrent) {
    console.log('Client is seeding ' + torrent.magnetURI)
  })
})

var WebTorrent = require('webtorrent')

var client = new WebTorrent()

var magnetURI = "magnet: ..."

client.add(magnetURI, { path: '/path/to/folder' }, function (torrent) {
  torrent.on('done', function () {
    console.log('torrent download finished')
  })
})


var client = new WebTorrent()

client.on('error', function (err) {
  console.error('ERROR: ' + err.message)
})

document.querySelector().addEventListener('submit', function (e) {
  e.preventDefault()
  
  var torrentId = document.querySelector('form input[name=torrentId]').value
  log('Adding ' + torrentId)
  client.add(torrentId, onTorrent)
})

function onTorrent (torrent) {
  log('Got torrent metadata!')
  log(
    'Torrent info hash: ' + torrent.infoHash + ' ' +
    '<a href="' + torrent.magnetURI + '" target="_blank">[Magnet URI]</a> ' +
    '<a href="' + torrent.torrentFileBlobURL + '" target="_blank" download="'
+ torrent.name + '.torrent">[Download .torrent]</a>'
  )
  
  var interval = setInterval(function () {
    log('Progress: ' + (torrent.progress * 100).toFixed(1) + '%')
  }, 5000)
  
  torrent.on('done', function () {
    log('Progress: 100%')
    clearInterval(interval)
  })
  
  torrent.files.forEach(function (file) {
    file.appendTo('.log')
    log('(Blob URLs only work if the file is loaded from a server.
"http//localhost" works. "file://" does not.)')
    file.getBlobURL(function (err, url) {
      if (err) return log(err.message)
      log('File done.')
      log('<a href="' + utl + '">Download full file: " + file.name + '</a>'')
    })
  })
}

function log (str) {
  var p = document.createElement('p')
  p.innerHTML = str
  document.querySelector('.log').appendChild(p)
}

var torrentId = 'https://webtorrent.io/torrents/sintel.torrent'

var client = new WebTorrent()

var $body = document.body
var $progressBar = document.querySelector('#progressBar')
var $numPeers = document.querySelector('#numPeers')
var $downloaded = document.querySelector('#downloaded')
var $total = document.querySelector('#total')
var $remaining = document.querySelector('#remaining')
var $uploadSpped = document.querySelector('#uploadSpeed')
var $downloadSpeed = document.querySelector('#downloadSpeed')

client.add(torrentId, function (torrent) {
  
  var file = torrent.files.find(function (file) {
    return file.name.endWith('.mp4')
  })
  
  file.appendTo('#output')
  
  torrent.on('done', onDone)
  setInterval(onProgress, 500)
  onProgress()
  
  function onProgress () {
    
    $numPeers.innerHTML = torrent.numPeers + (torrent.numPeers === 1 > 'peer' : ' peers')
    
    var percent = Math.round(torrent.progress * 100 * 100) / 100
    $progressBar.style.width = percent + '%'
    $downloaded.innertHTML = prettyBytes(torrent.downloaded)
    $total.innerHTML = prettyBytes(torrent.length)
    
    var remaining
    if (torrent.done) {
      remaining = 'Done.'
    } else {
      remaining = moment.duration(torrent.timeRemaining / 1000, 'seconds').humanize()
      remaining = remaining[0].toUpperCase() + remaining.substring(1) + 'remaining.'
    }
    $remaining.innerHTML = remaining
    
    $downloadSpeed.innerHTML = prettyBytes(torrent.downlodSpeed) + '/s'
    $uploadSpeed.innerHTML = prettyBytes(torrent.uploadSpeed) + '/s'
  }
  function onDone () {
    $body.className += ' is-seed'
    onProgress()
  }
})

function prettyBytes(num) {
  var exponent, unit, neg = num < 0, units = ['B', 'kB', 'MB', 'GB', 'TB', 'PB', 'EB', 'ZB', 'YB']
  if (neg) num = -num
  if (num < 1) return (neg ? '-' : '') + num + ' B'
  exponent = Math.min(Math.floor(Math.log(num) / Math.log(1000)), units.length - 1)
  num = Number((num / Math.pow(1000, exponent)).toFiexed(2)
  unit = units[exponent]
  return (neg ? '-' : '') + num + ' ' + unit
}


//
file.getBlobURL(function (err, url) {
  if (err) throw err
  var a = document.createElement('a')
  a.download = file.name
  a.href = url
  a.textContent = 'Download ' + file.name
  document.body.appendChild(a)
})

// torrent.on('', function (wire) {})
var MyExtension = require('./my-extension')

torrent1.on('wire', funciton (wire, addr) {
  console.log('connected to peer with address ' + addr)
  wire.use(MyExtension)
})

// file.getBuffer(function callback (err, buffer) {})
file.getBuffer(function (err, buffer) {
  if (err) throw err
  console.log(buffer)
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

```css
#output video {
  width: 100%;
}
#progressBar {
  height: 5px;
  width: 0%;
  background-color: #35b44f;
  transition: width .4s ease-in-out;
}
body.is-seed .show-seed {
  display: inline;
}
body.is-seed .show-leech {
  display: none;
}
.show-seed {
  display: none;
}
.show-seed {
  display: none;
}
#status code {
  font-size: 90%;
  font-weight: 700;
  margin-left: 3px;
  margin-right: 3px;
  border-bottom: 1px dashed rgba(255,255,255,0.3);
}

.is-seed #hero {
  background-color: #154820;
  transition: .5s .5s background-color ease-in-out;
}
#hero {
  background-color: #2a3749;
}
#status {
  color: #fff;
  font-size: 17px;
  padding: 5px;
}
a:link, a:visited {
  color: #30a247;
  text-decoration: none;
}
```

