# Gowiki

A simple wiki web application built in Go, following the [Writing Web Applications](https://go.dev/doc/articles/wiki/) tutorial.

## Prerequisites

- Go 1.16+

## Installation

```bash
git clone https://github.com/KarimBenkirane/gowiki.git
cd gowiki
go build wiki.go
./wiki
```

The server starts on [http://localhost:8080](http://localhost:8080) and redirects to the FrontPage by default.

## Directory structure

```
gowiki/
├── wiki.go
├── go.mod
├── data/
│   └── FrontPage.txt
├── tmpl/
│   ├── view.html
│   └── edit.html
└── static/     # Static assets (CSS, JS)
```

## Routes

| Route                | Description                                         |
| -------------------- | --------------------------------------------------- |
| `GET /view/{title}`  | View a page. Redirects to edit if it doesn't exist. |
| `GET /edit/{title}`  | Edit a page.                                        |
| `POST /save/{title}` | Save a page.                                        |

## Notes

- Page titles are alphanumeric only.
- Pages are stored as `.txt` files in the `data/` directory.
- Linking between pages is supported using `[PageTitle]` syntax in the page body.

## References

- [Writing Web Applications](https://go.dev/doc/articles/wiki/) — official Go tutorial
- [Finishing the Google Go Writing Web Applications Tutorial](https://larry-price.com/blog/2014/01/07/finishing-the-google-go-writing-web-applications-tutorial/) — Larry Price
