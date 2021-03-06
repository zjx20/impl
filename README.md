Declaration: this is a fork of https://github.com/josharian/impl, and some custom features have been added into.

------

`impl` generates method stubs for implementing an interface.

```bash
go get -u github.com/zjx20/impl
```

Sample usage:

```bash
$ impl 'f *File' io.ReadWriteCloser
func (f *File) Read(p []byte) (n int, err error) {
	panic("not implemented")
}

func (f *File) Write(p []byte) (n int, err error) {
	panic("not implemented")
}

func (f *File) Close() error {
	panic("not implemented")
}

# You can also provide a full name by specifying the package path.
# This helps in cases where the interface can't be guessed
# just from the package name and interface name.
$ impl 's *Source' golang.org/x/oauth2.TokenSource
func (s *Source) Token() (*oauth2.Token, error) {
    panic("not implemented")
}
```

`impl` could also be used as a package, see the sample code cli/impl.go or [godoc](https://godoc.org/github.com/zjx20/impl) for details.
