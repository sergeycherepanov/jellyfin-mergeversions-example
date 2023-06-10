###
Url: http://localhost:8096/  
User: `admin`  
Password: `admin`  

### Start Stack
```
docker compose up -d
```

### Call the API

```
curl -H 'Host: 127.0.0.1:8096' -H 'User-Agent: Go-http-client/1.1' -H 'Accept: application/json' -H 'Content-Type: application/json' -H 'X-Emby-Token: 660e35fc36d44a6980f57ffaf54acd78' --compressed -X POST http://127.0.0.1:8096/Library/Media/Updated -d '{"Updates":[{"path":"/Volumes/Merged/Adult/Movies/I, Robot (2004)","updateType":"Modified"}]}'
```
