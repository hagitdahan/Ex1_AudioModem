# Ex1_AudioModem

A simple audio modem project using OFDM over audio signals. This project is based on [romanz/amodem](https://github.com/romanz/amodem) and includes modifications for testing and experimenting with audio-to-audio digital communication.

## Features

- Send and receive messages using sound.
- Works between two computers using speakers and microphones.
- You can add noise and test how well it decodes under real-world conditions.
- Built with Python and designed to be modular and configurable.

## How to Run

### Requirements

- Python 3
- Required packages:
  - numpy
  - scipy
  - sounddevice
  - matplotlib
  - sox (for audio noise mixing)

To install the Python packages:

```bash
pip install -r requirements.txt
If sox is not installed, use:

```bash
sudo apt install sox
Sending a Message
To encode a message into an audio waveform:

```bash
echo "hello world" | amodem send > clean.wav
This will create a WAV file with the modulated message.

Receiving a Message
To decode the message from the waveform:

```bash
amodem recv < clean.wav
Adding Noise to the WAV
You can mix white noise into the audio file to simulate a noisy environment:

```bash
sox -m clean.wav "|sox -n -p synth whitenoise vol 0.03" noisy.wav
Then try receiving from the noisy file:

```bash
amodem recv < noisy.wav
Using with Microphone and Speakers
To run the modem live between two computers:

On the sender:

```bash
echo "hello world" | amodem send
This will play audio out loud.

On the receiver:

```bash
amodem recv
Make sure the microphone is recording and loopback is disabled.

#Configuration
The system uses the following configuration (in config.py):

Fs = 32000 (sampling frequency)

Tsym = 0.001 (symbol duration)

frequencies = [1000, 8000] Hz (carriers used)

silence_start = 0.5 (seconds of silence before)

silence_stop = 0.5 (seconds of silence after)

timeout = 60 seconds (for receiver to wait for signal)

#Credits
This project is based on the open-source amodem project by Roman Zeyde.

Modified and adapted by Hagit Dahan for experimentation and academic learning.
