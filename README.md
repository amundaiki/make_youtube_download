# YouTube Video Downloader API

En enkel API for å laste ned YouTube-videoer ved hjelp av yt-dlp.

## Lokal Testing

```bash
# Installer avhengigheter
pip install -r requirements.txt

# Kjør serveren
python app.py
```

## Deploy til Railway

1. Gå til [Railway.app](https://railway.app)
2. Klikk "New Project" → "Deploy from GitHub repo"
3. Velg dette repositoryet
4. Railway vil automatisk detektere Python og deploye

## API Endepunkter

### POST /download
Last ned en YouTube-video

**Request:**
```json
{
  "url": "https://www.youtube.com/watch?v=VIDEO_ID"
}
```

**Response:**
```json
{
  "success": true,
  "video_id": "VIDEO_ID",
  "title": "Video Title",
  "download_url": "/file/VIDEO_ID.mp4"
}
```

### GET /file/{filename}
Hent den nedlastede filen

### POST /info
Få informasjon om en video uten å laste den ned

**Request:**
```json
{
  "url": "https://www.youtube.com/watch?v=VIDEO_ID"
}
```

## Bruk i Make.com

1. Bruk **HTTP** modulen
2. Velg **Make a request**
3. URL: `https://din-railway-app.railway.app/download`
4. Method: POST
5. Body type: JSON
6. Body:
```json
{
  "url": "{{youtube_url}}"
}
```

## Miljøvariabler (Valgfritt)

Ingen påkrevd, men du kan legge til:
- `PORT` - Railway setter dette automatisk
