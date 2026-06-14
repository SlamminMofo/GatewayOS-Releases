# Gateway OS V1.0.0 Release Candidate

> Draft/private release notes. This is not a public release until SlamminMofo explicitly approves publication.

![Gateway OS GUI](https://github.com/SlamminMofo/GatewayOS-Releases/raw/main/docs/assets/GatewayOS_GUI.jpg)

## Status

- Release type: Private release candidate
- Version: 1.0.0
- Source code: Not included in this release repository
- Public visibility: Not approved
- Intended artifacts:
  - Windows VST3 x64
  - macOS AU
  - macOS VST3

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

- Copy `Gateway OS V1.0.0.vst3` to `C:\Program Files\Common Files\VST3\`
- Rescan plugins in the DAW.

macOS:

- Copy `Gateway OS V1.0.0.component` to `~/Library/Audio/Plug-Ins/Components/`
- Copy `Gateway OS V1.0.0.vst3` to `~/Library/Audio/Plug-Ins/VST3/`
- Rescan plugins in the DAW.

## Release Gate

Do not make this repository or release public until SlamminMofo explicitly approves publication.
