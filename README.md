# betadocs

# How to test

1. Install [DocFX](https://dotnet.github.io/docfx/index.html).
2. In the `betadocs` folder, start the terminal and type:
```
docfx --serve
```
3. By default the site is accessible via `http://localhost:8080`.

# How to convert

Every folder inside the `Wiki` contains one or more `.wiki` files. 
These are text files with the copy-paste content from the wiki.
Each `.wiki` is an input for the converter: `Patches\WikiConverter.vl`.

The converter takes a `.wiki` and generates `.md` files out of it, and also the `toc.yml` with the TOC for these `.md` files.
Images are downloaded into the `betadocs\img\`.
