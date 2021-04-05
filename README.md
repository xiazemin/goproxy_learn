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

