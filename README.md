Sound-Viewer-Tool
=================

This Python script uses the numpy and audiolab modules to generate waveform and spectrogram png images from a wav file. It is based on a script by Freesound.org.

v1.0 added option for window to use for the FFT

Requirements
------------

* Python 2.6 or 2.7 (not tested with 3)
* numpy 1.1+ (http://numpy.scipy.org/)
* libsndfile (http://www.mega-nerd.com/libsndfile/)
* audiolab module (http://www.ar.media.kyoto-u.ac.jp/members/david/softwares/audiolab/sphinx/index.html)

Installation
-------------

To install the required packages for in a current version of Ubuntu:
```bash
sudo apt-get install python-dev python-numpy python-setuptools libsndfile1-dev libasound2-dev python-imaging
```
Then, install the audiolab module.

If you have problems installing audiolab, try version 0.8:
```bash
wget http://pypi.python.org/packages/source/s/scikits.audiolab/scikits.audiolab-0.8.tar.gz
tar -xzf scikits.audiolab-0.8.tar.gz
cd scikits.audiolab-0.8
sudo python setup.py install
```

Usage
--------

```bash
svt.py [options] input-filename.wav
```

Options:
* --help : show this help message and exit
* -a OUTPUT_FILENAME_W, --waveout=OUTPUT_FILENAME_W : output waveform image (default input filename + _w.png)
* -o WAVEFILE, --wavefile=WAVEFILE : draw waveform image (yes:1, no: 0; default: no)
* -s OUTPUT_FILENAME_S, --specout=OUTPUT_FILENAME_S : output spectrogram image (default input filename + _s.png)
* -w IMAGE_WIDTH, --width=IMAGE_WIDTH : image width in pixels (default 500)
* -h IMAGE_HEIGHT, --height=IMAGE_HEIGHT : image height in pixels (default 170)
* -f FFT_SIZE, --fft=FFT_SIZE : fft size, power of 2 for increased performance (default 2048)
* -n WINDOW, --window=WINDOW : window to use for the FFT: bartlett, blackman, hanning, hamming, or kaiser (default hanning)
* -m F_MAX, --fmax=F_MAX : Maximum freq to draw, in Hz (default 22050)
* -i F_MIN, --fmin=F_MIN : Minimum freq to draw, in Hz (default 10)
* -p PALETTE, --palette=PALETTE : Which color palette to use to draw the spectrogram, 1 for black background and 2 for white background (default 1)
* -c CHANNEL, --channel=CHANNEL : Which channel to draw in a stereo file, 1 for left or 2 for right (default 1)
* -v, --version         display version information

