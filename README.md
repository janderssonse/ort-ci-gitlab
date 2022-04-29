<!--
SPDX-FileCopyrightText: 2022 Josef Andersson

SPDX-License-Identifier: CC0-1.0
-->

# ORT CI GitLab

GitLab templates for using the powerful [ORT (OSS Review Toolkit)](https://github.com/oss-review-toolkit/ort) to Analyze, Scan, Evaluate and Advise your code with ORT, with quite a lot of configuration options.

NOTE: TESTING THINGS; GIT HISTORY WILL BE RESET WHEN PROJECT IS "good enough" for an initial commit and pass the experimental phase, so if you clone it, dont expect to much, and dont use it "for real" yet, things will break

## Table of Contents

- [Usage](#usage)
- [Maintainers](#maintainers)
- [Contributing](#contributing)
- [License](#license)

## Usage

*Needs:*
- A pre built ORT CI Extensions image.(See [Extension Templates](#extension-templates)) for examples)
- A set GitLab Variable $ORT_CI_DOCKER_IMAGE pointing to above image.

After that, you can test in a repo:


```yaml
include: 
  - project: 'namespace/ort-ci-gitlab'
    file: '/ci-templates/.ort-scan-template.yml'


stages:
  - a stage...
  - ort-scan
  - another stage...
```
This should analyse the project and generate report artifacts in various formats.


For further configuration options, see [the variables configuration doc](https://github.com/janderssonse/ort-ci-base/blob/main/docs/variables.adoc) or [ci-templates/.ort-scan-template.yml](ci-templates/.ort-scan-template.yml), or check Run Pipeline to get an overview.

Run Pipeline Example Overview:  
<img src="https://user-images.githubusercontent.com/37870813/165504825-397424a9-0799-4fcf-ab8d-56e48c1fc6ca.png" width="700" height="454">

### Where can the results be found?

To the right of the finished Pipelines summary page, there is a dedicated section for artifacts. Here's a screenshot of something you might see:

<img src="https://user-images.githubusercontent.com/37870813/165504185-959f2c80-b646-4093-9ed5-be9b8a5f87b3.png" width="700" height="114">

### Extension templates

#### Build and promote a image with kaniko and crane on k8s

To-Do: Describe ci-templates/imagebuild/.ort-kaniko-build-template.yml

#### Posting a CycloneDXBom to [DependencyTrack](https://dependencytrack.org/)

To-Do: Describe ci-templates/integration/.post-bom-to-dependencytrack.yml

## Development

TO-DO.


### Project linters

The project is using a few hygiene linters:

- [MegaLinter](https://megalinter.github.io/latest/) - for shell, markdown etc check.
- [Repolinter](https://github.com/todogroup/repolinter) - for overall repostructre.
- [commitlint](https://github.com/conventional-changelog/commitlint) - for conventional commit check.
- [REUSE Compliance Check](https://github.com/fsfe/reuse-action) - for reuse specification compliance.

Before commiting a PR, please have run with this linters to avoid red checks. If forking on GitHub, you can adjust them to work for fork in the .github/workflow-files.

## Maintainers

[Josef Andersson](https://github.com/janderssonse).

## Contributing

ORT CI GitLab follows the [Contributor Covenant](http://contributor-covenant.org/version/1/3/0/) Code of Conduct.  
Please also see the [Contributor Guide](docs/CONTRIBUTING.adoc)

## License

The .ort-scan-template.yml is based on work [ort-gitlab-ci] done by the ORT-project and is

Copyright (C) 2020-2022 HERE Europe B.V.

ORT CI GitLab itself is is under

[MIT](LICENSE)

See .reuse/dep5 and file headers for further information.
Most other "scrap" files, textfiles etc are under CC0-1.0, essentially Public Domain.

## Credits

Thanks to the [ORT (OSS Review Toolkit) Project](https://github.com/oss-review-toolkit/ort), for developing such a powerful tool. It fills a void in SCA-toolspace.

## F.A.Q

* TO-DO
