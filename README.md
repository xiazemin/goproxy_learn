https://studygolang.com/articles/21379
https://leileiluoluo.com/posts/golang-modfetch-package.html

https://github.com/gomods/athens

 % git submodule add https://github.com/goproxyio/goproxy goproxy               
正克隆到 '/Users/xiazemin/go/src/github.com/xiazemin/goproxy_learn/goproxy'...


sumdb/handle.go
var supportedSumDB = []string{
	"sum.golang.org",
	"gosum.io",
}

func Handler(w http.ResponseWriter, r *http.Request) {
	if strings.HasSuffix(r.URL.Path, "/supported") {

func sumViaGoproxy(w http.ResponseWriter, r *http.Request) {
	p := "https://goproxy.io" + r.URL.Path
	proxySumdb(p, w, r)

func proxySumdb(p string, w http.ResponseWriter, r *http.Request)
	resp, err := http.Get(p)



func ServeContent(w ResponseWriter, req *Request, name string, modtime time.Time, content io.ReadSeeker)//该函数使用提供的ReaderSeeker提供的内容来恢复请求,该函数相对于io.Copy的优点是可以处理范围类请求,设定MIME类型,并且处理了If-Modified-Since请求.如果未设定content-type类型,该函数首先通过文件扩展名来判断类型,如果失效的话,读取content的第一块数据并将他传递给DetectContentType进行类型判断.name可以不被使用,更进一步说,他可以为空并且不在respone中返回.如果modtime不是0时间,该时间则体现在response的最后一次修改的header中,如果请求包括一个If-Modified-Since header,该函数利用modtime来决定是否发送该content.该函数利用Seek功能来决定content的大小.

https://studygolang.com/articles/2680

https://blog.csdn.net/whatday/article/details/109747385

https://github.com/golang/go/issues/43822




https://leileiluoluo.com/posts/golang-modfetch-package.html

https://studygolang.com/articles/21379

https://github.com/goproxyio/goproxy


	if excludeHost != "" {
		os.Setenv("GOPRIVATE", excludeHost)
	}



	// Direct decides whether a path should directly access.
func (rt *Router) Direct(path string) bool {
	if rt.pattern == "" {
		return false
	}
	return GlobsMatchPath(rt.pattern, path)
}

GOPRIVATE 的跳过



func sumViaGoproxy(w http.ResponseWriter, r *http.Request) {
	p := "https://goproxy.io" + r.URL.Path
	proxySumdb(p, w, r)
}

