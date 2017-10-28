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

    - itag:          137
      container:     mp4
      quality:       1920x1080
      size:          107.8 MiB (113048278 bytes)
    # download-with: you-get --itag=137 [URL]

    - itag:          248
      container:     webm
      quality:       1920x1080
      size:          91.6 MiB (96058892 bytes)
    # download-with: you-get --itag=248 [URL]

    - itag:          136
      container:     mp4
      quality:       1280x720
      size:          57.3 MiB (60064402 bytes)
    # download-with: you-get --itag=136 [URL]

    - itag:          247
      container:     webm
      quality:       1280x720
      size:          52.0 MiB (54503030 bytes)
    # download-with: you-get --itag=247 [URL]

    - itag:          135
      container:     mp4
      quality:       854x480
      size:          28.3 MiB (29683909 bytes)
    # download-with: you-get --itag=135 [URL]

    - itag:          244
      container:     webm
      quality:       854x480
      size:          26.7 MiB (27949342 bytes)
    # download-with: you-get --itag=244 [URL]

    - itag:          243
      container:     webm
      quality:       640x360
      size:          16.6 MiB (17378449 bytes)
    # download-with: you-get --itag=243 [URL]

    - itag:          134
      container:     mp4
      quality:       640x360
      size:          13.9 MiB (14594422 bytes)
    # download-with: you-get --itag=134 [URL]

    - itag:          242
      container:     webm
      quality:       426x240
      size:          10.7 MiB (11234554 bytes)
    # download-with: you-get --itag=242 [URL]

    - itag:          278
      container:     webm
      quality:       256x144
      size:          8.7 MiB (9078202 bytes)
    # download-with: you-get --itag=278 [URL]

    - itag:          133
      container:     mp4
      quality:       426x240
      size:          8.1 MiB (8446498 bytes)
    # download-with: you-get --itag=133 [URL]

    - itag:          160
      container:     mp4
      quality:       256x144
      size:          6.6 MiB (6922722 bytes)
    # download-with: you-get --itag=160 [URL]

    [ DEFAULT ] _________________________________
    - itag:          22
      container:     mp4
      quality:       hd720
      size:          57.3 MiB (60045090 bytes)
    # download-with: you-get --itag=22 [URL]

    - itag:          43
      container:     webm
      quality:       medium
    # download-with: you-get --itag=43 [URL]

    - itag:          18
      container:     mp4
      quality:       medium
    # download-with: you-get --itag=18 [URL]

    - itag:          36
      container:     3gp
      quality:       small
    # download-with: you-get --itag=36 [URL]

    - itag:          17
      container:     3gp
      quality:       small
    # download-with: you-get --itag=17 [URL]
```


Download the video in `3840x2160` quality and save to ~/videos:

```shell
$ docker run --rm -v ~/videos:/download kmdgeek/you-get --itag=313 'https://www.youtube.com/watch?v=EotbKqZmBuY'

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
