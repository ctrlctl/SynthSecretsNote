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
（波形是谐波不同组合的结果）

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





！！！
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
Why some synths not only sound different, but feel so different to play.
Two most revered monosynths of the early '70s -- the ==Minimoog and the ARP Odyssey== -- can respond so differently when you play them.

### About Envelopes
analogue envelope generators are all ADSRs?
Attack time : how percussive a sound is
Decay time : how long the sound takes to fall to the 
Sustain level : after the initial accent
Release time : the time the note takes to die away when you release the key

There are ==many other envelope shapes==.
Many ==envelopes== are themselves ==modified by== other ==controls like Amount and Invert==.

### Envelopes & Contours
#### Common waveforms are symmetrical and repeated
Such as sine or square wave, they have nice symmetrical shapes that repeat time after time.
If they didn't repeat, you wouldn't be able to perceive the pitch of the sound, at best you would hear a click.

The common sawtooth and pulse waveforms(can be symmetrical but not necessarily) also repeat.

#### A simple waveform neither symmetrical nor repeated
apply the output of this circuit to another part of the synthesiser such as a voltage controlled amplifier.
If the amplifier's gain at any intsant is proportional to the voltage shown, the waveform becomes the loudness contour of the sound.
If the destination is a voltage controlled low-pass filter(a VCF). the curve shown becomes the brightness contour of the sound. 
The contour can be used a output from an Envelope Generator.

#### Envelope
definition : the ==graph of the way== a ==parameter changes over time== is a visual representation of its envelope.
But in a typical synthesiser, you can change the value of a parameter using any number of modifiers at any given moment. The total envelope may be the sum of the simultaneous actions of numerous devices.
So, what we usually call an ==envelope generato==r may be only ==one contributor to the true envelope== of a given parameter.

The earliest synthesizer manufacturers called them 'Transient Generators'.

The first stage is the Attack of the transient, the second stage is Decay. The figure represents a functional =='AD' transient generator==. Apply ==2 dissimilar AD contours== to a single modifier such as a VCA or VCF. The envelope generated by the summation of the two contours is a ==more complex 4-stage contour==. It's one you cannot obtain from a 4-stage ADSR envelope generator.

### Triggers & Gates
Above is what happens when you apply more than one transient to a single parameter at any given time. Next is about what happens when we play more than one note sequentially.
Most analogue monosynths are controlled by keyboards. Many of these generate three signals every time you press a key.
1. ==Pitch CV== : it helps to determine the pitch of the sound produced for any given key.
2. ==The Trigger Pulse== : a pulse of short duration that at the exact moment you press a key, can trigger the actions of devices such as transient generators.
3. ==The Gate Signal== : the Gate's leading edge tells other parts of the synth that you have pressed a key. However the Gate ==remains open== for the whole time that you ==depress== the key. It can tell the rest of the synth the exact ==moment that you release== the key. 

Although a Trigger will initiate a transient generator, it's the Gate that tells the synth to continue developing the contour until the key is released. Without a Gate, all you would hear would be a short 'blip' at the start of the sound, but nothing thereafter.

#### Gate
3-stage transient generator uses the timing information in the ==Gate== signal to complete the ==Attack== stage and then ==maintain the maximum voltage== for the entie duration that the key is presses. This is a Trapezoid transient generator.(EMS VCS3)

Next level of complexity is 4-stage ADSR. But simple envelope shape assumes every transient exists in isolation, and theat every contour has the time  to run to its course before you initiate the next.

#### Trigger
When playing a heavily contoured solo sound with an instantaneous(Attack = 0) percussive spike of loudness and brightness at the start of each note. (The spike is created by applying a pair of contours to the VCF and VCA) When playing at ==higher speeds==, the Odyssey sounded ==punchier.== The Odyssey uses triggers, while the Minimoog does not.

When playing lines very quickly, the ==notes overlap==. But the ==contour on Odyssey remains dynamic==, the ==start== of each note is ==clearly defined==. The Odyssey ==re-triggers its transient generators== everytime I play a note, regardlss of whether previous ones are released or not and regardless of whether the Gate is open or not. So the sounds are correctly articulated, no matter how unevenly I release the keys.
（Trigger与Gate独立后，每个音的开始不受上个音的影响，对于演奏技巧较低的用户友好，不需要能够完整抬起手指即可演奏高速多音）

Minimoog does not generate triggers. It will ==not re-trigger== when the gate is open so the punch is lost.

If the transient generators are merely ADs or trapezoid. A ==retriggered AD transient== would sound much the ==same==, but with ==no triggers== the sound would diappear to ==silence== after the first note or two. If the contours are ==trapezoids==, the two solos would sound ==identical==. Odyssey's contours ==didnot reset to zero== at the start of each note.

==Resetting to zero==. lead to very ==disjointed sound== because of their ==lower Attacks and Releases==. It's noticeable on some string ensembles where the singgle envelope generator resets every time it is initialized.




### Putting It Together
There are many other facets to transient generators and timing signals. Analogue synths can have five or more stages contours with Hold stages and Break points amongst other extra goodies. Make a transient quicker at high pitches than at lower ones. There are other useful destinations for the contours, the pitch of the sound, modulation speed (add vibrato, growl or tremolo with electronic, changing the effect by applying contours to the LFO speed and depth). Applying 2 contours to a single VCO or VCF, and even delaying the trigger of one slightly with respect to the other.

If you want to recreate acoustic sounds or program interesting synthesizer sounds deterministically then, at the very least, you must be able to analyse and create the brightness and loudness contours of the sound.


## More about Envelopes
There are plenty of very common sounds that synthesizers cannot synthesize.
So digitally-controlled analogue architectures is better. 
DEGs -- ==Digital Envelope Generators== -- because their ==shapes are calculated in real time by a microprocessor before being converted into analogue voltages==. DEGs offer a far greater range of contours than the simple ADSR, if only the ==Break Point== can be above or below the Sustain level.

Don't become carried away by the current craze for vintage synths or their DSP-generated descendants. Think about the type of sounds you want to generate, and choose your instrument carefully  so that you can produce them.

## An Introduction to VCAs
VCA : Voltage Controlled Amplifier
digitally controlled analogue synths: DCA
pure digital synths and samplers have time-variant amplifiers(TVA), operator levels

#### Two Types of VCA
Amplifiers in the audio signal chain
and those used to modify control voltages

Whenver you have more than one amplifier and/or attenuator in series, you can calculate the Gain of the whole system simply by multiplying the individual Gains together.

G = (Output from Power Amplifier)/(Signal produced by Receiver)

### A better circuit
Redefined the preamp as a Voltage Controlled Amplifier, and the audio signal no longer passes through the volume control.

### From Radios to Synthesizers
The signal generated by the received circuit could be anything.

### Initial Gain
initial Gain/ VCA Gain. add an initial CV or offset to whatever CV the Contour Generator produces.

If the output exceeds the defined maximum output from the VCA, there will be a clipped signal. The result is a harsh distortion(clipping distortion). 

### A Different Use for VCAs
 Place a ==VCA in the control signal path==, and it is controlled by a CV that itself controlled by an attenuator. This VCA applies a Gain to the ADSR contour so that you can attenuate or amplify it without changing its shape.
 
ADSR is not the only CV affecting the signal amplifier. As well as the Initial Gain, you could have LFOs or a host of other controllers modifying the audio signal amplifier's action upon the signal. You are changing the degree by which the ADSR modifies the signal relative to the initial level and any other modifiers in use.
The CVs are controlling a low-pass filter, not an amplifier. The fader at the top of the figure is now the initial level of the filter, most usually called the cutoff frequency. And the VCA is controlling the amount of contour applied to this. Every synth allows you to attenuate the contour using a VCA.

### Real VCAs
==Amplifier or VCA== is ==dominated by an ADSR contour generator==, with an ==envelope level control(Amount)== and/or ==Initial Level control== too.
Similarly, the ==filter section== will often contain a ==second contour generator== and another ==Amount control== alongside the cutoff and resonance knobs. This means, there are ==VCAs in the VCF== section too.
In a well-specified VCA. has ==4 inputs==, 5 knobs and 1 output. 2 signal inputs(SIG 1 IN & SIG 2 IN), there's a ==signal mixer== in the module. 2 CV inputs which control the amplification of the VCA, meaning there is a ==CV mixer== too. The CV inputs are marked ==CV1-IN LIN and CV2-IN LOG==. Each of the four inputs has an associated ==level control==, and there is an ==Initial Level control.==

### And Finally
One of the most common uses for VCAs is to modify the actions of CVs using other CVs;

We should not differentiate between amplifiers in the audio signal chain and those used to modify control voltages.

Whenever you have more than one amplifier and/or attenuator in series, you can at any moment calculate the Gain of the whole system simply by multiplying the individual Gains -- at each instant -- together.













## Modulation
Modulation makes sounds live and breathe in an organic sort of way.

### Three Simple Modulations
A tone generator is the signal source. The output from this first passes through a filter, and then an amplifier before reaching the outside world. The contour generators shape the sound by causing the filter and amplifier to affect the brightness and loudness of the sound at the second and third stages. 
==Vibrato : raise and lower the pitch slightly.==
CV(the ==modulation waveform==) is supplied by a ==LFO==, ==VCA== controls the ==amplitude of the modulating waveform==, and the ==VCA== itself is ==controlled by a modulation wheel==. The VCA and wheel are very import for controlling the amount of vibrato.

### Tremolo
==Tremolo : a periodic change in the loudness of the sound.== The frequency of the note remains constant, but the level changes in time.
Vibrato modulates the pitch of the oscillator, tremolo requires something ==modulates the gain of the audio amplifier== at the end of the signal chain.

Modulate voltage controlled filter. 
3 distinct effects : 
1. slowest settings ==0.1Hz==, slow filter sweep, useful for ==ambient sounds==.
2. increase the speed to around ==1/2Hz, wah-wah effect==
3. increase the speed to the upper limit of subsonic oscillations, around ==10-20Hz==, a ==growl==, which can be super for simulating ==brass== instruments.

A better synth will offer ==individual LFOs that you can assign to each destination==, with the depth of each effect governed by a selection of controllers. This might include modulation wheels, aftertouch(pressure sensitivity), or foot pedals.

It's unlikely that you will want to control the level of each of the three modulation VCAs using all three controllers simultaneously. You should consider the lines joining the controllers to the VCAs as options. This introduces us to the ==switches that select between sources and destinations== on most synthesizers.

### Another Simple Modulation
Square wave : a pulse waveform that spends the same amount of time at its peak as it does at its nadir.
The square wave is a special case of pulse waves. Pulse waves sahre the same rectangular shape, but are different in as much as the ratio of the time the signal spends at the top and bottom of the wave differs. The ratio is '==duty cycle=='. The square wave spends half its time at the top, it has a ratio of 1:2, a duty cycle of 50%. 1:3(33.3%), 1:4(25%)/ 
（Duty cycle的百分比指的是top时间占top+bottom时间的比例）

Duty cycle greater than 50%. For any number X lying between 0 and 50, a duty cycle of (50+X) percent is identical to that of (50-X) percent, but the phase is inverted.

Pulse waves with different duty cycles have quite different audible characteristics.
1. Narrow cycles, 5-10%, thin and nasal, used to create sounds such as oboes.
2. Closer to 50% sounds thicker.
3. exactly 50%, distinctively hollow character that is ideal for simulating clarinets and other woody sounds.

Timbral changes are a consequence of the harmonics present in each waveform, and the amplitudes that they each process. The relationship between the duty cycle and the harmonic distribution:
A pulse wave has the same harmonic distribution as a sawtooth wave except that, for a ==duty cycle of 1:n==(n is an integer) every ==nth harmonic is missing== from the spectrum.

e.g. a duty cycle of 1:2, every 2nd harmonic is missing. Only have 1st, 3rd, 5th, 7th...harmonics.
1:3. missing every 3rd harmonic, 1st, 2nd, 4th, 5th, 7th ...
1:4, missing every 4th harmonic, 1st, 2nd, 3rd, 5th, 7th, 9th ...

What happens when the duty cycle is not an exact integer ratio?
e.g. 28.5% pulse wave, between 1:3 and 1:4 duty cycles. Every 3rd harmonic is ==somewhat attenuated==, as is every fourth, but ==no harmonics are completely eliminated== from the signal.

==Pulse Width Modulation==, uses a second CV input to the oscillator which instead of modulating the frequency, allows you to modulate the duty cycle of the pulse wave oscillation. If an LFO provides the modulating CV....
Creates the lush chorused sounds that make many analogue synthesizers desirable. Pulse Width Modulation is usually applied to pulse waves, you can also apply it to sawtooth waves.

PWM is ideal for creating string ensemble sounds, as well as rich lead synth patches. But don't confuse it with chorus effects. ==Chorus splits the final signal== produced into 2 parts, and then use ==delay and modulation== processes to create their effects. ==PWM modulates the amplitudes of the individual harmonics at their source==, and produce a unique range of sounds.
They use LFO as the source of modulating control voltages. What happens when we modulate the oscillator, filter and amplifier using audio-frequency(AF) signals.








## Amplitude Modulation
1 signal acts as Carrier and the other acts as Modulator.
Creates 2 new frequency Sum and Difference.
And the result is Carrier signal as dominant signal, sum and difference half the amplitude of the Modulator.

### In Use
2 cases, one is the Modulator lies at a fixed frequency, another where the Modulator as well as the Carrier tracks the keyboard or any other controlling voltage.

e.g. The Modulator is fixed at a frequency of 100Hz.

CASE 1 : 
	Carrier frequency = 100Hz, the three frequencies produced by the Amplitude Modulation lie at 0Hz, 100Hz and 200Hz. ==0Hz==, still has an ==amplitude==, and this manifests itself as an offset in the signal. We call this a ==DC offset== because being at 0Hz it has ==no oscillation frequency==. Because a very high proportion of the output signal lies above the axis. ==DC offsets== can have significant ==effects== when a signal is processes by other synthesizer modules such as ==filters and amplifiers==. The Sum signal is 200Hz, an octave above the Carrier, sound harmonic, sweet. The three components at the output lie at 0 percent, 100 percent and 200 percent of the Carrier frequency.

CASE 2 :
	Carrier frequency = 200Hz, difference = 100Hz, sum = 300Hz. Still tonal to a degree because the difference is an octave below the Carrier. The sum is not harmonically related to the Carrier. The Sum is the third harmonic of the Difference, so the output still sounds musical. The three components at the output lie at 50%, 100%, 150% of the Carrier frequency.

CASE 3 : 
	Carrier frequency = 371Hz, difference = 271Hz, sum = 471Hz. No harmonic relationship. The three components at the output lie at roughly 73%, 100% and 127% of the Carrier frequency and the result is enharmonic and clangorous.
	==Fixed-Modulator AM== is most useful for creating ==aggressive and conventionally unmusical sounds== that change dramatically as you play up and down the keyboard. You can control the amount of ==enharmonicity by raising or loweing the level of the Modulator.==

CASE 4 :
	Carrier = 200Hz, Modulator = 100Hz. Output difference 100Hz and sum 300Hz. 
	Patch the synthesiser so that the modulator frequency tracks the change in the Carrier frequency. Carrier = 400Hz, Modulator = 200Hz. D = 200Hz, S = 600Hz. The relationship between the Difference, Carrier, and Sum signals is 50%, 100% and 150%. The frequency may have doubled, but the shape of the waveform remained the same. This happens if both Carrier and Modulator track the keyboard equallt. You always obtain a consistent tone at the output. This form of AM offers a way to create complex non-harmonic timbres that change pitch normally as you play up and down the keyboard.

AM is a powerful tool that allows you to create and play new sounds that you cannot obtain using conventional oscillators alone.

If you use other waveforms such as sine waves as input signals. Each signal has a fundamental and 1 extra harmonic. There will be 8 signals. If each signal had 3 components, the number of these side bands will be 18. 4 components -> 32 side bands.

Use square waves and sawtooth waves as Carriers and Modulators. A sawtooth wave contains all the harmonics in the conventional harmonic series. There will be a lot of reactions between the fundamental and harmonics of the modulator and those of the Carrier.


### Real VCAs & Ring Modulators
Even a small amount of Modulator will contaminate the output signal quite noticeably and this will increase the enharmonic quality of the result.
There is another class of synthesiser modules that eliminate not only the Modulator but also the Carrier from the output. These are Ring Modulators, devices that have acquired a certain mystique over the past few years. A Ring Modulator is a special case of an AM. It only works when both the Carrier and the Modulator waveforms are precisely centered on 0 volts. To facilitate this, many ==RMs are AC coupled==. which means, any ==DC offsets in the inputs are eliminated before modulation==. The result is an ==output consisting of the Sum and Difference frequencies==, but ==neither of the input frequencies==. Lesser RMs are DC coupled and respond somewhat differently from the ==AC-coupled== cousins. These allow the Carrier and Modulator signals to pass into the output. 

### Filter Modulation
==modulate the cutoff frequency of a low-pass filter== rather than the gain of a VCA. A single ==harmonic== of a complex waveform lying somewhere just ==above the cutoff frequency Fc==. As you ==modulate Fc== you will find that sometimes the ==harmonic is attenuated more== because of the modulation, while at other times it is attenuated less. The harmonic is being ==AM by the changing action of the filter==. Depending on the ==width of the modulation== the same is true to a greater or lesser extent for all the other ==harmonics== within the signal. So this time, instead of having one set of harmonics modulating another set of harmonics, we have just ==a single set==, but ==each== component is being ==modulated in a different way.==
## Frequency Modulation
### FM is Simply Very Fast Vibrato
the simple vibrato, the frequency of that Modulator is significantly lower than that of the Carrier. That happens as we increase the Modulator's frequency until it approaches, equals or even exceeds that of the Carrier. Instead of looking like a cyclical squeezing and stretchhing of the Carrier waveform, the modulation will become a form of distortion within the individual cycles of the Carrier waveform. Apply Modulation whose frequency is 60 times of that of the Carrier, it sounds nothing like vibrato.

### Side Bands, Side Bands Everywhere.
Like AM, FM generates side bands -- additional components, not necessarily harmonically related to the frequency of the Carrier or Modulator -- in the frequency spectrum  of the output signal. Take an example of a sine wave Carrier with frequency wc and a sine wave Modulator of frequency wm.  AM generates just 2 side bands sum and difference, FM produce a whole series that can be expresses as
$$ w_sb = w_c +- n* wm$$
Each side band lies at a frequency equal to the Carrier frequency plus or minus an integer multiple of the Modulator frequency. n can take any integer value, FM to a signal produces an infinite series of side bands. In real world, no system has infinite bandwidth. An analogue system are limited to producing side bands within their finite bandwidth.

FM generate side bands, and Modulator's frequency determines where they lie. But as for the shape of the resulting spectrum? turn to 2nd attribute of the Modulator, its gain. Modulation Index, beta.

Imagine a simple synthesiser patch where the amplitude of a modulation is modified by a VCA that is itself controlled by a CV source. A simple vibrato case. The gain of the VCA is zero, no modulation, the Carrier will produce an unmodified tone. Increase the gain of the VCA, a gentle vibrato results. Keep increasing the gain until the Modulator is sweeping the Carrier over a wide range of frequencies. ==The sound we hear is not only determined by the frequency== of the Modulator, but ==also by its gain or maximum amplitude==.

Applying these ideas to audio frequency FM, define beta as the ratio of the Carrier's frequency's sweep(the amount by which the Carrier deviates from its unmodulated frequency) divided by the Modulator frequency.
$$ Beta = delta(w_c)/w_m$$
The numerator of this expression is the change in the Carrier frequency, beta is directly related to the amplitude of the Modulator. For any given Modulator frequency, it is the ==Modulation Index== that ==determines the amplitude== of each of the ==components== in the spectrum of the output signal.

If the Modulation Index is low (<=0.1), the only significant side bands will be those closest to the Carrier frequency. If beta is higher, in the region of 5, we obtain a broader series of side bandsm and a much more complex spectrum results. The consequence is that the amplitude of the original Carrier frequency has diminished significantly. 

In beta, the denominator is the f of the Modulator. If you play the sound up and down the keyboard, require ==C & M track the keyboard equally==. But as ==M frequency increases==, beta decreases. To avoid this change, the ==Modulator amplitude must increase proportionally.==

### FM Versus Analogue Filters
Bandwidth is the range of frequencies occupied by any given signal.
==Bandwidth of FM signal==. Theoretically infinite, the Modulation Index will ensure that side bands of higher n are of negligible amplitude.
$$B = 2*w_m(1+beta)$$
==High values of beta== allow FM to create much more ==complex signals with a much higher bandwidth== than the other methods of making 2 signals interact. 

In simple subtractive synthesis, ==changes in the volume== are most often determined by a ==contour generator acting upon an amplifier==. Any ==changes in the tone== of a sound are usually determined by a ==contour generator acting upon the cutoff frequency== of a filter. 
In FM configuration, the volume of the sound is still determined by the volume envelope of the audio signal, but you ==no longer need a filter to modify the tone==. This is because, for any given Modulator frequency, the ==Modulator amplitude determines the bandwidth of the output.==
The amplitude of the output signal will decrease as EG2 decreases the gain of VCA2 -- so over time, the output gets quieter and quieter. The maximum amplitude of the Modulator signal will increase as EG1 increases the gain of VCA1. As time passes, the Modulation Index increases, the bandwidth increases, and the output gets brighter and brighter.

### Summary
- The number of significant spectral components and their amplitudes are determined by the Modulation Index, which is proportional to the Modulator's amplitude; but inversely proportional to the Modulator's frequency.
- For any given Carrier frequency, the position of the spectral components is determined by the Modulator's frequency alone.

Frequency Modulation is a powerful method of synthesis that is as relevant to the analogue synthesisers as it is to digital ones, and which is capable of generating sounds unobtainable by any other method.

## More On Frequency Modulation
