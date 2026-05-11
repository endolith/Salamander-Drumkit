# StudioRack publishing

[StudioRack](https://github.com/studiorack/studiorack) discovers packages via repos tagged [`studiorack-plugin`](https://github.com/topics/studiorack-plugin) and GitHub **Releases** that include a release asset named exactly **`plugins.json`**. The indexer fetches:

`https://github.com/<owner>/<repo>/releases/download/<tag>/plugins.json`

The repository root has a [`plugins.json`](plugins.json) template. Copy it into the release and set **`version`**, **`date`**, and each **`files.*.size`** to the byte sizes GitHub shows for that release’s assets.

## Release assets

1. **`plugins.json`** — same shape as the repo file. `files.linux`, `files.mac`, and `files.win` must name a **`.zip`** on the same release (one zip reused for all three is fine for SFZ + WAV).
2. **`SalamanderDrumkit.zip`** — SFZ files from this repo plus the `.wav` tree from the [Internet Archive](https://archive.org/details/SalamanderDrumkit) (or another licensed copy). Layout inside the zip must match SFZ paths.
3. **`SalamanderDrumkit.jpg`** — small cover or kit photo (JPEG is what their tooling recommends for previews).
4. **`SalamanderDrumkit.flac`** — short audio preview (FLAC recommended).

Add the **`studiorack-plugin`** topic on GitHub (About → Topics). [studiorack-registry](https://github.com/studiorack/studiorack-registry) merges `plugins.json` with release assets; indexing runs on a daily schedule.

## GitHub license

The registry rejects `license: other`. Set a repository license GitHub exposes as a known SPDX id (see [choosealicense.com](https://choosealicense.com/appendix/)) so the API is not `null` / other. Original sample terms remain as in `readme.md` (Original README).

## YAML vs `plugins.json`

The [Open Audio Stack registry](https://github.com/open-audio-stack/open-audio-stack-registry) uses YAML for packages it hosts. StudioRack’s **GitHub** flow expects **`plugins.json` attached to the release**, not a separate YAML file in the repo for that crawler.
