# Ajay Singh's website

## Run locally

Prerequisites: Ruby and Bundler. On macOS, install Ruby with Homebrew:
`brew install ruby`.

```sh
git clone https://github.com/ajaydeepsingh/ajaydeepsingh.github.io.git
cd ajaydeepsingh.github.io
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000) in your browser. Jekyll
regenerates the site when source files change.

To enable LiveReload, use a different port if the default is already in use:

```sh
bundle exec jekyll serve --livereload --livereload-port 35730
```

## Validate changes

```sh
bundle exec rake check
```

This builds the site and checks generated HTML for broken links and markup
issues.

## License

MIT License
