func NewRouter(srv *Server, opts *RouterOptions) *Router
	rt := &Router{
		opts: opts,
		srv:  srv,
	}

    remote, err := url.Parse(opts.Proxy)

    proxy := httputil.NewSingleHostReverseProxy(remote)

    proxy.Director = func(r *http.Request) {
        director(r)
        r.Host = remote.Host
    }

    rt.proxy.Transport = &http.Transport{
        Proxy:           http.ProxyFromEnvironment,
        TLSClientConfig: &tls.Config{InsecureSkipVerify: true},
    }


type RouterOptions struct {
	Pattern      string
	Proxy        string
	DownloadRoot string
}


type Router struct {
	opts         *RouterOptions
	srv          *Server
	proxy        *httputil.ReverseProxy
	pattern      string
	downloadRoot string
}

func (router *Router) customModResponse(r *http.Response) error {
if r.StatusCode == http.StatusFound {
_, err := url.Parse(loc)
}
}

func (rt *Router) Direct(path string) bool 

func (rt *Router) ServeHTTP(w http.ResponseWriter, r *http.Request) {
if strings.HasPrefix(r.URL.Path, "/sumdb/") {
		sumdb.Handler(mw, r)
}

if strings.HasSuffix(r.URL.Path, "/@latest") {
}
rt.proxy.ServeHTTP(mw, r)
}

func GlobsMatchPath(globs, target string) bool {
matched, _ := path.Match(glob, prefix)
}