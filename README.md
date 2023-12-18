# grizzle
A wavetable instrument for Pure Data, which can transform live input or samples. A multi-voice, user-friendly but also more cpu-heavy version is available as **grizzle**. There is a more light-weight version **grizzle_module** and the super cpu-friendly but rather ugly version **grizzle_slim**.

## grizzle standalone
grizzle.pd is the standalone and more cpu heavy version of this instrument. It can modify incoming audio or a sample, that can be loaded into the instrument by making wavetables out of it. It has a maximum of 3 voices.

It is meant to be played with a midi keyboard and midi controllers. To edit the control-bindings, go into subpatch -> utilities -> midi -> controls.
If you have your midi device connected, the GUI is mainly meant for display. You should only use it to load a sample as audio input or to choose the envelopes. 

Pitch is a multiplier for the frequency of each note. The volume-multiplier is shown by the slider to the right of the two sample buffer arrays.
The left and right limit show which part of the wavetable is used. They can be controlled with the midi controller (see "start-pos" and "wheel") and also by "mod".
The duty-cycle can be understood as a simple implementation of pulsar synthesis - it is a ratio of the time the wavetable is being played and silence. 
The Toggles labeled "LOOP" and "RECORD" determine whether the samples in the buffers are reloaded every cycle and whether new samples should be recorded from the incoming audio.
The small slider below the two arrays shows the table-size. The Maximum is 96000 samples, the lower, the more cpu intensive this instrument gets. 
The buttons labeled gauss, boxy, pulse... change the envelope of each wavetable.

The feedback, delay and filter effects help, to create a more sustained sound. Next to those sliders you can change how the midi notes trigger the synth (sus toggles the notes on and off, velocity enables velocity, normalize normalizes every wavetable).

The presets do not work!

## grizzle module
This is a more lightweight version, which is meant to be placed inside other patches, not necessarily as a standalone instrument.
It can modify an incoming audio signal or a loaded sample (click the dark gray button in the bottom left to load a soundfile). The faders below the array which has the input sample loaded control the start and end boundaries of that sample.

In this version I ditched the midi inputs. Everything you would want to play with is accessible in the main interface. You can control the left limit (slider), the right limit (through the "wheel" number box, not the slider), the duty-cycle and the frequency with the respective number boxes.
The Volume Fader is on the right, next to the sample arrays. The Toggles labeled "LOOP" and "RECORD" determine whether the samples in the buffers are reloaded every cycle and whether new samples should be recorded from the incoming audio. In the area below you can control the buffer-size (with the small fader) and the envelope with the labeled buttons.

Also try drawing in the phase-distortion array, or choose a preset with the buttons next to it.

## grizzle slim
This is a super cpu efficient version of grizzle. It has basically no GUI, so if you want to learn how this instrument works, maybe start with one of the other two versions. 

It is basically the same as grizzle module, just without fancy graphics. 
