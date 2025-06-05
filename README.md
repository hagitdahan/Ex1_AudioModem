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

bash
Copy
Edit
sudo apt install sox
Sending a Message
To encode a message into an audio waveform:

bash
Copy
Edit
echo "hello world" | amodem send > clean.wav
This will create a WAV file with the modulated message.

Receiving a Message
To decode the message from the waveform:

bash
Copy
Edit
amodem recv < clean.wav
Adding Noise to the WAV
You can mix white noise into the audio file to simulate a noisy environment:

bash
Copy
Edit
sox -m clean.wav "|sox -n -p synth whitenoise vol 0.03" noisy.wav
Then try receiving from the noisy file:

bash
Copy
Edit
amodem recv < noisy.wav
Using with Microphone and Speakers
To run the modem live between two computers:

On the sender:

bash
Copy
Edit
echo "hello world" | amodem send
This will play audio out loud.

On the receiver:

bash
Copy
Edit
amodem recv
Make sure the microphone is recording and loopback is disabled.

Configuration
The system uses the following configuration (in config.py):

Fs = 32000 (sampling frequency)

Tsym = 0.001 (symbol duration)

frequencies = [1000, 8000] Hz (carriers used)

silence_start = 0.5 (seconds of silence before)

silence_stop = 0.5 (seconds of silence after)

timeout = 60 seconds (for receiver to wait for signal)

Credits
This project is based on the open-source amodem project by Roman Zeyde.

Modified and adapted by Hagit Dahan for experimentation and academic learning.

scss
Copy
Edit

אם את רוצה גם גרסה בעברית או תוספות נוספות (למשל תמונה, דיאגרמה, או טיפים לשימוש), רק תגידי 😊






You said:
אני רוצה את הקבץ המלא באנגלית כמו שהיה רק סדר את הנראות שאדבק


ChatGPT said:
בוודאי! הנה הקובץ שלך באנגלית, מסודר ומעוצב נכון עם כותרות Markdown תקינות, כך שתוכלי להעתיק ולהדביק אותו ל־README:

markdown
Copy
Edit
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

bash
Copy
Edit
sudo apt install sox
Sending a Message
To encode a message into an audio waveform:

bash
Copy
Edit
echo "hello world" | amodem send > clean.wav
This will create a WAV file with the modulated message.

Receiving a Message
To decode the message from the waveform:

bash
Copy
Edit
amodem recv < clean.wav
Adding Noise to the WAV
You can mix white noise into the audio file to simulate a noisy environment:

bash
Copy
Edit
sox -m clean.wav "|sox -n -p synth whitenoise vol 0.03" noisy.wav
Then try receiving from the noisy file:

bash
Copy
Edit
amodem recv < noisy.wav
Using with Microphone and Speakers
To run the modem live between two computers:

On the sender:

bash
Copy
Edit
echo "hello world" | amodem send
This will play audio out loud.

On the receiver:

bash
Copy
Edit
amodem recv
Make sure the microphone is recording and loopback is disabled.

Configuration
The system uses the following configuration (in config.py):

Fs = 32000 (sampling frequency)

Tsym = 0.001 (symbol duration)

frequencies = [1000, 8000] Hz (carriers used)

silence_start = 0.5 (seconds of silence before)

silence_stop = 0.5 (seconds of silence after)

timeout = 60 seconds (for receiver to wait for signal)

Credits
This project is based on the open-source amodem project by Roman Zeyde.

Modified and adapted by Hagit Dahan for experimentation and academic learning.
