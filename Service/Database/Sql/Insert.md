```
INSERT INTO media (media_uuid, url, media_id) VALUES ('VHVlIFNlcCAyOSAyMDE1IDE1OjE5OjQzIEdNVCswODAwIChDU1QpOjpwcXY5XzY4dExjNDdXanNNc2Z6eGRIU2d6YTJ1dTlTdGRFODRucTlOR2l2TVVJY3U4VEJkWHFfOXVYdi1sRFeu', 'http://voice-answer.oss-cn-beijing.aliyuncs.com/voice/VHVlIFNlcCAyOSAyMDE1IDE1OjE5OjQzIEdNVCswODAwIChDU1QpOjpwcXY5XzY4dExjNDdXanNNc2Z6eGRIU2d6YTJ1dTlTdGRFODRucTlOR2l2TVVJY3U4VEJkWHFfOXVYdi1sRFeu', 'I do not have a media_id');
```

```
insert into users (created_at,mobile_phone_verified,quota,daily_quota,last_quota_time,wx_info,roles) values (now(),false,990, 5, now(), '{"sex": 1, "city": "", "openid": "oXXz4t0ONvpJKl2ptmpiQcNxidkk", "remark": "", "country": "英国", "groupid": 0, "unionid": "oAzn5t6YhhZCWtQY_Uy63HLMS6Jk", "language": "en", "nickname": "Seth", "province": "", "subscribe": 1, "headimgurl": "http://wx.qlogo.cn/mmopen/Z9Ck33FoNY5HdB3ww3FNHzKQ9EH0cwuYcMuzeknAk3GZicF7liciakf8WEwbaiaDue7L3HTiaNTmbQKYAIsDBYqjgQkVmGmX2B5xO/0", "subscribe_time": 1432274473}', '{"admin"}');
```

There is an alternative to using COPY, which is the multirow values syntax that Postgres supports. From the documentation:

```
INSERT INTO films (code, title, did, date_prod, kind) VALUES
    ('B6717', 'Tampopo', 110, '1985-02-10', 'Comedy'),
    ('HG120', 'The Dinner Game', 140, DEFAULT, 'Comedy');
```

Dupulica a row

```
insert into posts (created_at, updated_at, title, user_id, stocks, anonymous, published, content, poster, topics, source_link, source_created_at, source_text, summary, open_in_browser, source_name, route, route_data, extra_data, investors ) select created_at, updated_at, title, user_id, stocks, anonymous, published, content, poster, topics, source_link, source_created_at, source_text, summary, open_in_browser, source_name, route, route_data, extra_data, investors from posts where id=15220;
```