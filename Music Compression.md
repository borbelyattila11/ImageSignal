# Music Compression
Music compression refers to reducing the amount of data required to store or transmit audio signals while preserving much of the perceived quality as possible.

## MPEG (Moving Picture Experts Group)
MPEG is a working group that develops standards for audio and video compression. Most common standards for audio:
1. MPEG-1 Audio Layer III (MP3): Lossy audio compression format designed to reduce file size while maintaining audio quality.
2. MPEG-4: More advanced standard that includes AAC (Advanced Audio Coding), which offers better quality at similiar bitrates compared to MP3.

### MP3
Achieves significant reduction in file size by discarding audio data that is considered less perceptible to the human hearing. Allows variable bitrates, ranging 32 kpbs to 320 kpbs providing trade-off between file size and quality. Higher bitrates generally yield better audio quality at the cost of larger file sizes. Efficient in compressing audio, reducing typical CD-quality 16bit 44.1kHz stereo audio track to around one-tenth of its original size. Uses a psychoacoustic model to remove sounds that are less audible to the human ear, such as quiet sounds that occur simultaneously with louder sounds or high-frequency components that are difficult for the human ear to perceive.

## Sound as a Physical Phenomenon
Sound is a physical phenomenon that involves the propagation of mechanical waves through a medium. It is created by vibrating objects that generate pressure waves in the surrounding medium, which are detected by our ears as sound.
- **Vibrations:** When an object vibrates, it causes the particles of the surrounding medium to oscillate.
- **Sound Waves:** Sound travels as longitudal waves, meaning displacement of particles occurs in the same direction as the wave. As the wave propagates, particles in the medium move back and forth along the direction of wave travel.

### Longitudal waves (characteristics)
- **Amplitude:** The height of the wave, which corresponds to the intensity or loudness of the sound, higher amplitude means louder sound.
- **Frequency:** The number of oscillations per second, measured in **Hertz** (Hz), higher frequency means a higher-pitched sound.
- **Wavelength:** The distance between two consecutive points in phase, shorter wavelengths correspond to higher frequencies.
- **Speed:** The speed at which sound waves travel depends on the medium, like sound travels faster in water than in air.

### Human Perception of Sound
When sound waves reach the ear, they cause vibrations in the eardrum, which are transmitted to inner ear and converted to electrical signals. These signals are interpreted by the brain as different sounds. The human eaer can generally hear sounds in the frequency range of 20Hz to 20kHz (this range decreases with age).

## The Psyhoacoustic Model
The psychoacoustic model is central to lossy audio compression and leverages the limitations of human hearing to remove audio data that is less perceptible.

### Hearing Threshold
Humans can only hear sounds within a frequency range of about [20Hz, 20kHZ], sounds below the hearing threshold are inaudible and can be discarded.

### Frequency Masking
Louder sounds in a particular frequency range can make softer sounds in nearby frequencies inaudible to the human ear. So Frequency Masking modifies or enhances certain aspects of an audio signal by selectively manipulating its frequency components. Involves blocking or attenuating specific frequency ranges in the signal, effectively "masking" parts of the audio spectrum.

So the audio signal is converted from time domain to the frequency domain using Fourier Transform (Short-Time Fourier Transform), because in the time domain the sound is represented as a waveform, making it difficult to isolate specific frequency components. In the frequency domain based on the psychoacoustic models we can mask out or suppress given frequencies making inaudible or less important.

### Temporal Masking

### The Bark Scale and Critical Bands

### Steps of MPEG compression
