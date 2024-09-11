# bdanmaku

[mpv](https://mpv.io) plugin to correctly display Bilibili danmaku.
Powered by [DanmakuFactory](https://github.com/hihkm/DanmakuFactory).

## Installation

First, [install DanmakuFactory](https://github.com/hihkm/DanmakuFactory?tab=readme-ov-file#%E8%8E%B7%E5%8F%96).
Then, see [mpv documentation](https://mpv.io/manual/stable/#script-location) for how to run the script in mpv.

## Usage

First, use [yt-dlp](https://github.com/yt-dlp/yt-dlp) as the youtube-dl executable in mpv
by [setting the `ytdl_path` option](https://mpv.io/manual/stable/#options-ytdl-path).
Then, watch Bilibili video by running a command like this:

```shell
mpv https://www.bilibili.com/video/BV1Sm4y1N78J
```

## Configuration

You can configure the plugin by setting the `script-opts` option in mpv.
Set the DanmakuFactory executable by setting the `dmk2ass_executable` option like this:

```shell
mpv --script-opts=dmk2ass_executable=/path/to/DanmakuFactory https://www.bilibili.com/video/BV1Sm4y1N78J
```

You can also set the `dmk2ass_options` option to pass additional options to DanmakuFactory.
For example, if you want to make the opacity(range: 1-255) of danmaku to 32, you can do this:

```shell
mpv --script-opts=dmk2ass_options=-O\ 32 https://www.bilibili.com/video/BV1Sm4y1N78J
```

## Notice for Windows users

You have to specify the `tmpdir` option on Windows (e.g. `--script-opts=tmpdir=C:\tmp`).
Otherwise, downloading danmaku will fail.
