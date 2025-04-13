#it2  Notes: [[sound.pdf]]

# Digital Audio

- ==**Digital audio:**== is created when you represent the characteristics of a sound wave using numbers, a process referred to as digitizing
- ==**Sampling:**== is recording sound every nth fraction of a second and stored digitally in the form of bits and bytes
- ==**Bit Depth, Sample Size, Resolution, Dynamic Range:**== It is the number of bits used to store each sample of sound.
- ==**Sampling rate or frequency:**== is the number of samples taken in one second. It is measured in kilohertz.
	3 sampling rates used most are:
	- 44.1kHz
	- 22.05kHz
	- 11.025kHz

>[!warning|right-medium]
>- Quantization can produce an unwanted background hissing noise
>- Clipping may severely distort the sound

==**Quantization:**== The rounded off of value of each sample to the nearest integer is called Quantization.

==**Clipping:**== Amplitude greater than the intervals available are clipped off from the top and bottom of the wave.
![[Pasted image 20250413170137.png]]

---

# Making Digital Audio Files

### 🎙️ **1.** Setting Proper Recording Levels

**🎧 Why It Matters:**
- **Too Loud = Distortion**: Causes **crackling** or **ripping** noises.
- **Too Soft = Useless**: Signal is buried under **residual noise** (like a whisper in a storm).

**📈 Your Goal: The Sweet Spot**
- Use **digital audio meters** — always visible in good recording/editing software.
- **Peak level target**: **–3 dB to –10 dB**
    - This ensures **clarity without distortion**.

**🚨 Watch Out:**
- **Digital ≠ Analog**:
    - Analog meters have a 0 in the middle and go up to **+5, +8**, etc.
    - **Digital meters cap at 0** — **NEVER cross 0 dB**.
    - **If it’s red, it’s dead** (distortion has already happened).

**🎚️ Fix It Before It’s Broken:**
- If the signal **clips (crosses 0 dB)**:
    - Lower **input gain** on your recording device.
    - Or lower **output volume** of your source.
    - **Record again** — never try to "fix" distortion later.

### ✂️ Trimming – The First Cut is the Cleanest

**🎯 Purpose:**
- **Remove "dead air"** (silence or noise) from:
    - **Start** of the recording
    - **End** (unnecessary tail time)

**📉 Why It Matters:**
- Enhances **professional feel**.
- Reduces **file size** (even a few seconds trimmed = big impact).

**🛠️ How It's Done:**
- Visual-based editing:
    - Select the **audio waveform** using your **mouse**.
    - Apply editing commands:
        - **Cut**
        - **Clear**
        - **Erase**
        - **Silence** (replaces with complete silence)

### 🧩 Splicing & Assembly – The Audio Puzzle

**🛠️ What You’re Doing:**
- **Clean up** extra noises (coughs, clicks, background rustles).
- **Assemble** short clips into a longer, seamless track.

**🔧 How It’s Done:**
- Use trimming tools: **Cut**, **Paste**, **Erase**, etc.
- Visually select unwanted parts via waveform view.
- Think digital, not analog:
    - Old-school = cutting magnetic tape

### 🔄 Format Conversion – Speak the Right Language

**Problem**: Editing software ≠ Playback software formats  
**Solution**: Convert formats (e.g., WAV ↔ MP3 ↔ AAC)
- Use your editor to **export** into widely accepted formats.
    
- ⚠️ **Data Loss Warning**:  
    Example: DRM-protected **M4P → Audio CD**
    - **DRM stripped**
    - You can then **rip** to **MP3**, now unprotected.

### 🔽 Resampling / Down Sampling – Slim It Down

**When?**: Original recording = **high quality (16-bit)**  
**Project needs?** = **lower quality (8-bit, lower kHz)**
- Software **reduces the number of samples** → saves disk space.
- Acceptable when publishing to **web or mobile**.

### 🌄 Fade-Ins & Fade-Outs – Smooth Transitions

- Done using **enveloping tools**.
- **Gently increase/decrease volume** at the beginning or end.
- Removes harsh starts and stops.

### 🎚️ Equalization (EQ) – Tone Tuning

- Adjusts **frequency content**:
    - More highs = **brighter**
    - More lows = **darker**, bass-heavy
### ⏳ Time Stretching – Slow Down Without the Clown

- Change **duration**, not **pitch**.
- Useful for syncing voice or music to visuals.
- ⚠️ Don't overdo — most algorithms degrade quality if stretched too far.

### 🎶 DSP – Effects That Matter

**Digital Signal Processing adds magic:**
- **Reverb** – puts sound in a room/hall/cathedral
- **Delay, Chorus, Flange** – adds texture
✅ Makes audio immersive  
❌ Don’t overdo — too many effects = mess

### 🔁 Reversing Audio – Flip the Script

- Play sound **backwards**.
- Great for **surreal effects** (especially dialog or sounds).
### 🧵 Multiple Tracks – Your Sound Canvas

- Mix:
    - **Voice-over**
    - **Music**
    - **Sound FX**
- Combine → Export final mix as a **single audio file**.

### 🧮 Formula 
 
>[!multi-column]
>>[!abstract] Formula to calculate size of digital recording in bytes
>> 
>>$$ Size =\ SR\ *\ T\ *\ \frac{R}{8}\ *\ C $$

SR = Sampling Rate in Hz (convert kHz to Hz)
T = duration in seconds
R = Bit resolution (8 bit, 16 bit)
C = 1 for Mono, 2 for Stereo

---

# MIDI Audio (Musical Instrument Digital Interface)
