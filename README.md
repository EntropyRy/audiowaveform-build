# Docker Container to Build Audio Waveform Image Generator

**audiowaveform** is a C++ command-line application that generates waveform data
from either MP3, WAV, FLAC, Ogg Vorbis, or Opus format audio files. Waveform data can
be used to produce a visual rendering of the audio, similar in appearance to
audio editing applications. The code for the application binary can be found [here](https://github.com/bbc/audiowaveform).
Compiled for 386, amd64, arm/v6, arm/v7, arm64, ppc64le, s390x.

![Example Waveform](https://raw.githubusercontent.com/bbc/audiowaveform/master/doc/example.png "Example Waveform")

Waveform data files are saved in either binary format (.dat) or JSON (.json).
Given an input waveform data file, **audiowaveform** can also render the audio
waveform as a PNG image at a given time offset and zoom level.

This is modified from
[audiowaveform-docker](https://github.com/realies/audiowaveform-docker/)
to compile audiowaveform as a completely statically linked executable
that can be run anywhere without docker or any other dependencies.

## Typical Usage

```
git submodule init
git submodule update
docker build -t audiowaveform-build .
docker run --rm -v "`pwd`/audiowaveform:/audiowaveform" audiowaveform-build
```

The executable should appear at `audiowaveform/build/audiowaveform`.
Copy it from there to where you need it.
