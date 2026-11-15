# Interactive Signal Transformation & Analyzer

# Project Overview
This project is a Python-based simulation for the Signals and Systems course. It generates standard continuous-time signal samples, applies a selected time operation, separates the resulting signal into even and odd components, estimates energy and average power over a finite interval, and plots the results.

# Features
- Generates eight signals: Sine, Cosine, Square, Triangular, Ramp, Unit Step, Impulse and Exponential.
- Supports three operations: No Operation, Time Shifting and Time Scaling.
- Calculates even and odd components.
- Reconstructs the signal by adding the even and odd components.
- Estimates signal energy and average power over the selected finite time interval.
- Classifies the selected signal as periodic or aperiodic using the categories defined in the program.
- Saves a four-panel graph as `output_graph.png`.

# Technologies
- Python 
- NumPy
- Matplotlib

# Project Files
- `signal_transformation_analyzer.py` — main Python program.
- `requirements.txt` — required Python libraries.
- `output_graph.png` — supplied simulation output graph.
- `PROJECT_REPORT.pdf` — technical project report.

# Installation
Open a terminal in this folder and run:

```bash
python -m pip install -r requirements.txt
```

# Run the Program

```bash
python signal_transformation_analyzer.py
```

Enter:
1. Signal choice (1 to 8).
2. Amplitude.
3. Positive frequency in Hz.
4. Operation (1: no operation, 2: time shifting, 3: time scaling).
5. The shift or non-zero scaling factor if requested.

The program uses a time array from -5 to +5 with 1001 samples and saves the generated plot as `output_graph.png` in the current working directory.

# Mathematical Concepts

* Signal generation*
- Sine: `x(t) = A sin(2πft)`
- Cosine: `x(t) = A cos(2πft)`
- Square: `x(t) = A` when `sin(2πft) >= 0`, otherwise `-A`
- Triangular: `x(t) = (2A/π) sin⁻¹(sin(2πft))`
- Ramp: `x(t) = A max(t, 0)`
- Unit step: `x(t) = A` for `t >= 0`, otherwise `0`
- Impulse: represented numerically by one non-zero sample.
- Exponential: `x(t) = A exp(-ft)` for `t >= 0`, otherwise `0`.

* Time operations*
- Time shifting: `y(t) = x(t - t₀)`
- Time scaling: `y(t) = x(at)`, where `a` is non-zero.

* Even and odd decomposition*
- `x_even(t) = [x(t) + x(-t)] / 2`
- `x_odd(t) = [x(t) - x(-t)] / 2`
- `x(t) = x_even(t) + x_odd(t)`

*Numerical energy and average power*
- `E ≈ Σ |x[n]|² Δt`
- `P ≈ E / T`

# Graph Description
The supplied graph contains four panels:
1. Original signal.
2. Even component.
3. Odd component.
4. Signal reconstruction, comparing the transformed signal with the sum of its even and odd components.

# Notes and Limitations
- Energy and average power are numerical estimates over the finite interval from -5 to +5; they are not infinite-duration analytical values.
- The impulse is approximated by a single non-zero array sample, not an ideal continuous-time Dirac delta.
- The even/odd calculation uses reversed samples. This corresponds to time reversal for the symmetric, uniformly sampled time grid used in the program.
- Very small values in the even component of an ideally odd signal can appear because of floating-point numerical precision.
- The program labels Sine, Cosine, Square and Triangular as periodic, and Ramp, Unit Step, Impulse and Exponential as aperiodic, following its built-in classification list.

## Author Details
 Pushpendra Maurya

