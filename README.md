# HashiCorp Nomad Field Workshops
All HashiCorp field workshops focused on Nomad should be placed in this repository. Similar field workshop repositories exist for these HashiCorp solutions:
* [field-workshops-consul](https://github.com/hashicorp/field-workshops-consul)
* [field-workshops-terraform](https://github.com/hashicorp/field-workshops-terraform)
* [field-workshops-vault](https://github.com/hashicorp/field-workshops-terraform)

Additionally, field workshops focused on more than one HashiCorp solution can be found in the [field-workshops-hashistack](https://github.com/hashicorp/field-workshops-hashistack) repository.

## Slides
The slides for these workshops should be created using [Remark](https://remarkjs.com) and should be placed under the [docs/slides](./docs/slides) directory. This directory is organized by cloud and then by workshop.  If a workshop targets a single cloud, its slides should be placed in a directory under that cloud's directory ([aws](./docs/slides/aws), [azure](./docs/slides/azure), or [gcp](./docs/slides/gcp)). If a workshop can be used with multiple clouds, its slides should be placed in a directory under the [multi-cloud](./docs/slides/multi-cloud) directory.

Please do **NOT** place any slides or any other content directly inside the [docs](./docs) directory.

All of the slides will be available for students to view in their web browsers under https://hashicorp.github.io/field-workshops-nomad/slides.  Each workshop should give the full link to that workshop's slides in one of its first few slides.

When creating slides for a new workshop, you will need to do the following:
1. Create a new workshop directory under the appropriate directory as discussed above.
1. Create an `assets` directory under your new workshop's directory.
1. Copy all contents from the [docs/assets](./docs/assets) directory into the assets directory of your new workshop's directory.
1. Copy [docs/index.html](./docs/index.html) to your new workshop's directory.
1. If you want to create a single part slide show, then create a file in your directory called `index.md` and add all your slides to it.
1. You can copy content from [docs/index.md](./docs/index.md) to get started with a title slide and a few regular slides. Note that the speaker notes in that file have some useful pointers for creating Remark slide shows.
1. If you want to create a multi-part slide show, then do the following:
  1. Create multiple files such as `nomad-1.md`, `nomad-2.md`, and `nomad-3.md` with corresponding HTML files such as `nomad-1.html`, `nomad-2.html`, and `nomad-3.html`.
  1. In each of the HTML files, replace `index.md` with the name of the corresponding MD file in the `sourceURLs` list. For instance, use `nomad-1.md` in `nomad-1.html`.
  1. Replace `index.md` in the `sourceURLs` list of your workshop's copy of `index.html` with a comma-delimited list of your MD file names. So, with the 3 MD files listed above, you would specify `sourceURLs` like this:
  ```
  sourceUrls = [
    'nomad-1.md',
    'nomad-2.md',
    'nomad-3.md'
  ]
  ```

Whether you create a single-part or multi-part slide show, users will be able to access all of your slides with a URL like `https://hashicorp.github.io/field-workshops-nomad/slides/aws/nomad-oss/index.html`, but they can leave off `index.html`.

If you create a multi-part slide show, users will also be able to access each part of your slide show separately at URLs like these:
* https://hashicorp.github.io/field-workshops-nomad/slides/aws/nomad-oss/nomad-1.html
* https://hashicorp.github.io/field-workshops-nomad/slides/aws/nomad-oss/nomad-2.html

## Instructor Guides
The instructor guides for these workshops should be created as Markdown files and should be placed in the [instructor-guides](./instructor-guides) directory and have names like `<cloud>_<workshop_name>_INSTRUCTOR_GUIDE.md` where `<cloud>` is the cloud the workshop targets and `<workshop_name>` is the name of the workshop. But if the workshop is intended for use with multiple clouds, `<cloud>` should be omitted.

## Labs (Instruqt Tracks)
The labs for these workshops should be created using [Instruqt Tracks](https://instruqt.com/hashicorp).  Each track should be placed in its own directory directly underneath the [instruqt-tracks](./instruqt-tracks) directory. Doing this allows each track to be used by multiple workshops within this repository.
