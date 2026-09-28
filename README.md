# Ajay Singh's website

## Run locally

Prerequisites: Ruby and Bundler.

```sh
git clone https://github.com/ajaydeepsingh/ajaydeepsingh.github.io.git
cd ajaydeepsingh.github.io
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000) in your browser. Jekyll
regenerates the site when source files change. Use `rake preview` to start the
site with LiveReload instead.

## Validate changes

```sh
rake check
```

This builds the site and checks generated HTML for broken links and markup
issues.

## License

MIT License
