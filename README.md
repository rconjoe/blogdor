# blogdor

really simple static blog generator and tooling, all in a single bash file.
it is meant to meet the following requirements i have for my personal blog:

1. create new blog posts in markdown
2. translate markdown to html
3. publish html to servers
4. support easy image usage in posts
5. support drafts
6. archive posts
7. fit in a single bash file

## why

once upon a time, I used [vimwiki](https://github.com/vimwiki/vimwiki) for my blog, and it was heaven.
it doesn't work the same for me in neovim nowadays, after which i tried hexo, next.js, hugo, gatsby, and jekyll.

this is basically a counter-reaction to everything that list having too many features for my requirements.

since everything i need to do throughout the process can fit in a single bash file, i made `blogdor`.

## requirements

the script is written to run on any linux system with a bash shell and the following programs on $PATH:

- **bash**: at the time of writing I use v5.2.37.
- **pandoc**: does most of the heavy lifting.
- **python3**: used to serve files during development.
- **imagemagick**: helps with image support.

## installation

have `$HOME/local/bin` on your path.

```
curl -sLo "$HOME/.local/bin/blogdor" "https://raw.githubusercontent.com/rconjoe/blogdor/refs/heads/master/blogdor"

chmod +x "$HOME/.local/bin/blogdor"
```

## usage

`blogdor` requires an empty file simply titled `.blogdor` in the root directory of the blog.

_(in the future, the status check on this file (present & empty) will be used to determine error handling operations.
for now, it just ensures we don't try to build in a directory that isn't the root of a blog._

**you need a `template.html`, `style.css`, and `metadata.yaml` in the root directory for the program to work.**

```
  ./blogdor                 Build the blog (excluding drafts)
  ./blogdor new [title]     Create a new blog post
  ./blogdor preview         Build the blog including draft posts
  ./blogdor serve           Start a local server for the public site
  ./blogdor serve-preview   Start a local server for the preview site
  ./blogdor clean           Remove the build directories
  ./blogdor help            Show this help message
```

## LICENSE

MIT.

don't ask me for help before you submit a PR. even then, i might ignore you.
