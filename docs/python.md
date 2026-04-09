# Python

To install python 3.14 in this example, install [uv](https://docs.astral.sh/uv/) then

```bash
uv python install 3.14
```

To install a tool distributed across PyPI such as [yt-dlp](https://github.com/yt-dlp/yt-dlp) or [glances](https://github.com/nicolargo/glances). This tool will be added into the PATH on a dedicated isolated environment. Example with tool glances.

```bash
uv tool install glances
```

To run a tool without installing it, run

```bash
uvx glances
```
