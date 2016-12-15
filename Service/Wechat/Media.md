# upload

## command

```
curl -F media=@6426.mp3 "https://api.weixin.qq.com/cgi-bin/media/upload?access_token=0pDsVAqPGwTM9XHsBLjnqcselECWgKryFhd2NkT7-M7H747NEzz0tOKH7rBxN9-pRX6UcP_rjGpb1GRUW_ydY1qaXcI4m7OfWBVE-AJrrYw&type=voice"
```

```
curl -F media=@6426.mp3 -F filename=hhhhh -F "Content-Disposition:form-data;content-type=audio/mp3;filename=asdf.mp3" "https://api.weixin.qq.com/cgi-bin/media/upload?access_token=6Ru2GVx_-2Tev0fxpH8BbLwqBhLNGQkByefNvFdHqGK99_pTyWBvW2nqOOJ5H0L2Ksvrl8J5Jl4AH4oD5JVm6mxvOK-VDi4VQIGoz1TsSqc&type=voice"
```

http://bbs.csdn.net/topics/391015604

## output

```
{"type":"voice","media_id":"y6ZerdT71toBIJb35MlGhwYDdSL1lMB3PIZK1-IeH-SEaB120yCxsCbN0ylyUF1J","created_at":1444813090}
```

# download

## command

```
curl -I -G "https://api.weixin.qq.com/cgi-bin/media/get?access_token=6Ru2GVx_-2Tev0fxpH8BbLwqBhLNGQkByefNvFdHqGK99_pTyWBvW2nqOOJ5H0L2Ksvrl8J5Jl4AH4oD5JVm6mxvOK-VDi4VQIGoz1TsSqc&media_id=oWwGNk7HTlj2C8Yvv2yOZzcXyytec2QdXxIxde_sehRQ1XMBkfOWw4AX8-MmJa-0"
```

## output

```
HTTP/1.1 200 OK
Server: nginx/1.8.0
Date: Wed, 14 Oct 2015 08:59:00 GMT
Content-Type: audio/amr
Content-Length: 9734
Connection: keep-alive
Content-disposition: attachment; filename="y6ZerdT71toBIJb35MlGhwYDdSL1lMB3PIZK1-IeH-SEaB120yCxsCbN0ylyUF1J.amr"
Cache-Control: no-cache, must-revalidate
```
