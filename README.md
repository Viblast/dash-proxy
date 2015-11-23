# Dash Proxy
dash proxy is a tool that allows for easy downloading or mirroring of remote MPEG-DASH streams.

## How to use

### Mirroring a remote live stream
```shell
./dashproxy.py http://server.com/Manifest.mpd -o .
```
The content of `http://server.com/Manifest.m3u8` will be downloaded to the output directory (specified by `-o`). The playlist will be constantly refreshed and when new content is available it will be also downloaded while old content will be removed. This will practically mirror the remote stream in the output directory (`-o`). The downloaded stream itself can be served using any HTTP server.

### Downloading a remote live stream
```shell
./dashproxy.py http://server.com/Manifest.mpd -o . -d
```
This will behave just as the above command except that old content will not be deleted effectively downloading the live stream in the output directory (`-o`). This is useful for downloading a long sample of a live stream that can latter be used for debugging and testing puposes.

### Downloaidng a remote VoD steram
```shell
./dashproxy.py http://server.com/Manifest.mpd -o . -d
```
The VoD stream will be downloaded in the output directory (`-o`). In this case the download (`-d`) parameter is effectively ignored. In this example it is provided for clarity.

## Supported features
 * Segment list
 * Manifests that reference whole .mp4 files and don't contain additional info

## Dependencies
 * [Requests](http://docs.python-requests.org/en/latest/)

## License
MIT

