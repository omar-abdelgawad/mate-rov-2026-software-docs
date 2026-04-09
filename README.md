# mate-rov-2026-software-docs

This repository is dedicated to document all different kinds of stuff in our work from github-usernames to important data-links. You can think of it as the root node.

## Our Team:

- [Omar Abdelgawad](https://github.com/omar-abdelgawad) -> supervisor
- [Ahmed Ismail](https://github.com/ahmed-Ismail-elbrolosy) -> lead
- [Motaz Elsaman](https://github.com/motazsaman214)
- [Marwan](https://github.com/MarwanULQ)
- [Nadine Nabih](https://github.com/NadineNabih)
- [Seif Eldeen Mostafa](https://github.com/Vseif1011)
- [Abdelrhman Elziat](https://github.com/abdelrahman120240010-cmyk)
- [Ahmed Anwar](https://github.com/0xanwar)
- [Mahmoud Abualfadl](https://github.com/MahmoudAbualfadl)

## Gdrive link:

This link contains all big data that we need to share for training, testing, or just general documentation but is too big to be added to github. The link should be shared as read-only for anyone.

https://drive.google.com/drive/folders/1ywYO08Prxha8mJFXOx24Lt_mlt3WUB-b?usp=sharing

Tip: the link can be chaotic and is not meant for you to navigate it looking for something. you should probably know exactly what you are looking for before opening it.

## ROV software system docs

This link has a description of the software system required for submission in the competition.

https://docs.google.com/document/d/1D1Ii5b2isC0X4MzS_ErAI6QmNewqK_K6YoDMUKLM9jA/edit?tab=t.0

TODO: this link requires review and updates from last year.

## Other Important links:

- [competition manual](https://20693798.fs1.hubspotusercontent-na1.net/hubfs/20693798/2026/Manuals/2026%20EXPLORER%20Manual_updated_12_17_Cover.pdf)
- [competition website](https://materovcompetition.org/2026)
- [tasks preview](https://www.youtube.com/watch?v=rRYs0vXm_m0)

## Repositories

We decided to develop each subtask in a repository mainly as a library. Here are the list of subtasks and their respective repos:

| Task                                                         | Repository |
|:--------------------------------------------------------------:|:-----------:|
| Measure iceberg depth                                        | [mate-rov-2026-iceberg-depth](https://github.com/MarwanULQ/mate-rov-2026-iceberg-depth) |
| 3D Model                                                     | [3dws](https://github.com/ahmed-Ismail-elbrolosy/3dws) |
| Threat Level determination through Information Sheet         | [mate-rov-2026-information-sheet-problem](https://github.com/ejustroboticsclub/mate-rov-2026-information-sheet-problem) |
| Crab Detection                                               | [mate-rov-2026-crab-detection](https://github.com/ejustroboticsclub/mate-rov-2026-crab-detection) |
| GUI                                                          | TODO |
| eDNA utils                                                   | TODO (might be inside GUI repo) |

## Development practices

In general, each task will be handled by its respective subteam. However, general conventions/development tools are preferred. For example:

- All projects require a pyproject.toml file and should be handled by uv as a dependency manager. this circumvents a lot of dependency-management headache during deployment.
- Always Freeze your dependecies to a specific version. This is the default behaviour for "uv add <package>" command btw.
- Document all important commands for the project. This is done favorably using .PHONY recipes in a Makefile or a justfile or even a txt file. Any document for how to run the project is highly encouraged especially if the project contains more than one script or entry point. for example the crab-detection repo might have a script for training, one for testing, and another for a ros node.
- The implementations will mostly be implemented as libraries and the ros nodes will all be written in the same repository for th entire workspace. The one responsible for the workspace should use [pixi](https://pixi.prefix.dev/latest/tutorials/ros2/) to make sure the build is reproducible.

