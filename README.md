# Notes from HorseyofCoursey
Once upon a time there was a kit that was a collaboration between Google and Raspberry Pi that came with a convenient board https://pinout.xyz/pinout/aiy_voice_bonnet a "do-it-yourself intelligent speaker".

They have been paper weights for years as updates to OS's left this board behind. The most recent progress was from viraniac to make it work in Bulleye, but it didn't have full functionality with the microphone (someone please correct me if I'm wrong about that).

So I forked viraniac's progress and continued to work on it to make it work in Trixie.

What it took to make it work in Trixie:
* 2 API renames in the sound driver and rt5645 codec
* 1 probe signature fix in aiy-io-i2c
* 3 platform driver remove() return type fixes across gpio, pwm, and adc
* 1 missing header in gpio driver
* Full pwm_chip API rewrite for the new 6.12 ownership model
* 1 device tree compatible string fix for BCM2837
* Makefiles converted to out-of-tree obj-m style

There were other kit versions that had different hats but this is the only one I have. If anyone want to mail me there old hats to the USA I could try to get other versions to work too.

# AIY Projects

This repository contains an easy-to-use Python API for the [AIY Vision Kit][aiy-vision]
and [AIY Voice Kit][aiy-voice]. The code for all AIY kits is in the `aiyprojects` branch,
and is included in images starting with `aiyprojects-2017-12-18.img`.
The previous `voicekit` branch contains code just for the Voice Kit, and the
`master` branch contains the original deprecated `Voice Recognizer` demo.

## Documentation

If you're just getting started with the Vision or Voice kit, see the
assembly guide and other maker guides at [aiyprojects.withgoogle.com].

If you just need the Python API reference, see [aiyprojects.readthedocs.io].
Also have a look at the [example code][aiy-github-examples].

If you want to flash the latest AIY system image or install AIY packages on an existing
Raspbian system, read the [system updates guide][HACKING.md].

## Releases

* [SD card image downloads][downloads]
* [Change log][changelog]

You can also build an SD card image yourself using [AIY Projects Tools][aiy-projects-tools].

## Bugs & Support

If you've found a bug, please [review the known issues and report a new one][aiy-github-issues].

If you've fixed a bug yourself, please send us a pull request!
For details, read [CONTRIBUTING.md].

If you're having trouble assembling your kit or running the demos, try the following links:

* [AIY Help docs][help-docs]
* [AIY Forums][aiy-forums]
* [AIY Stack Overflow][aiy-stack-overflow]
* [AIY GitHub Issues][aiy-github-issues]
* support-aiyprojects@google.com

##

<p align="center">
  <img width="15%" src="https://aiyprojects.withgoogle.com/static/images/icons/aiy-circular-logo.svg">
</p>

[HACKING.md]: HACKING.md
[CONTRIBUTING.md]: CONTRIBUTING.md
[downloads]: https://github.com/google/aiyprojects-raspbian/releases
[changelog]: CHANGES.md

[aiy-projects-tools]: https://github.com/google/aiyprojects-raspbian-tools
[aiyprojects.withgoogle.com]: https://aiyprojects.withgoogle.com
[aiyprojects.readthedocs.io]: https://aiyprojects.readthedocs.io
[aiy-vision]: https://aiyprojects.withgoogle.com/vision/
[aiy-voice]: https://aiyprojects.withgoogle.com/voice/

[help-docs]: https://aiyprojects.withgoogle.com/help
[aiy-forums]: https://www.raspberrypi.org/forums/viewforum.php?f=114
[aiy-stack-overflow]: https://stackoverflow.com/questions/tagged/google-aiy
[aiy-github-issues]: https://github.com/viraniac/aiyprojects-raspbian/issues
[aiy-github-examples]: https://github.com/viraniac/aiyprojects-raspbian/tree/aiyprojects/src/examples
