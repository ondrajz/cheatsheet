# Go Cheatsheet

## Read build ID from Go binary

- Using Go tool [`buildid`](https://pkg.go.dev/cmd/buildid)

  ```sh
  ➤ go tool buildid ./binary
  # output:
  #	_Ysf0-sSFTz_fhCvxCOO/gGAGtSimUqljGsEaAaCy/_rvMOn8YPdNuUsRy3kEY/e7v_cRGgGjkAf2pLjVh7
  ```

- Using linux command [`readelf`](https://man7.org/linux/man-pages/man1/readelf.1.html)

  ```sh
  ➤ readelf -p ".note.go.buildid" ./binary
  # output:
  #	String dump of section '.note.go.buildid':
  #	 [     4]  S
  #	 [     c]  Go
  #	 [    10]  _Ysf0-sSFTz_fhCvxCOO/gGAGtSimUqljGsEaAaCy/_rvMOn8YPdNuUsRy3kEY/e7v_cRGgGjkAf2pLjVh7
  ```

## Get project info for a package path

  ```sh
  ➤ export GO111MODULE=on
  ➤ go get -u -d github.com/golang/gddo@latest
  ➤ cd $(go list -m -f '{{.Dir}}' github.com/golang/gddo@latest)
  ➤ go run ./gosrc/print.go github.com/ofabry/go-callvis
  ImportPath     github.com/ofabry/go-callvis
  ResovledPath   github.com/ofabry/go-callvis
  ProjectRoot    github.com/ofabry/go-callvis
  ProjectName    go-callvis
  ProjectURL     https://github.com/ofabry/go-callvis
  VCS            git
  Etag           71bdc75f8bf8f3730757679bb7c645ee2fcfd3d1
  BrowseURL      https://github.com/ofabry/go-callvis
  Subdirectories examples, images
  LineFmt        %s#L%d
  Files:
                       README.md  6554 https://github.com/ofabry/go-callvis/blob/master/README.md
                     analysis.go  7102 https://github.com/ofabry/go-callvis/blob/master/analysis.go
                          dot.go  4543 https://github.com/ofabry/go-callvis/blob/master/dot.go
                      handler.go  1402 https://github.com/ofabry/go-callvis/blob/master/handler.go
                         main.go  4229 https://github.com/ofabry/go-callvis/blob/master/main.go
                       output.go 10289 https://github.com/ofabry/go-callvis/blob/master/output.go
                      version.go   172 https://github.com/ofabry/go-callvis/blob/master/version.go
  ```      
  
