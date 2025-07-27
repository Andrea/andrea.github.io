
# Blog


This is a jekyll blog


## Development setup

Uses
* https://github.com/mmistakes/minimal-mistakes



* To run locally with docker use https://github.com/BretFisher/jekyll-serve for example

To serve

```bash
docker run -p 4000:4000 -v $(pwd):/site bretfisher/jekyll-serve
```

To install things

```bash
docker run -v $(pwd):/site bretfisher/jekyll-serve bundle install
```