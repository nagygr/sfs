# Simple File Server (SFS)

This application starts a file server that serves a directory's contents on
HTTP in the local network.

By default it serves the directory that it is started in, and listens on port
8100. Both values can be changed on the command line:

-	`-d <path>`: sets the path that is served by sfs
-	`-p <port>`: sets the port that sfs listens on

The file server is accessible on the local network at the address of the host
machine. The program prints this information on standard out so the address
doesn't need to be looked up. The output of the program is something like this:

```
2022/12/30 23:21:54 Serving . on HTTP port: 8100
2022/12/30 23:21:54 Within your local network, browse: 192.168.0.105:8100
2022/12/30 23:21:54 Use -d <path> to change the served directory, -p <port> to change the port
```

## Compilation

The application needs to be compiled. In order to do that, a working Go build environment
is needed. Please refer to your distribution's package manager or visit
[this][1] page for information on how to install Go.

>	**Note**
>
>	Go can typically be installed using package managers, although it might not
>	be the latest version that's available (especially if the package manager
>	serves a point release distribution). Some install commands for popular
>	package managers are:
>
>	Arch/Manjaro: `pacman -S go`
>	Fedora: `dnf install golang`
>	Ubuntu: `apt-get install golang`

Once Go is available on the system, the compilation can be performed by
issuing:

```bash
go build -mod=mod -o build/sfs ./cmd/sfs
```

or by using the attached Makefile:

```bash
make all
```

The binary will be available in the `build` folder of the repositry root.

## Installation

The application can also be installed from `github` using the following
command:

```bash
go install github.com/nagygr/sfs/cmd/sfs@latest
```

>	**Note**
>
>	Please note, that the command above also requires Go to be installed on the
>	system. Please see details about Go installation above.

[1]: https://go.dev/doc/install

