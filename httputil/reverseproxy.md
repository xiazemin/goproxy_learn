type ReverseProxy struct {
	Director func(*http.Request)
    ModifyResponse func(*http.Response) error
}

type BufferPool interface {
	Get() []byte
	Put([]byte)
}


func NewSingleHostReverseProxy(target *url.URL) *ReverseProxy {
director := func(req *http.Request) {
}
return &ReverseProxy{Director: director}
}

func copyHeader(dst, src http.Header)

func (p *ReverseProxy) modifyResponse(rw http.ResponseWriter, res *http.Response, req *http.Request) bool 

func (p *ReverseProxy) ServeHTTP(rw http.ResponseWriter, req *http.Request)

res, err := transport.RoundTrip(outreq)


func shouldPanicOnCopyError(req *http.Request) bool {
}




func (p *ReverseProxy) handleUpgradeResponse(rw http.ResponseWriter, req *http.Request, res *http.Response) 
conn, brw, err := hj.Hijack()


https://blog.csdn.net/idwtwt/article/details/52588762

https://blog.csdn.net/puss0/article/details/103484163
