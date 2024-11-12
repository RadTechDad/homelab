<a id="readme-top"></a>

<div align="center">

# 🏔️ Alpine Base Image

<img src="https://avatars.githubusercontent.com/u/7600810" alt="Alpine Linux Logo" width="160"/>

</div>

<br />
<hr>
<br />


A custom Alpine Linux image that I use for my other Docker images.


<br /><br />
## ✨ Installed Packages

- `shadow` - for changing the UID/GID of a user
- `tzdata` - for setting the timezone


<br /><br />
## 🚀 Usage

To use this image as a base for your own Dockerfile:

```
FROM radtechdad/alpine:latest
```


<br /><br />
## 🏗️ Build Arguments

The following build arguments can be used when building this image:

| Argument | Default Value | 
|----------|---------------|
| ALPINE_VERSION | "3.20" | 
| SHADOW_VERSION | "4.15.1-r0" |
| TZDATA_VERSION | "2024b-r0" |
| TZ | "America/Los_Angeles" |


<br /><br />
## 🌍 Environment Variables

| Variable | Default Value | Description |
|----------|---------------|-------------|
| TZ | Set by TZ build arg | Timezone of the container |


<br /><br />
## 🛠️ Customizing the Image

This image supports the `linux/amd64` and `linux/arm64` platforms. If you need it to support another platform, you must build it yourself.

For more information on multi-platform builds, check out these references:
 - https://docs.docker.com/build/building/multi-platform/
 - https://www.docker.com/blog/how-to-rapidly-build-multi-architecture-images-with-buildx/

You can use the following command, just replace `<repo>/<package>:<version>` with whatever `<repo>/<package>:<version>` you want to use. Also make sure you replace `<timezone>` with your appropriate timezone according to the tz identifier listed [here](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

To create and save the image to your local docker:
```
docker buildx build -t <repo>/<package>:<version> --build-arg TZ="<timezone>" --build-arg BUILD_DATE=$(date -u +"%Y-%m-%dT%H:%M:%SZ") --platform=linux/amd64,linux/arm64 --builder <name_of_custom_builder> --load .
```

To create and save the image to Docker Hub:
```
docker buildx build -t <repo>/<package>:<version> --build-arg TZ="<timezone>" --build-arg BUILD_DATE=$(date -u +"%Y-%m-%dT%H:%M:%SZ") --platform=linux/amd64,linux/arm64 --builder <name_of_custom_builder> --push .
```
<br />

As of November 1, 2024, here is a compatability list of shadow and tzdata for different verions of Alpine:

| Package | Alpine 3.20 | Alpine 3.19 | Alpine 3.18 | Alpine 3.17 | Alpine 3.16 | Alpine 3.15 |
|---------|-------------|-------------|-------------|-------------|-------------|-------------|
| shadow | 4.15.1-r0 | 4.14.2-r0 | 4.13-r4 | 4.13-r0 | 4.10-r3 | 4.8.1-r1 |
| tzdata | 2024b-r0 | 2024a-r0 | 2024-r0 | 2024a-r0 | 2024a-r0 | 2023c-r0 |

<br />
To check the compatability of other software, visit https://pkgs.alpinelinux.org/packages


<br /><br />
## 🏃‍♂️ Running the Container

To run a container using this image:

```
docker run -it --rm radtechdad/alpine:latest
```


<br /><br />
## 🔒 Security

- The container runs as a non-root user 'guest'
- Minimal set of installed packages to reduce attack surface


<br /><br />
## 🔧 Maintenance

This image is regularly updated to include the latest security patches and updates from Alpine Linux.


<br /><br />
## 📜 License

This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).


<br /><br />
## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.


<br /><br />
## 🆘 Support

For support, please open an issue on the GitHub repository.
