# XiamiMusicAPI
虾米音乐 API，PHP 版
基于虾米音乐 web 端接口改写的 PHP 版本，已经对低版本 PHP 进行兼容， 建议 PHP 5.6 以上环境  
本 API 为个人学习作品，请支持正版音乐，勿滥用

### Function
 - [x] 关键字搜索
 - [x] 歌手热门单曲
 - [x] 歌曲详细信息
 - [x] 专辑解析
 - [x] 歌单解析
 - [x] 歌曲地址获取
 - [] 歌词解析

### Get Started

```php
<?php
# just download the XiamiMusicAPI.php into directory, require it with the correct path.
require_once 'XiamiMusicAPI.php';

# Initialize
$api = new XiamiMusicAPI();

# Get data
$result = $api->search('hello');
// $result = $api->artist('23485');
// $result = $api->detail('1774998338');
// $result = $api->album('2100226190');
// $result = $api->playlist('123020403');
// $result = $api->url('1774998338');

# return JSON, just use it
$data=json_decode($result);
header('Content-type: application/json; charset=UTF-8');
echo json_encode($data,JSON_UNESCAPED_UNICODE|JSON_PRETTY_PRINT|JSON_UNESCAPED_SLASHES);
```

```json
{
    "state": 0,
    "message": "",
    "request_id": "0ab6004714812906866643578e",
    "data": {
        "songs": [
            {
                "song_id": 1774998338,
                "song_name": "Hello",
                "album_id": 2100226190,
                "album_name": "Hello",
                "album_logo": "http://img.xiami.net/images/album/img85/23485/21002261901445585261_1.jpeg",
                "artist_id": 23485,
                "artist_name": "Adele",
                "artist_logo": "http://img.xiami.net/images/artistlogo/93/14569905318193_1.jpg",
                "listen_file": "http://m5.file.xiami.com/485/23485/2100226190/1774998338_59030550_l.mp3?auth_key=2fb54d67cd0fae78af85c02a40e41c20-1481857200-0-null",
                "demo": 0,
                "need_pay_flag": 0,
                "purview_roles": [
                    {
                        "quality": "l",
                        "operation_list": [
                            {
                                "purpose": 1,
                                "upgrade_role": 0
                            },
                            {
                                "purpose": 2,
                                "upgrade_role": 0
                            }
                        ]
                    },
                    {
                        "quality": "h",
                        "operation_list": [
                            {
                                "purpose": 1,
                                "upgrade_role": 0
                            },
                            {
                                "purpose": 2,
                                "upgrade_role": 0
                            }
                        ]
                    },
                    {
                        "quality": "s",
                        "operation_list": [
                            {
                                "purpose": 1,
                                "upgrade_role": 1
                            },
                            {
                                "purpose": 2,
                                "upgrade_role": 1
                            }
                        ]
                    }
                ],
                "is_play": 0,
                "lyric": "",
                "play_counts": 0,
                "singer": ""
            },
            ...
        ],
        "total": 14855,
        "previous": 0,
        "next": 0
    }
}
```

### Link
 - [METO Blog](https://i-meto.com/)
 - [DEMO](https://music.i-meto.com/xiami)  

### License
XiamiMusicApi is under the MIT license.

