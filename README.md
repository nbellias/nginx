# Another nginx clone with a specific configuration

## Commands
docker build . -t nbellias/nginx

docker run -d -p 12345:80 -v D:\DATA\Volumes\nginx:/usr/share/nginx/html --name nginx nbellias/nginx

docker login 
docker buildx create --name buildx-multi-arch          
docker buildx use buildx-multi-arch      
docker buildx build --no-cache --platform linux/amd64,linux/arm64/v8 . -t nbellias/cmatrix --push
docker buildx build --no-cache --platform linux/386,linux/amd64,linux/arm64/v8,linux/arm/v7,linux/ppc64le,linux/s390x  . -t nbellias/nginx --push

docker run --rm -it --platform linux/ppc64le  nbellias/nginx -a -r

docker rmi nbellias/nginx