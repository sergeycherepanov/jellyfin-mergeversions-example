###
Url: http://localhost:8096/  
User: `admin`  
Password: `admin`  

### Steps to reproduce  

1. Clone the repo: `https://github.com/sergeycherepanov/jellyfin-mergeversions-example`  

1. Navigate to folder and run docker compose   `docker compose up -d`

1. Create Movies library with the path `/Volumes/Merged/Adult/Movies` and wait until the library to be scanned  

1. Merge movies via the plugin page or scheduled tasks menu

1. Rename one of files in the `Volumes/Merged/Adult/Movies/I, Robot (2004)`  

1. Call the API update
```
curl -H 'Host: 127.0.0.1' -H 'User-Agent: Go-http-client/1.1' -H 'Accept: application/json' -H 'Content-Type: application/json' -H 'X-Emby-Token: 660e35fc36d44a6980f57ffaf54acd78' --compressed -X POST http://127.0.0.1:8096/Library/Media/Updated -d '{"Updates":[{"path":"/Volumes/Merged/Adult/Movies/I, Robot (2004)","updateType":"Modified"}]}' -v
``` 
7. Wait a few minutes for the result.  
