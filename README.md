# Github Actions `gcloud`

This is a repository that, on build, clones the
[`gcloud` action from the hub](https://github.com/actions-hub/gcloud), then build
the Docker image, then release it on the Docker Hub under
`patrickdappollonio/github-action-gcloud`.

It's a simple workflow process whose sole purpose is to reduce the time spent by
the Actions workflow, since actions pulled from a repository must be built
(unless they're from the `github.com/actions` organization).

You can use any of the examples on the [`gcloud` docs](https://github.com/actions-hub/gcloud)
just replace the `uses` directive from:

```
- name: My step name
  uses: actions-hub/gcloud@master
```

... to...

```
- name: My step name
  uses: docker://patrickdappollonio/github-action-gcloud:latest
```

Mapping-wise, `master` in the `actions-hub/gcloud` maps to `latest` tag in
Docker. The tagged versions are also available upon demand, but since my
personal requirements are just to build latest and the latest tag, I haven't
built the rest.
