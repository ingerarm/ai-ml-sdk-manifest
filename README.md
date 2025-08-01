<!--
SPDX-FileCopyrightText: Copyright 2025 Arm Limited and/or its affiliates <open-source-office@arm.com>
SPDX-License-Identifier: Apache-2.0
-->

# ML SDK for Vulkan® Manifest

This repository contains the xml manifest describing how to checkout all the [ML
SDK for Vulkan®](https://github.com/arm/ai-ml-sdk-for-vulkan) software plus all
its dependencies.

## Setup

Install git-repo tool from <https://gerrit.googlesource.com/git-repo>

```bash
curl --create-dirs --output ~/.local/bin/repo https://storage.googleapis.com/git-repo-downloads/repo
chmod +x ~/.local/bin/repo
```

In order to perform the checkout, use the following commands:

```bash
repo init https://github.com/arm/ai-ml-sdk-manifest.git
repo sync -j $(nproc)
```

This will checkout all the ML SDK for Vulkan® software plus all the required
dependencies. The project structure will look like the following:

```text
ROOT_DIR/
    |_ sw/emulation-layer
    |_ sw/model-converter
    |_ sw/scenario-runner
    |_ sw/vgf-lib
    |_dependencies/
    |  |_ ...
    |  |_ ...
    |_docs/
    |  |_ ...
    |  |_ ...
    |_ ...
```

The sub-directory `sw` contains the ML SDK for Vulkan® components projects. The
sub-directory `dependencies` contains all the software dependencies necessary to
build the ML SDK for Vulkan®. The `docs` folder contains the ML SDK for Vulkan®
documentation.
