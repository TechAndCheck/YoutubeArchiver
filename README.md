# Overview

YoutubeArchiver is a Ruby gem that downloads YouTube Video metadata and media. It works in connjunction with Zenodotus and Hypatia to archive fact-checked image/video posts. YoutubeArchiver exists alongside a collection of other media scrapers created by the Duke Reporter's Lab, including Birdsong (a Twitter scraper), Zorki (an Instagram scraper), and Forki (a Facebook scraper). 

Like the other scrapers, Zorki follows a standard architecture created by @cguess. The scraper is engaged by one of two methods: `Video.lookup` or `Channel.lookup`, which respectively return `YoutubeArchiver::Video` and `YoutubeArchiver::Channel` objects. These psuedo JSON object store video/channel metadata and media. 

`YoutubeArchiver` differs from the other scrapers in how it acquires  media and metadata for a video or channel lookup. `YoutubeArchiver` uses [yt-dlp](https://github.com/yt-dlp/yt-dlp) to download video media files. To download video and channel metadata, the project uses the [YouTube Data API V3](https://developers.google.com/youtube/v3), specifically its [Videos: list](https://developers.google.com/youtube/v3/docs/videos/list) and [Channels: list](https://developers.google.com/youtube/v3/docs/channels/list) endpoints. 

# Setup

## Acquiring a YouTube API key

1. [Create or select](https://console.cloud.google.com/projectselector2/home/dashboard?authuser=0&supportedpurview=project&pli=1) a Google Cloud Project  
2. Find the [Youtube Data API v3](https://console.cloud.google.com/apis/api/youtube.googleapis.com/metrics?project=multi-scrobble-yt&authuser=0&supportedpurview=project) in the Google API marketplace. Enable the API. 
3. Click on the credentials tab link in the YouTube API page sidebar. 
4. Create an "API Key" credential. 

## Setting environment variables
Set the `YOUTUBE_API_KEY` environment variable equal to the API key generated above. 
