# wercker-step-gh-pages

Deploy to Github Pages with Wercker.

## Usage

```yaml
box: wercker/default
build:
  steps:
    - arjen/hugo-build:
        theme: hugo-paper
        flags: --buildDrafts=false
deploy:
  steps:
    - uetchy/gh-pages:
        token: $GITHUB_TOKEN
        repo: randompaper/randompaper.github.io
        path: public
        domain: randompaper.co
```

## Options

|name|description|optional|
|----|-----------|--------|
|token|Github token|false|
|repo|Destination repository|true/false|
|domain|Custom domain|true|
|path|root dir|true|
