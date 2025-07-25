# YouTube Clipper PHP Package

[GitHub Repository](https://github.com/roamingwilson/youtube-tools)

Download and cut clips from YouTube videos using [`yt-dlp`](https://github.com/yt-dlp/yt-dlp) and [`ffmpeg`](https://ffmpeg.org/), and cut them into smaller clips.

## 📦 Installation

### Requirements

- PHP 7.4+
- `yt-dlp` installed
- `ffmpeg` installed

### Install on Different OS:

#### ✅ Ubuntu / Debian
```bash
sudo apt update
sudo apt install ffmpeg
pip install -U yt-dlp
```

#### ✅ macOS
```bash
brew install ffmpeg
pip install -U yt-dlp
```

#### Install the PHP package
```bash
composer require roamingwilson/youtube-tools
```
### Usage

```php
use RoamingWilson\YouTubeTools\YouTubeClipper;

$clipper = new YouTubeClipper(
    '/your/temp/dir',                 // Optional temp directory
    '/your/cookies.txt'              // Optional cookies.txt file from browser
);

$result = $clipper->downloadAndCut(
    'https://www.youtube.com/watch?v=dQw4w9WgXcQ', 
    [
        ['from' => '00:00:00', 'to' => '00:00:10'],
        ['from' => '00:01:00', 'to' => '00:01:30'],
    ],
    '/your/output/dir'
);

print_r($result);
```

### How to get cookies.txt
To get the `cookies.txt` file, you can use browser extensions like [Get cookies.txt LOCALLY](https://chromewebstore.google.com/detail/get-cookiestxt-locally/cclelndahbckbenkjhflpdbgdldlbecc). Visit YouTube and export the cookies.

### 🛠 Features
- Download any YouTube video with yt-dlp
- Cut multiple time-based clips using ffmpeg
- Optional crop (if `crop_x`, `crop_y`, `crop_width`, `crop_height` provided)