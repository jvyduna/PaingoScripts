# PaingoScripts

I find the Pangolin scripting language (PangoScript) to be quite painful, but I've wrestled it unwillingly into doing some useful things. This repo contains scripts I've polished up with lots of comments.

## Scripts

* **[Knob or fader to QuickFX 2^X speeds](scripts/Knob%20or%20fader%20to%20QuickFX%202%5EX%20speeds.BeyondCode)** - Takes a fader or rotary pot on a MIDI controller, such as on a APC40mk2 or Traktor F1, and scale the global cue speed to snap to a 2^X speed multiplier (25%, 50%, 100%, 200%, 400%, etc). For example, if you've made cues with a 4 beat duration, this lets you us a MIDI control to instantly change their duration to 8, 16, or 32 beats (as well as 2, 1, 1/2, 1/4 of a beat).
* **[Rotary relative encoder to 2^X cue speeds](scripts/Rotary%20relative%20encoder%20to%202%5EX%20cue%20speeds.BeyondCode)** - Takes a rotary incremental (relative mode) encoder on a MIDI controller, such as on a APC40mk2 or Traktor F1, and scale the metronome for beat-based effects in selected QuickFX rows to snap to a 2^X time scale multiplier. For example, if you've made effects with a 2 beat nominal duration, this lets you twist a knob and instantly change their duration to 2, 4, 8, or 16 beats (as well as 1, 1/2, 1/4, or 1/16th of a beat).
* **[Advance a QuickFX, toggling through multiple layers](scripts/Advance%20QuickFX%20Color%20layers.BeyondCode)** - Many workspaces keep the default scheme of having the first two QuickFX layers apply colors. On some compact MIDI controllers, I've wanted to have a single button advance through the effects in a row. This script advances through the first 24 colors on layer 1, then disables layer 1 and advances through the first 24 effects in layer 2, finally ending with a state where both layers are off.
* **[Relative encoder for fine Channel adjustment](scripts/Relative%20encoder%20for%20fine%20channel%20control.BeyondCode)** - Beyond channels show up as values between 0 and 100 in the Channels tab, but are internally stored as a normalized 0..1 float. This makes them useful tools for linking to any parameter that takes an input. Sometimes you want much finer control over a parameter than 127 values from MIDI (and few controllers support 14-bit MSB+LSB). You may have experienced this when linking MIDI controllers to Z rotation - it's steppy and I've resorted to enabling physics to dampen the motion which helps a little but is still imprecise. I was recently preparring for a film shoot where I needed fine control over some large value ranges (precise points counts in a resampler to help tune rolling shutter banding). By configuring my rotary encoder to send incremental up/down values, you can route it to paramater inputs through Channels using arbitrary fine resolution using the internal float value.
* **[Select Groups mode Destination cues from APC40 Track/Clip Stop buttons](scripts/Select%20Groups%20mode%20Destination%20cue%20from%20APC40%20Track%20btn.BeyondCode)** - I like Groups mode, though it still has several bugs around destination/chase cues being brittle. I like the default assignment of zone destinations, and there seem to be many effects across zones that can only be accomplished with MultiFX. However, you cannot select destination cues from MIDI controllers. This is likely a temporary bug that will eventually be fixed, but I wanted to be able to select them from an APC40 mkii now. Since the Clip Stop and Channel Select rows are mapped to Zone Mute and Output by default, I reassigned those buttons to use this script, which also manages the LED state. Unfortunately it currently requires your page of destination cues to be the first page in your workspace, but there's likely some way around this limitation with more scripting.

## PangoScript Documentation

[Official PangoScript Command List](https://wiki.pangolin.com/doku.php?id=beyond:pangoscript_commands)

[Wiki Docs](https://wiki.pangolin.com/doku.php?id=beyond:pangoscript_commands) (see the PangoScript heading)

The documentation in the editor is inconsistent and a little difficult to read. I commonly need to search these docs in a more flexible format. I've exported them to a Google Doc [here](https://docs.google.com/document/d/1z5e5lyS2LXS5ih7t-NOKsidoieMEVjgoa71GHQ82yeY/edit).

I've also seen that @anodetocode has started an [excellent intro to PangoScript doc](https://github.com/anodetocode/pangoscript-intro).

If you have a ChatGPT Plus account, [try this GPT](https://chat.openai.com/g/g-UmZr51iip-paingoscript-helper) which has been trained with the PangoScript docs and some larger example scripts. It's... not highly reliable.

## Undocumentated helpful tricks

* `writeln` logs output to a console-like window that is much more usable than the `DisplayPreview` or `LogInfo` (QLog tab)
* param(1), param(2), and param(3) will return the three bytes from an incoming MIDI message that triggered a script