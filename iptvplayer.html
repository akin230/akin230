<!doctypehtml><html lang=en><meta charset=UTF-8><meta content="width=device-width,initial-scale=1"name=viewport><meta content=no-referrer name=referrer><link href=data:image/x-icon;, rel=icon><title>github.com/dbghelp</title><link href=https://cdnjs.cloudflare.com/ajax/libs/shaka-player/4.11.2/controls.min.css rel=stylesheet><link href=https://dbghelp.github.io/xml-epg.css rel=stylesheet>

<style>
                 {
    margin: 0;
    padding: 0;
    background: black;
    height: 100%;
    overflow: hidden;
  }
  video {
    width: 100%;
    height: 40%;
    object-fit: cover; /* ครอบคลุมเต็มจอ */
  }
  
         #videoContainer {
            position: relative;
            width: 100%;
            max-width: 800px;
            margin: auto;
            background: black;
        }
        
        video {
            width: 100%;
            height: auto;
            display: flex;
        }

        .controls {
            display: flex;
            justify-content: space-between;
            padding: 10px;
            background: rgba(0, 0, 0, 0.7);
            color: white;
        }

        .button {
            cursor: pointer;
            padding: 5px 10px;
            border: none;
            background: #444;
            color: red;
            border-radius: 5px;
        }

        .button:hover {
            background: #555;
        }
  
      body {
          margin:0;font-family:Arial,sans-serif;display:flex;height:100vh;background-color:#282c34}#playlist{width:350px;background-color:#282c34;color:#fff;overflow-y:auto;border-right:1px solid #444;padding:20px;box-shadow:2px 0 5px rgb(0 0 0 / .2);display:flex;flex-direction:column}#search-input,#url-input{width:100%;padding:10px;margin-bottom:10px;border:1px solid #444;border-radius:5px;background-color:#3c4043;color:#fff;font-size:1em;box-sizing:border-box}#epg-button{display:none;width:100%;padding:10px;margin-bottom:10px;background-color:#61dafb;color:#000;border:none;border-radius:5px;font-size:1em;cursor:pointer;box-shadow:0 4px 8px rgb(0 0 0 / .3)}#fetch-button{width:100%;padding:10px;margin-bottom:10px;background-color:#61dafb;color:#000;border:none;border-radius:5px;font-size:1em;cursor:pointer;box-shadow:0 4px 8px rgb(0 0 0 / .3)}#fetch-button:hover{background-color:#4fa3c4}#epg-button:hover{background-color:#4fa3c4}
          
          #videoContainer{flex:1;display:flex;flex-direction:column;z-index:2}
          
          #video{flex:1;width:680px;height:260px;background-color:#000}
          
          #video-list{list-style:none;padding:0;margin:0}
          
          #video-list li{padding:10px;margin:5px 0;border-radius:5px;cursor:pointer;transition:background-color .3s ease,transform .2s ease;display:flex;align-items:center}
          
          #video-list li:hover{background-color:#61dafb;transform:scale(1.05)}
          
          #video-list img{width:500px;height:50px;margin-right:10px;border-radius:5px;object-fit:cover;object-fit:contain}.video-title{font-size:1em}.active{background-color:#4fa3c4}#overlay{display:none;flex-direction:column;align-items:center;overflow-y:auto;z-index:2;flex:1}#epg-container{display:none;z-index:1000;position:fixed;width:100%;height:100%;overflow-y:scroll;overflow-x:scroll;background-color:#282c34}#search-input{display:none}.input-container{position:relative;display:flex;align-items:center;width:100%}#upload-button{width:10%;padding:10px;margin-bottom:10px;margin-left:5px;background-color:#61dafb;color:#000;border:none;border-radius:5px;font-size:1em;cursor:pointer;box-shadow:0 4px 8px rgb(0 0 0 / .3)}#upload-button:hover{background-color:#4fa3c4}</style>
          
          

          
          <div id=videoContainer><video autoplay controls id=videoPlayer></video></div>
          
          
          <div id=playlist><div class=input-container><input id=url-input placeholder="Enter M3U8 Playlist URL"> <input id=file-input style=display:none type=file> <button id=upload-button onclick='document.getElementById("file-input").click()'>↑</button></div><button id=fetch-button>Load Playlist</button> <button id=epg-button onclick=openEPG()>EPG</button> <input id=search-input placeholder=Search...><ul id=video-list></ul></div>
          
          
          

          
          <div id=overlay></div><div id=epg-container></div><script src=https://cdnjs.cloudflare.com/ajax/libs/shaka-player/4.7.11/shaka-player.compiled.js></script><script src=https://dbghelp.github.io/M3U8Interpreter.js></script><script src=https://cdnjs.cloudflare.com/ajax/libs/pako/2.0.4/pako.min.js></script><script src=https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js></script><script src=https://dbghelp.github.io/xml-epg.js></script><script>var xmlepg=new XMLEPG();var overlay=document.getElementById('overlay');var videoContainer=document.getElementById('videoPlayer');var epgContainer=document.getElementById('epg-container');hideOverlayTimeout=null;overlay.addEventListener('mouseenter',()=>{if(hideOverlayTimeout){clearTimeout(hideOverlayTimeout)}
overlay.style.display='flex';videoContainer.style.display='none'});overlay.addEventListener('mouseleave',()=>{overlay.style.display='none';videoContainer.style.display='flex'});document.addEventListener('DOMContentLoaded',()=>{const videoElement=document.getElementById('videoPlayer');const videoList=document.getElementById('video-list');const searchInput=document.getElementById('search-input');const urlInput=document.getElementById('url-input');const fetchButton=document.getElementById('fetch-button');const fileInput=document.getElementById('file-input');const uploadButton=document.getElementById('upload-button');let selectedFileContent=null;var player=new shaka.Player(videoElement);var channels;var lastActiveChannel;shaka.polyfill.installAll();var extracted=extractAppendedURL();if(extracted){document.getElementById('upload-button').remove();document.getElementById('url-input').remove();document.getElementById('fetch-button').remove();setPlaylistFromUrl(extracted)}
fetchButton.addEventListener('click',async()=>{const url=urlInput.value;if(selectedFileContent){setPlaylistFromFile(selectedFileContent)}else if(url){setPlaylistFromUrl(url)}});fileInput.addEventListener('change',(event)=>{const file=event.target.files[0];if(file){urlInput.value=file.name;const reader=new FileReader();reader.onload=(e)=>{selectedFileContent=e.target.result};reader.readAsText(file)}});async function setPlaylistFromUrl(url){try{const response=await fetch(url);if(response.ok){const text=await response.text();parseAndSetPlaylist(text)}else{console.error('Failed to fetch M3U8 playlist.')}}catch(error){console.error('Error fetching M3U8 playlist:',error)}}
async function setPlaylistFromFile(content){parseAndSetPlaylist(content)}
async function parseAndSetPlaylist(content){const m3u8Interpreter=new M3U8Interpreter(content);m3u8Interpreter.parse();channels=m3u8Interpreter.getChannels();const urls=m3u8Interpreter.getUrlTvg();xmlepg.setPlaylistChannels(channels);xmlepg.load(urls).then(()=>{xmlepg.displayAllPrograms('epg-container','xmlepg')});if(urls!=null&&urls.length!==0){document.getElementById('epg-button').style.display='block'}
updatePlaylist(channels);document.getElementById('search-input').style.display='block'}
function extractAppendedURL(){const params=new URLSearchParams(window.location.search);return params.get('file')}
window.loadVideo=function(manifestUrl,licenseKey){if(licenseKey!=null&&!Array.isArray(licenseKey)){licenseKey=JSON.parse(decodeURIComponent(licenseKey))}
if(licenseKey){licenseKey.forEach(pair=>{player.configure({drm:{clearKeys:{[pair.keyId]:pair.key}}})})}
player.load(manifestUrl);videoElement.play()}
function updatePlaylist(channels){videoList.innerHTML='';channels.forEach(channel=>{const listItem=document.createElement('li');listItem.innerHTML=`
										<img src="${channel.tvgLogo}" alt="${channel.channelName} logo">${channel.channelName}
										</span>`;const imgElement=listItem.querySelector('img');imgElement.onmouseenter=()=>{xmlepg.displayPrograms('overlay',channel.tvgId);overlay.style.display='flex';videoContainer.style.display='none';if(hideOverlayTimeout){clearTimeout(hideOverlayTimeout)}};imgElement.onmouseleave=()=>{hideOverlayTimeout=setTimeout(()=>{overlay.style.display='none';videoContainer.style.display='flex'},100)};listItem.onclick=()=>{loadVideo(channel.manifestUrl,channel.licenseKey);const parent=listItem.parentElement;const children=parent.getElementsByTagName('li');for(let i=0;i<children.length;i++){children[i].classList.remove('active')}
listItem.classList.add('active');lastActiveChannel=listItem.innerHTML}
videoList.appendChild(listItem)})}
function filterPlaylist(searchTerm){const filteredChannels=channels.filter(channel=>channel.channelName.toLowerCase().includes(searchTerm.toLowerCase()));updatePlaylist(filteredChannels)}
searchInput.addEventListener('input',(event)=>{const searchTerm=event.target.value;filterPlaylist(searchTerm)})});function openEPG(){epgContainer.style.display='block';xmlepg.timelineNeedleRender()}
function showToast(message){const style=document.createElement('style');style.innerHTML=`
.toast-container{position:absolute;top:20px;right:20px;z-index:9999}.toast{background-color:#333;color:#fff;padding:10px 20px;border-radius:5px;margin-bottom:10px;font-size:16px;box-shadow:0 4px 6px rgb(0 0 0 / .1);opacity:0;animation:fadeIn 0.5s forwards,fadeOut 3s forwards 2s}@keyframes fadeIn{from{opacity:0}to{opacity:1}}@keyframes fadeOut{from{opacity:1}to{opacity:0}}
		  `;document.head.appendChild(style);const toast=document.createElement('div');toast.classList.add('toast');toast.textContent=message;const toastContainer=document.querySelector('.toast-container');if(!toastContainer){const newContainer=document.createElement('div');newContainer.classList.add('toast-container');document.body.appendChild(newContainer)}
document.querySelector('.toast-container').appendChild(toast);setTimeout(()=>{toast.remove()},4000)}
function copyToClipboard(text,name){text=decodeURIComponent(text);navigator.clipboard.writeText(text.replace(/x123x/g,"'")).then(()=>{showToast(name+' command successfully copied to clipboard')}).catch(err=>{showToast('Failed to copy '+name+' download command: ',err)})}</script>


                
          <font color="red">

 <text color="whitegreen">
    <input type="text" id="videoInput" placeholder="กรอก URL ของไฟล์ .m3u8 ที่นี่" />
    <button id="loadPlayer">โหลดวีดีโอ</button>
<button onclick="toggleFullScreen()">เต็มจอ / ย่อจอ</button>
    </text>
    <div class="controls">
        <button class="button" id="stretch">Stretch</button>
        <button class="button" id="crop">Crop</button>
        <button class="button" id="zoom">Zoom</button>
        <button class="button" id="fullscreen">Fullscreen</button>
    </div>
</div>

<script>
    const videoPlayer = document.getElementById('videoPlayer');
    const loadVideoBtn = document.getElementById('loadPlayer');
    const videoInput = document.getElementById('videoInput');
    const fullscreenBtn = document.getElementById('fullscreen');
    
    loadPlayer.addEventListener('click', () => {
        const videoURL = videoInput.value;
        if (videoURL) {
            videoPlayer.src = videoURL; 
            videoPlayer.play(); 
        } else {
            alert('กรุณากรอก URL ของวีดีโอ');
        }
    });
    
    fullscreenBtn.addEventListener('click', () => {
        if (videoPlayer.requestFullscreen) {
            videoPlayer.requestFullscreen();
        } else if (videoPlayer.webkitRequestFullscreen) {
            videoPlayer.webkitRequestFullscreen();
        } else if (videoPlayer.msRequestFullscreen) {
            videoPlayer.msRequestFullscreen();
        }
    });

    const stretchBtn = document.getElementById('stretch');
    const cropBtn = document.getElementById('crop');
    const zoomBtn = document.getElementById('zoom');
    
    stretchBtn.addEventListener('click', () => {
        videoPlayer.style.objectFit = 'fill'; // Stretch
    });

    cropBtn.addEventListener('click', () => {
        videoPlayer.style.objectFit = 'cover'; // Crop
    });

    zoomBtn.addEventListener('click', () => {
        if (videoPlayer.style.objectFit === 'none') {
            videoPlayer.style.objectFit = 'contain'; // Zoom
        } else {
            videoPlayer.style.objectFit = 'none'; // Reset
        }
    });


let isFullScreen = false;
let initialDistance = null;
let scale = 1;

// ฟังก์ชันสำหรับเข้าสู่/ออกจากเต็มจอ
function toggleFullScreen() {
  if (!document.fullscreenElement) {
    document.getElementById('videoPlayer').requestFullscreen()
      .then(() => {
        isFullScreen = objectFit-contain;
      });
  } else {
    document.exitFullscreen().then(() => {
      isFullScreen = false;
      // รีเซ็ตการซูมเมื่อออกจากเต็มจอ
      scale = 1;
      video.style.transform = `scale(${scale})`;
    });
  }
}

// เชื่อมต่อ Event สำหรับ Touch
video.addEventListener('touchstart', handleTouchStart, {passive: false});
video.addEventListener('touchmove', handleTouchMove, {passive: false});
video.addEventListener('touchend', handleTouchEnd);

let lastDistance = 0;

function getDistance(touches) {
  const [touch1, touch2] = touches;
  const dx = touch2.clientX - touch1.clientX;
  const dy = touch2.clientY - touch1.clientY;
  return Math.hypot(dx, dy);
}

function handleTouchStart(e) {
  if (e.touches.length === 2) {
    // เริ่มต้นจับการซูม
    initialDistance = getDistance(e.touches);
    lastDistance = initialDistance;
  }
}

function handleTouchMove(e) {
  if (e.touches.length === 2) {
    e.preventDefault(); // ป้องกันการเลื่อนหน้า
    const currentDistance = getDistance(e.touches);
    const delta = currentDistance - lastDistance;
    lastDistance = currentDistance;

    // คำนวณ scale จาก delta
    const zoomFactor = 0.005; // ปรับความเร็วซูมได้ตามต้องการ
    scale += delta * zoomFactor;

    // จำกัด scale ให้อยู่ในช่วงที่ต้องการ
    if (scale < 0.5) scale = 0.5;
    if (scale > 3) scale = 3;

    // ปรับ scale ของวิดีโอ
    video.style.transform = `scale(${scale})`;
  }
}

function handleTouchEnd(e) {
  if (e.touches.length < 2) {
    initialDistance = null;
  }
}
</script>
</body>
</html>
