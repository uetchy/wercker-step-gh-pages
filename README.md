# wercker-step-gh-pages

Deploy to Github Pages with Wercker.

## Usage

Put __uetchy/gh-pages__ step into your wercker.yml.

Please make sure your wercker-box contains 'git' command.

### Example(Docker-stack)

```yaml
box: debian
build:
  steps:
    - arjen/hugo-build:
        version: "0.15"
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

Then set your Github [Personal Access Token](https://github.com/settings/tokens)  as environment variables.

![Deployment variables](http://randompaper.co.s3.amazonaws.com/github.com/uetchy/wercker-step-gh-pages/deploy-variables.png)

Finally, you will be able to deploy to Github Pages.

## Options

|name|description|optional|
|----|-----------|--------|
|token|Github token|false|
|repo|Destination repository|true/false|
|domain|Custom domain|true|
|path|Root dir|true|
