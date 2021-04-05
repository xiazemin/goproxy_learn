% ls
Dockerfile              contrib                 main.go                 scripts
LICENSE                 docker-compose.yaml     proxy                   sumdb
Makefile                go.mod                  renameio                test
README.md               go.sum                  robustio

main.go
func init()
func getDownloadRoot() string

func main() 

handle = &logger{proxy.NewRouter(proxy.NewServer(new(ops)), &proxy.RouterOptions{
    Pattern:      excludeHost,
    Proxy:        proxyHost,
    DownloadRoot: downloadRoot,
})}

handle = &logger{proxy.NewServer(new(ops))}

server := &http.Server{Addr: listen, Handler: handle}

func (l *logger) ServeHTTP(w http.ResponseWriter, r *http.Request)

type ops struct{}

func (*ops) List(ctx context.Context, mpath string) (proxy.File, error)

func (*ops) Latest(ctx context.Context, path string) (proxy.File, error) {
	d, err := download(module.Version{Path: path, Version: "latest"})

func (*ops) Info(ctx context.Context, m module.Version) (proxy.File, error) 

func (*ops) GoMod(ctx context.Context, m module.Version) (proxy.File, error)

func (*ops) Zip(ctx context.Context, m module.Version) (proxy.File, error)



type downloadInfo struct {
	Path     string
	Version  string
	Info     string
	GoMod    string
	Zip      string
	Dir      string
	Sum      string
	GoModSum string
}
