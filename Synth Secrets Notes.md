# Synth Secrets Notes
## What's In A Sound?
#### Let's get plucking
You attenuate or remove harmonics from harmonically rich waveforms to create new sounds.
Static : create simple tones
Dynamic : filters, envelop generators, modulators

Pythagoras : plucking two similar strings stretched to the same tension gave a pleasing sound if their lengths were related by simple integers
	e.g. if one string was half the length of the other(1:2), the result sounded quite nice. (2:3) relationship would sound pleasant too.
	（弦长是整数关系时，听起来不错）

- Volume: amplitude 
- Pitch: how high or low a note is
- Harmonics(Overtones): whole number multiples of the fundamental frequency
- Standing wave: it does not run up and down the string like waves on the surface of the sea, but vibrates up and down.
- Waveform: a point at the center of the string moves in a simple, repeating pattern called a sine wave
- Fundamental frequency: the frequency with which the waveform completes one cycle

#### Harmonics and Octaves

Guitar strings: fixed at both ends. Standing waves(as a result of two waves) form between two nodes(two fixing points). Wavelength of the actual wave is ==twice== the distance between two nodes.

1st Harmonic(fundamental), f, wavelength = 2 L(fundamental)
2nd: 2f, wavelength = 2/2 L (1st octave)
3rd: 3f, wavelength = 2/3 L
4th: 4f, wavelength = 1/2L   (2nd octave)
5th: 5f, wavelength = 2/5L
6th: 6f, wavelength = 1/3L
7th: 7f, wavelength  = 2/7L
8th: 8f, wavelength = 1/4L   (3rd octave)
.......................
16th: 16f, wavelength = 1/8L (4th octave)

Harmonic number = 2^(Octave Number)

C->D->E->F->G->A->B->C 
from C->C is one octave above

Musical scale based on the C note tuned to 256Hz
Note      Frequency         Factor                                 Octave
C            256                    ==1(Harmonic)==
D            288                    1.125
E             320                    1.25
F             341                    1.33
G            384                    1.5(384 = 256 * 1.5)
A            427                    1.67(440A = A#)
B            480                    1.875
C            512                    ==2(Harmonic)==                         1st
D            576                    
E             640
F            682
G            768                    ==3(Harmonic)==
A            854
B            960
C            1024                  ==4(Harmonic)==                       2nd
D            1152
E             1280                 ==5(Harmonic)==
F             1364
G            1536                  ==6(Harmonic)==
A            1708
Bb          1792                  ==7(Harmonic)===
B            1920
C            2048                 ==8(Harmonic)==                        3rd

C G E are harmonics of C, so they can form a chord.

####  The Nature of A Sound
When you pluck a string, you don't hear the sound of a single harmonic. Any naturally occurring tone is ==a composite of many harmonics present in differing amounts==. At any given moment it is this ==combination== that ==determines the waveform== of the sound. Because of the number of harmonics present, this waveform will be much more ==convoluted== than the simple sine wave. You can only see a real complex waveform through a waveform editor.

Fourier Analysis: 
	Any ==periodic motion==, no matter how complex, could be broken down into its ==harmonic components==.
It also shows that given a set of harmonics, you can derice a unique waveform.
（周期性运动可拆成多个谐波组分，一组谐波可以组成应该独特波形）

Harmonics and waveform are 2 ways of expressing the same thing.
The natures of ==musical tones are defined== by the ==numbers and amplitudes of the harmonics contained within== them.

e.g. square wave/ sawtooth wave, this setting generates a particular set of harmonics withh amplitude of x, y and z.....

#### Subtractvive  Synthesis
Sawtooth wave:
	has a simple harmonic relationship:
		Every harmonic is present, and the amplitude of the nth harmonic is 1/n times that of the fundamental.( the harmonics taper off at higher and higher frequencies)

But if you truncate this series of harmonics. Remove all but the first 5 of them using filter, the spectrum of them are left still but the waveform is different. It sounds different. 

You have used a filter to subtract harmonics(harmonic series), thereby creating a new waveform, and thus a new sound.


## The Physics of Percussion
sawtooth wave -> basis of most of the orchestra's brass and string sections
square wave -> woody sounds such as clarinets
thinner-sounding pulse wave -> reedier tones of oboes and bassoons

sawtooth+pulse wave -> bass guitar
sawtooth -> lead guitar
A synthesiser that offers just 3 waveforms provides you with the raw materials to imitate most of the instruments.

non-harmonic oscillators. do not conform to the same set of rules
e.g. drums, timpani, many of the ethnic instruments

### A Multi-dimensional Problem
the stretched string, only have one ==primary dimension of its length==(for stretched string, pipe). Other factors as diameter, carved lump of resonating wood and metal, nature of its bore, material from which it is made.

Circular membrane, stretched with an equal tension at all points, and fixed at all points around its circumference.

### The Banged Drum
### Synthesizeing the un-synthesizable
generate the dense cluster of frequencies and ensure that they are not harmonically related.
Most synthesizers have a module that produces something similar. A perfect noise generator produces all audio frequencies simultaneously, close enough to provide a basis for many analogue drum sounds.

## Modifiers & Controllers
Most natural sounds have complex harmonic structures. these derive from the nature of the object making the sound.

### Modifying a sound
static/stationary sounds: unvarying tones(only produced by devices that generate a tone by outputting a fluctuating voltage that is passed through an amplifier and then onwards to a speaker, which converts the voltage into sound that you can hear)

Controller signal, gives predictable, reproducible results each time it is used.
Control Voltgae, CV. 
	For any given voltage applied at the amplifier's Controller input, the amplifier applies a defined gain to the signal/
	Voltage Controlled Amplifier(VCA)

### Envelopes
The loudness of the sound at any given time is defined using the CV.
Envelop generator.
ADSR(Attack/Decay/Sustain/Release)
	- Attack time determines the speed at which the sound reaches its maximum loudness
	- Decay time determines the speed at which the loudness drops until it reaches
	- the sustain level, the level the loudness maintains until
	- it decays to its final level in a time determined by the Release time
[[8ddeaf3c3d4b6583c21b7314457a36d.png]]
e.g. the organ has a rapid attack and maintains its full volume before dropping to silence when the player releases the key. The loudness contour is almost precisely rectangular. (organ envelope)
 the trombone, loudness usually peaks at the end of the attack stage before falling back to a lower, sustained level. When the player stops blowing, the sound rapidly falls back to silence.
 Thunderclap develops relatively slowly, no decay or sustain stages, once it has peaked, the loudness dies away slowly.

### Low Frequency Oscillators and Tremolo
Every harmonic sound has a fundamental frequency that is the simplest mode of vibration of the oscillator producing it. If this fundamental lies in the range of ==20Hz to 20kHz==, the sound is audible.
Swing the control of the volume, you introduce a new periodic effect the sound, that of tremolo(颤音). Apply an oscillator to the amplifier's volume.

Low Frequency Oscillators(LFO) generate low-frequency signals that control many of the synth's other functions. LFO produce oscillations in a range of frequencies lying between about ==0.1Hz and 20Hz==.

Tone Generator -> Amplifier
								^
								LFO sinewave

Tone Generator is a Signal Generator: produces the basic audio tone
Voltage Controlled Amplifier, an example of Modifier: changes the audio siganl in some way
LFO sineway generator is acting as a Controller: it is directing the signal-modifying action of the Modifier itself. 

LFO on powerful synths produce higher-frequency oscillations that stray well into the audio range/ offer a wider range of waveforms. You can use another Tone Generator to do so.
## Further with Filters
### Passive Filters
passive low-pass RC filter. resistors, capacitors and inductors are examples of passive components, while transistors and other amplifiers are not.
We can define the cutoff frequency of an RC filter simply by choosing appropriate values for the two passive components within it.

The relationship between what you put into a filter and what you get out is called the Transfer Function. This should encompass both the amplitude response and he phase response of the filter.

The amplitude response: the transfer function of our RC filter is very simple: for every doubling of the frequency above the cutoff frequency(Fc), the gain at the output is halved. Each successive halving of the gain is known as an attenuation of 6dB, the response is most commonly called a 6dB/octave filter.

The cutoff frequency of a passive low-pass filter does not define the frequency at which the filter starts to work; it is itself defined as that frequency at which the signal is already attenuated by 3dB. And, since an attenuation of 3dB is easily perceived by the human ear, this means that you are already significantly affecting the signal at the cutoff frequency






## Of Responses & Resonance
### Resonance
Almost without exception, all physical objects resonate.
==Resonant low-pass filter.== The filter still attenuates the frequencies far above the cutoff frequency, but ==a band around the cutoff is boosted==. The ==low frequencies are slightly attenuated==. The ==width of the resonant peak== is described by a parameter called its =='Q'==. If ==Q is low==, the ==peak is broad==
, but as Q increases, the peak in the filter response becomes more and more pronounced and creates dramatic tonal changes.

### Self-Oscillation
If you continue to increase Q, the resonance becomes so pronounced that the high and low frequencies disappear from the signal and another effect occurs: the filter begins to oscillate at its cutoff frequency. This is a powerful sonic effect, and a filter on the edge of self-oscillation will create a range of unnatural sounds unique to the electronic synthesizer.

### Synthesizer Heaven
Lots of advice in using resonant filter
The resonant low-pass filter defines the sound of subtractive synthesis.
- You can use a ==static filter== to ==emphasise certain frequencies==, creating character and making a sound ==stand out== in a complex mix
- You can use ==two or more static filters== to ==create formants== in a sound, and tailor these to imitate the characteristics of the human voice or traditional acoustics instruments.
- If you use a ==resonant filter with moderate Q== and make the ==cutoff freuqency track the pitch==, you can create a characteristic =='emphasized' quality== that remains tonally consistent as you play up and down the keyboard.
- ==Increase Q further==, you can enter a region where the filter is on the edge of ==self-oscillation==. It will then ring in sympathy with certain frequencies in the input signal. This creates a distinctive distortion that can be very effective for 'off-the-wall' sounds.
- Increase ==Q to its maximum==, the filter will become a ==sinewave generator== in its own right. If the ==filter tracks the keyboard CV== accurately, you can then play it as if it were an ==extra oscillator==. You can even ==add vibrato using a filter modulation CV==. In theory, ==no input signal is passed== at this point, but ==few filters completely remove all the signal==. And the result is a ==tortured sound== that has extensive uses in modern music.

## Envelopes, Gates & Triggers
