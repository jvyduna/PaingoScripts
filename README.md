# PaingoScripts

I finds the Pangolin scripting language (PangoScript) to be quite painful, but I've wrestled it unwillingly into doing some useful things. This repo contains scripts I've polished up with lots of comments.

## Scripts

* **[Knob or fader to QuickFX 2^X speeds](scripts/Knob%20or%20fader%20to%20QuickFX%202%5EX%20speeds.BeyondCode)** - Takes a fader or rotary pot on a MIDI controller, such as on a APC40mk2 or Traktor F1, and scale the global cue speed to snap to a 2^X speed multiplier (25%, 50%, 100%, 200%, 400%, etc). For example, if you've made cues with a 4 beat duration, this lets you us a MIDI control to instantly change their duration to 8, 16, or 32 beats (as well as 2, 1, 1/2, 1/4 of a beat).
* **[Rotary relative encoder to 2^X cue speeds](scripts/Rotary%20relative%20encoder%20to%202%5EX%20cue%20speeds.BeyondCode)** - Takes a rotary incremental (relative mode) encoder on a MIDI controller, such as on a APC40mk2 or Traktor F1, and scale the metronome for beat-based effects in selected QuickFX rows to snap to a 2^X time scale multiplier. For example, if you've made effects with a 2 beat nominal duration, this lets you twist a knob and instantly change their duration to 2, 4, 8, or 16 beats (as well as 1, 1/2, 1/4, or 1/16th of a beat).

## PangoScript Documentation

[Official PangoScript Command List] (https://wiki.pangolin.com/doku.php?id=beyond:pangoscript_commands)

[Wiki Docs](https://wiki.pangolin.com/doku.php?id=beyond:pangoscript_commands) (see the PangoScript heading)

The documentation in the editor is inconsistent and a little difficult to read. I commonly need to search these docs in a more flexible format. I've exported them to a Google Doc [here](https://docs.google.com/document/d/1z5e5lyS2LXS5ih7t-NOKsidoieMEVjgoa71GHQ82yeY/edit).

If you have a ChatGPT Plus account, [try this GPT](https://chat.openai.com/g/g-UmZr51iip-paingoscript-helper) which has been trained with the PangoScript docs and some larger example scripts.
