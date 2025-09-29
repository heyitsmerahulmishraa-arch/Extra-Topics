# Extra-Topics
## Install yt-dlp and ffmpeg
- Download ffmpeg [ffmpeg.org](https://www.gyan.dev/ffmpeg/builds/?utm_source=chatgpt.com)
- Download yt-dlp [yt-dlp.exe](https://github.com/yt-dlp/yt-dlp/releases)
- Download 7-zip [7-zip.org](https://www.7-zip.org/download.html)

Add both yt-dlp.exe and ffmpeg.exe to your system PATH (or keep them in the same folder).
like yt-dlp add on ffmpeg bin folder and add ffmpeg bin folder on enviroment variables path.

## Basic Download Command
Download the best quality video + audio (merged with ffmpeg)
- `-f` Format
- `bv*+ba` best video + best audio
- `b` fallback to best available
```bash
yt-dlp -f "bv*+ba/b" <video_url>
```

### Save with custom filename
- `-o` Output
- bydefault its download on C drive's user folder
```bash
yt-dlp -o "%(title)s.%(ext)s" <video_url>
```

### Extract audio only (mp3/opus/etx.)
- `--audio-format mp3` convert with ffmpeg
- `--audio-quality 0` best quality
```bash
yt-dlp -f bestaudio --extract-audio --audio-format mp3 --audio-quality 0 <video_url>
```

### Download playlist
```bash
yt-dlp -o "%(playlist_index)s - %(title)s.%(ext)s" <playlist_url>
```

### Download playlist best quality
```bash
yt-dlp -f "bv*+ba/b" -o "E:\Frontend\%(playlist_index)s - %(title)s.%(ext)s" <playlist_url>
```




