# Notes on How to Download a Youtube Video

url\_format: [ `https://www.youtube.com/watch?v=%s&gl=US&hl=en&has_verified=1&bpctr=9999999999`, video_id ]

Get the above web page. It contains `ytplayer.config` which is assigned a JSON. Get that JSON. It contains all the information pertaining to the video.

## Try these after extracting the config
-  Find 'dashmpd' in 'args' inside the config. 
-  Find 'ypc_vid' in 'args' inside the config.
-  Find 'sts' and store it. 

## Getting video_info
Send request to [ `https://www.youtube.com/get_video_info` ] using 

```
url_params {
	'video_id': video_id,
	'ps': 'default',
	'eurl': '',
	'gl': 'US',
	'hl': 'en',
	'el': 'info',
	'sts': sts,
}
```

## Find these in the video_info 
* `url_encoded_fmt_stream_map`
* `fmt_list`

## Parsing links in `url_encoded_fmt_stream_map`
