# General

ffmpeg - everything audio and video related

- `brew install ffmpeg`
- https://ffmpeg.org/

# Python

Miniconda - miniature installation of Anaconda that only includes conda, Python and some useful packages

- `brew install --cask miniconda`
- https://www.anaconda.com/docs/getting-started/miniconda/main

## Packages

uv - replacement for pip

- `brew install uv`
- https://github.com/astral-sh/uv

pretty-errors - make python errors pretty

- https://pypi.org/project/pretty-errors/
- https://github.com/onelivesleft/PrettyErrors
- `python -m pip install pretty_errors`
- `python -m pretty_errors`
  - install into miniconda3 folder
  - then use default file to install to

### Create a new conda environment called media

Will be used to use 2 pip packages to download media.

- `conda create --name media`
- `conda activate media`
- `conda install python`
- `uv pip install yt-dlp`
- `uv pip install spotdl`

If there is a TooManyRedirects error for spot-dl, see https://github.com/spotDL/spotify-downloader/issues/2458#issuecomment-3206244696 for help.

# JavaScript / TypeScript

## Node Version Manager (NVM)

- https://github.com/nvm-sh/nvm
- `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash`
