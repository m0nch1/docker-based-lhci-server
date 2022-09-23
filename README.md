# docker-based-lhci-server

## Building Locally

```bash
docker image build -t lhci .
docker volume create lhci-data
docker container run --publish 9001:9001 --mount='source=lhci-data,target=/data' --detach lhci
open http://localhost:9001/app/
```

## clean up

```bash
docker container ls -a
docker container rm --volumes [CONTAINER ID]
```
