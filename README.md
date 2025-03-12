# blogdor

really simple static blog generator and tooling, all in a single bash file

## requirements

the bash script expects the following programs to be on your $PATH:

- **bash**: at the time of writing I use v5.2.37.
- **pandoc**: does most of the heavy lifting.
- **python3** (optional): used to serve files during development.
- **imagemagick** (optional): helps with image support.

## installation

have `$HOME/local/bin` on your path.

```
curl -sLo "$HOME/.local/bin/blogdor" "https://raw.githubusercontent.com/rconjoe/blogdor/refs/heads/master/blogdor"

chmod +x "$HOME/.local/bin/blogdor"
```

## usage

`blogdor` requires an empty file simply titled `.blogdor` in the root directory of the blog.

_in the future, the status check on this file (present & empty) will be used to determine error handling operations._
_ for now, it just ensures we don't try to build in a directory that isn't the root of a blog._

```
  ./blogdor                 Build the blog (excluding drafts)
  ./blogdor new [title]     Create a new blog post
  ./blogdor preview         Build the blog including draft posts
  ./blogdor serve           Start a local server for the public site
  ./blogdor serve-preview   Start a local server for the preview site
  ./blogdor clean           Remove the build directories
  ./blogdor help            Show this help message
```
