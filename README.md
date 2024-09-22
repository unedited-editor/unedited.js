# unedited.js
The javascript API for unedited video editor.

Thought process 1 - <br/><br/>
EXTRACTION:<br/>
Get video information with mediainfo.js / wasm (video and audio tracks + encoding information)<br/>
Extract individual frames with video decoder (supported everywhere, besides ff android) - https://developer.mozilla.org/en-US/docs/Web/API/VideoDecoder#browser_compatibility<br/>
Extract audio track with MediaSource Extensions (MSE) and AudioContext API (iOS safari and iOS webview not supported) - https://developer.mozilla.org/en-US/docs/Web/API/MediaSource#browser_compatibility & https://developer.mozilla.org/en-US/docs/Web/API/AudioContext#browser_compatibility<br/>
Extract subtitles tracks with MP4box.js?<br/>
FFmpeg WASM - fallback for video & audio extraction<br/>
Extract GIF into seperate frames<br/>
Images & Audio imported directly, nothing needs to be done.<br/>
<br/>
COMPILING:<br/>
MP4box.js - MP4, WebM, Mov, Mkv (frames + audio + subtitles) <br/>
Use Video Encoder only if no audio or subtitles - https://developer.mozilla.org/en-US/docs/Web/API/VideoEncoder#browser_compatibility<br/>
use gif.js to make gifs.<br/>
FFmpeg WASM - fallback for other export types, create mp4, then convert to other types<br/>
Other - https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder#browser_compatibility & https://github.com/Yahweasel/libav.js/ & https://news.ycombinator.com/item?id=38069974
