# Gateway OS V1.0.1

Public binary hotfix release for Gateway OS.

![Gateway OS GUI](https://github.com/SlamminMofo/GatewayOS-Releases/raw/main/docs/assets/GatewayOS_GUI.jpg)

## Status

- Release type: Public binary hotfix
- Version: 1.0.1
- Source code: Not included in this release repository
- Included artifacts:
  - Windows VST3 x64
  - macOS AU
  - macOS VST3

## V1.0.1 macOS Hotfix

- Corrects the AU AudioComponents identity so macOS hosts see `SlamminMofo: Gateway OS` instead of inherited NeuralAmpModeler metadata.
- Gives the AU its Gateway OS manufacturer/subtype/name tuple: `aufx` / `G100` / `SMfo`.
- Adds Apple `auval -v aufx G100 SMfo` validation to the macOS build workflow.
- Ad-hoc signs the staged macOS AU and VST3 bundles before upload.
- Keeps the same Gateway OS DSP, oversampling, multicore, and GUI source used for the Windows VST3 build.

## Highlights

- Correct WaveNet-family oversampling modes: Off, 2x, 3x, 4x, 8x, 16x, and 32x.
- Supported models run at the requested internal multiple with time/dilation scaling to preserve capture feel while reducing aliasing.
- Multicore polyphase mode is designed to reduce oversampling wall-clock CPU cost while remaining bit-identical to single-core mode.
- Main-window OS/MC status readout.
- Theme-color selector with compact dot palette.
- EQ, noise gate, slim, input calibration, IR loading, and pre/post EQ routing included.

## Install Notes

Windows:

- Copy `Gateway OS V1.0.1.vst3` to `C:\Program Files\Common Files\VST3\`
- Rescan plugins in the DAW.

macOS:

- Remove older `Gateway OS V1.0.0.component` and `Gateway OS V1.0.0.vst3` bundles if installed.
- Copy `Gateway OS V1.0.1.component` to `~/Library/Audio/Plug-Ins/Components/`
- Copy `Gateway OS V1.0.1.vst3` to `~/Library/Audio/Plug-Ins/VST3/`
- Rescan plugins in the DAW.

If a macOS host cached the old AU metadata, reboot or clear the host/plugin cache before rescanning.
