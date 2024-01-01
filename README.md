# Soundcloud Playlist Downloader
A simple bash script using yt-dlp to download playlists from soundcloud with account authorisation (for private playlists and Go+ songs).

Note: it is against [Soundclouds Terms of Use](https://soundcloud.com/terms-of-use) section (v) to use automated interactions, your account may be disabled for using this script.

## Requirements
You must have `ffmpeg` and `yt-dlp` installed, these can be installed via your package manager, for debian based linux distros use:
```bash
sudo apt-get install ffmpeg yt-dlp -y
```

## Initial Setup

### Initial Modifications
1) Download the script:
```bash
curl https://raw.githubusercontent.com/peterc-s/Soundcloud-Playlist-Downloader/main/sc-dl -o sc-dl; chmod +x sc-dl
```

3) Replace the '/path/to/save/directory' with the path to the directory you want to save the playlists to. Each playlist will be put in its own folder.
4) Replace put playlists in the `playlists` dictionary with the playlists you want to download in the format given.

### Account Authorisation
1) Navigate to [Soundcloud](https://soundcloud.com/) and sign in.
2) Open up your browsers developer tools (usually `F12`) and navigate to the network tab (`ctrl-shift-E` might work).
3) Reload the page and look for a POST request with `me` in it:

![image](https://github.com/peterc-s/Soundcloud-Playlist-Downloader/assets/66807853/77446987-dc3f-4624-9143-d4d41efad3ae)

4) Click on the POST request and look for the request header named "Authorization":

![image](https://github.com/peterc-s/Soundcloud-Playlist-Downloader/assets/66807853/a15de6b7-5bdf-4595-83ce-18389b5cf759)

5) Copy the OAuth key and replace the placeholder (`OAuth x-xxxxxx-xxxxxxxxxx-xxxxxxxxxxxx`) with your key.
6) Find your user agent in the same POST request:

![image](https://github.com/peterc-s/Soundcloud-Playlist-Downloader/assets/66807853/db769ef1-fd5d-49d3-8a3a-bf019fd1b80d)

7) Replace the placeholder (`'YOUR USER AGENT'`) with your user agent.

You are now ready to run the script!

## Usage
Execute the script and let it run:
```bash
./sc-dl
```

You should now have all the songs in your playlists downloaded with thumbnails and metadata, enjoy!

## Credits
This script is modified from [this blog post](https://blog.rtrace.io/posts/how-to-youtube-dl/index.html) by Raffael (AKA 'Ruffy'). Please read this blog post for legal and ethical implications.
