# docker-you-get
This is a docker for you-get (https://github.com/soimort/you-get). Available at https://hub.docker.com/r/kmdgeek/you-get/


### Tags
- `latest`: Use the official release of you-get that distributed on PyPI.
- `dev`: Use the latest develop branch of you-get: https://github.com/soimort/you-get/tree/develop .

### Usage
If you know how to use you-get (see https://github.com/soimort/you-get), you can easily use this docker image.

By default, videos will be saved to `/download` in the container, so, you should set volume like this:

```shell
docker run --rm -v /some/path/to/save/videos:/download kmdgeek/you-get [OPTIONS..] URL
```

### Example
Take this video as an example: `https://www.youtube.com/watch?v=EotbKqZmBuY`

To get quality and formats:

```shell
$ docker run --rm kmdgeek/you-get -i 'https://www.youtube.com/watch?v=EotbKqZmBuY'
```
```
site:                YouTube
title:               The Great Wall of China in 4k - DJI Phantom 4
streams:             # Available quality and codecs
    [ DASH ] ____________________________________
    - itag:          313
      container:     webm
      quality:       3840x2160
      size:          645.6 MiB (676945940 bytes)
    # download-with: you-get --itag=313 [URL]

    - itag:          271
      container:     webm
      quality:       2560x1440
      size:          286.9 MiB (300792483 bytes)
    # download-with: you-get --itag=271 [URL]

    - itag:          264
      container:     mp4
      quality:       2560x1440
      size:          257.9 MiB (270429128 bytes)
    # download-with: you-get --itag=264 [URL]

    ...
```

***

Download the video in `3840x2160` quality and save to ~/videos:

```shell
$ docker run --rm -v ~/videos:/download kmdgeek/you-get --itag=313 'https://www.youtube.com/watch?v=EotbKqZmBuY'
```
```
site:                YouTube
title:               The Great Wall of China in 4k - DJI Phantom 4
stream:
    - itag:          313
      container:     webm
      quality:       3840x2160
      size:          645.6 MiB (676945940 bytes)
    # download-with: you-get --itag=313 [URL]

Downloading The Great Wall of China in 4k - DJI Phantom 4.webm ...
 100% (645.6/645.6MB) ├█████████████████████████████████████████┤[2/2]   11 MB/s
Merging video parts... Merged into The Great Wall of China in 4k - DJI Phantom 4.webm
```
