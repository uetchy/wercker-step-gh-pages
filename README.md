# wercker-step-gh-pages

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
        basedir: public
        domain: randompaper.co
```
