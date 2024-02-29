### Testing GitHub Packages

Create env vars
- GH_USERNAME
- GH_TOKEN
- GH_IMAGE_NAME
- GH_VER

```sh
export GH_USERNAME='github-username'
export GH_TOKEN='PAT'
export GH_IMAGE_NAME='hello-world'
export GH_VER='1.0.1'

echo $GH_TOKEN | docker login ghcr.io -u $GH_USERNAME --password-stdin`
docker tag $GH_IMAGE_NAME:latest ghcr.io/$GH_USERNAME/$GH_IMAGE_NAME:$GH_VER
docker push ghcr.io/$GH_USERNAME/$GH_IMAGE_NAME:$GH_VER
```