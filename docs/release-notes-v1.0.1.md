# Gateway OS V1.0.1

Public binary hotfix release for Gateway OS.

![Gateway OS GUI](https://github.com/SlamminMofo/GatewayOS-Releases/raw/main/docs/assets/GatewayOS_GUI.jpg)

![Gateway OS settings menu](https://github.com/SlamminMofo/GatewayOS-Releases/raw/main/docs/assets/GatewayOS_GUI_Menu.jpg)

> Superseded for macOS users by Gateway OS V1.0.2.

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

## Research Background

- R. E. Crochiere and L. R. Rabiner, "Interpolation and Decimation of Digital Signals: A Tutorial Review", Proceedings of the IEEE, 1981. https://doi.org/10.1109/PROC.1981.11969
- P. P. Vaidyanathan, "Multirate Digital Filters, Filter Banks, Polyphase Networks, and Applications: A Tutorial", Proceedings of the IEEE, 1990. https://ieeexplore.ieee.org/document/52200
- J. O. Smith and P. Gossett, "A Flexible Sampling-Rate Conversion Method", ICASSP 1984. https://ccrma.stanford.edu/~jos/resample/
- Z. Cvetkovic and M. Vetterli, "Oversampled Filter Banks", IEEE Transactions on Signal Processing, 1998. https://doi.org/10.1109/78.668721
- J. D. Parker, V. Zavalishin, and E. Le Bivic, "Reducing the Aliasing of Nonlinear Waveshaping Using Continuous-Time Convolution", DAFx-16, 2016. https://www.dafx.de/paper-archive/2016/dafxpapers/20-DAFx-16_paper_27-PN.pdf
- A. Carson, V. Valimaki, A. Wright, and S. Bilbao, "Resampling Filter Design for Multirate Neural Audio Effect Processing", 2025. https://arxiv.org/abs/2501.18470
- R. Sato and J. O. Smith III, "Aliasing Reduction in Neural Amp Modeling by Smoothing Activations", 2025. https://arxiv.org/abs/2505.04082
- A. Carson, A. Wright, and S. Bilbao, "Anti-aliasing of Neural Distortion Effects via Model Fine Tuning", 2025. https://arxiv.org/abs/2505.11375
- A. Carson, A. Wright, J. Chowdhury, V. Valimaki, and S. Bilbao, "Sample Rate Independent Recurrent Neural Networks for Audio Effects Processing", 2024. https://arxiv.org/abs/2406.06293
- R. Yoneyama, A. Miyashita, R. Yamamoto, and T. Toda, "Wavehax: Aliasing-Free Neural Waveform Synthesis Based on 2D Convolution and Harmonic Prior for Reliable Complex Spectrogram Estimation", 2024. https://arxiv.org/abs/2411.06807

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
