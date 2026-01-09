
# Audio Amplifier Project

An analog audio amplifier circuit designed and simulated as part of Electronic Workshop II. This project implements a complete audio amplification system with preamplification, filtering, and power amplification stages.

## Project Overview
This project demonstrates the design and analysis of a three-stage audio amplifier capable of amplifying input signals from microphone-level voltages (10mV) to speaker-level outputs (3.8V) with an overall gain of 383.37.

## Circuit Stages

### 1. Preamplifier Stage
- **Design:** Two-transistor feedback amplifier
- **Purpose:** Amplifies very small input signals (microphone/tape head levels)
- **Key Features:**
  - Feedback loop for improved amplification
  - Push-pull operation for efficient signal regeneration
  - Suitable for boosting small frequencies to higher outputs
  - Historically used in cassette playback recorders

**Frequency Response:** Superior to differential amplifiers with flatter, more stable response curves

**Feedback Effects:**
- Input impedance amplified by feedback factor (1+GH)
- Output impedance reduced by feedback factor
- Assumes feedback network elements are small compared to input impedance

### 2. Active BandPass Filter Stage
- **Type:** Cascaded Low-Pass and High-Pass filters
- **Purpose:** Filters frequencies outside the audio range (50Hz - 20kHz)
- **Design Specifications:**
  - **High-Pass Section (50Hz cutoff):** C₁ = 10μF, R₁ = 320Ω
  - **Low-Pass Section (20kHz cutoff):** C₂ = 10nF, R₂ = 800Ω
- **Q-Factor:** Low Q-factor for wide passband

### 3. Power Amplifier Stage
- **Type:** Class AB Amplifier
- **Characteristics:**
  - Output current flows for more than half but less than one full cycle
  - Two switching transistors in complementary output stage
  - Each transistor conducts on opposite half cycles
- **Advantages:**
  - Better efficiency than Class A
  - Higher quality output than Class B
  - Low crossover distortion
  - High linearity

## Circuit Analysis

### Stage-wise Performance:
| Stage | Input | Output | Gain | Phase Relationship |
|-------|-------|--------|------|-------------------|
| Stage 1 (Preamplifier) | 10mV | 123.16mV | 12.316 | Phase Difference of 180 degrees |
| Stage 2 (Filter) | 123.16mV | 1.6075V | 11.048 | Same phase |
| Stage 3 (Power Amp) | 10mV | 3.9149V | 2.4354 | Phase Difference of 180 degrees |
| **Overall Circuit** | **10mV** | **3.8337V** | **383.37** | Same Phase |

### Capacitor Placement Rationale:
- **Output Capacitor:** Blocks DC voltage while allowing AC signals, preventing DC offset from reaching output
- **Input Capacitor:** Blocks any DC voltage from input source or amplifier biasing, preventing damage or signal distortion

## Design Tools & Simulations
- **Simulation Software:** LTspice/NGSpice (as inferred from project context)
- **Analyses Performed:**
  - Transient Analysis
  - AC Analysis
  - DC Analysis
- **Key Simulation Results:**
  - Input: 10mV sine wave
  - Output: 3.8337V
  - Gain: 383.37 (51.67 dB)

## Technical Specifications
- **Frequency Range:** 50Hz - 20kHz (audio bandwidth)
- **Total Gain:** 383.37 (≈51.67 dB)
- **Amplifier Class:** Class AB
- **Filter Type:** Active BandPass
- **Input Impedance:** Enhanced by feedback network
- **Output Impedance:** Reduced by feedback network



