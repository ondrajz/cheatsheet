# Go

## How to

### Read build ID from binary

#### With go tool `buildid`

```sh
$ go tool buildid ./binary
# output:
#	_Ysf0-sSFTz_fhCvxCOO/gGAGtSimUqljGsEaAaCy/_rvMOn8YPdNuUsRy3kEY/e7v_cRGgGjkAf2pLjVh7
```

#### With builtin command `readelf`

```sh
$ readelf -p ".note.go.buildid" ./binary
# output:
#	String dump of section '.note.go.buildid':
#	 [     4]  S
#	 [     c]  Go
#	 [    10]  _Ysf0-sSFTz_fhCvxCOO/gGAGtSimUqljGsEaAaCy/_rvMOn8YPdNuUsRy3kEY/e7v_cRGgGjkAf2pLjVh7
```



