# kelly-mccarthy.com
The online home of @ShirleyTemper

## Build and deployment

Use Ruby 3.3:

```sh
bundle install
JEKYLL_ENV=production bundle exec jekyll build
bundle exec jekyll serve
```

GitHub Actions validates pull requests and deploys generated `_site` output from
`master`. Select **GitHub Actions** in Pages settings and configure
`kelly-mccarthy.com` as the custom domain. No persistent Ruby server is needed.
The contact form continues to submit directly to the existing Wufoo service.

The old `rake go` task targets a retired server deployment and must not be used.
Deployment configuration, development administration, and original source
photographs are not published. Revert a source commit and rerun the workflow to
roll back; retain the old origin until live acceptance checks pass.

For DNS cutover, use A records `185.199.108.153`, `185.199.109.153`,
`185.199.110.153`, and `185.199.111.153`. Use a `www` CNAME to
`aarongustafson.github.io`. Leave mail and other unrelated records alone; enable
HTTPS enforcement after GitHub provisions a valid certificate.
