<!-- .slide: class="center dark" -->
<!-- .slide: data-background="../img/background/hands-on.jpg" -->
# Versioning Releases

<div class="label">Hands-on Time</div>


<!-- .slide: class="dark" -->
<div class="eyebrow">Section 8</div>
<div class="label">Hands-on Time</div>

## Semantic Versioning

### MAJOR.MINOR.PATCH

* *Patch* is incremented when we release bug fixes
* *Minor* is incremented when new functionality is added in a backward-compatible manner
* *Major* is incremented when changes are not backward compatible


<!-- .slide: class="dark" -->
<div class="eyebrow">Section 8</div>
<div class="label">Hands-on Time</div>

## Versioning From Pipelines

```bash
jx get applications --env staging

VERSION=2.0.0

echo "VERSION := $VERSION" | tee -a Makefile

git add .

git commit -m "Finally 2.0.0"

git push
```


<!-- .slide: class="dark" -->
<div class="eyebrow">Section 8</div>
<div class="label">Hands-on Time</div>

## Versioning From Pipelines

```bash
jx get activities --filter go-demo-6/master --watch

jx get activities --filter environment-jx-rocks-staging/master --watch

jx get applications --env staging

GH_USER=[...]

open "https://github.com/$GH_USER/go-demo-6/releases"
```


<!-- .slide: class="dark" -->
<div class="eyebrow">Section 8</div>
<div class="label">Hands-on Time</div>

## Versioning From Pipelines

```bash
echo "A silly change" | tee README.md

git add . && git commit -m "A silly change" && git push

jx get activity --filter go-demo-6/master --watch

jx get activities --filter environment-jx-rocks-staging/master --watch

jx get applications --env staging

cd ..
```
