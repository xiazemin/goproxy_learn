func NewServer(ops ServerOps) *Server {
	return &Server{ops: ops}
}

type ServerOps interface {
}

type File interface {
	io.Reader
	io.Seeker
	io.Closer
	Stat() (os.FileInfo, error)
}

type Server struct {
	ops ServerOps
}

func (s *Server) ServeHTTP(w http.ResponseWriter, r *http.Request) {

if strings.HasPrefix(r.URL.Path, "/sumdb/") {
		sumdb.Handler(w, r)
}

i := strings.Index(r.URL.Path, "/@")

modPath, err := module.UnescapePath(strings.TrimPrefix(r.URL.Path[:i], "/"))

switch what {
	case "latest":
		ctype = contentTypeJSON
		f, openErr = s.ops.Latest(ctx, modPath)
	case "v/list":
		ctype = contentTypeText
		f, openErr = s.ops.List(ctx, modPath)
	default:
		what = strings.TrimPrefix(what, "v/")
}

switch ext {
		case ".info":
			ctype = "application/json"
			f, openErr = s.ops.Info(ctx, m)
		case ".mod":
			ctype = "text/plain; charset=UTF-8"
			f, openErr = s.ops.GoMod(ctx, m)
		case ".zip":
			ctype = "application/octet-stream"
			f, openErr = s.ops.Zip(ctx, m)
		default:
			http.Error(w, "request not recognized", http.StatusNotFound)
			return
		}

http.ServeContent(w, r, what, info.ModTime(), f)

type memFile struct {
	*bytes.Reader
	stat memStat
}

type memStat struct {
	t    time.Time
	size int64
}


func NewInfo(version string, t time.Time) File{
	return MemFile(js, t)
}

