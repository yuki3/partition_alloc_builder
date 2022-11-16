# partition_alloc_builder
Build the PartitionAlloc library without checking out the entire Chromium repository.

## Prerequisites

You need to have
[depot_tools](https://chromium.googlesource.com/chromium/tools/depot_tools.git)
set up on your local environment (including PATH).

## Build steps

1. git clone https://github.com/yuki3/partition_alloc_builder.git
1. gclient config https://github.com/yuki3/partition_alloc_builder.git
1. cd partition_alloc_builder/
1. gclient sync
1. gn args out/Default
1. autoninja -C out/Default

Then, //out/Default/libpartition_alloc.so is built (on GNU/Linux).

## Known problems

This project depends on the _latest_ version of dependencies, so the resulting objects are not stable (you cannot reproduce the exactly-same resulting objects). Everytime you sync (you fetch the dependencies), the resulting objects may change.
