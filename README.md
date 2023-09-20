# Bluestream

RSS feed generator for [Bluesky](https://bsky.app).

https://bluestream.deno.dev/

## Development

This works with [Deno](https://deno.land).

To run this locally, clone this repository and create `.env` file with the
following content:

```
BLUESKY_IDENTIFIER=your-handle
BLUESKY_PASSWORD=your-pass
```

After that, run `deno task dev` to start server.

## Docker/Podman Use
You can deploy this server using Docker or Podman using the included Containerfile to build the image.  Simply...

`git clone https://github.com/Nitrousoxide/bluestream.git`

navigate into the repo directory and 

`git checkout docker`

and either

`podman build -t bluestream:latest .`

or

`docker build -t bluestream:latest .`

You can also directly build from the repo without doing a clone with:

`podman build -t bluestream:latest https://github.com/Nitrousoxide/bluestream.git#docker`

or

`docker build -t bluestream:latest https://github.com/Nitrousoxide/bluestream.git#docker`

which will create a temporary clone of the repo for the build and then delete it when complete.

---

create an .env file with 
```
BLUESKY_IDENTIFIER=your-handle
BLUESKY_PASSWORD=your-pass
```

It is recommended you make this outside of the repo's directory (if you don't build directly from the repo in the cloud) so it won't get included in the container image in later builds.

and run:

`podman run -d -v /path/to/env/file/on/host/.env:/app/.env:z -p 8000:8000 bluestream:latest`

or

`docker run -d -v /path/to/env/file/on/host/.env:/app/.env -p 8000:8000 bluestream:latest`

You should be able navigate to whatever port you exposed on the host for the container to access the server.

## Author

[kawarimidoll](https://bsky.app/profile/did:plc:okalufxun5rpqzdrwf5bpu3d)

## License

MIT
