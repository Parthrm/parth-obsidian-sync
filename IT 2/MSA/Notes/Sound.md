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

### 🧩 **What is MIDI?**

- Developed: **1980s**
- **Purpose**: Communication protocol for **electronic instruments & computers**
- Works via **cables** and **digital messages**

> ⚠️ **MIDI ≠ Sound**  
> It’s a **shorthand** for music – not the actual audio.

🎯 **Analogy**:

> _MIDI = Vector graphics_  
> _Digital Audio = Bitmap image_

### 🎹 **How MIDI Works**

- **Captures** musical actions:
    - Which note played
    - How hard it was hit
    - How long it lasted
    - Volume dynamics
    - Instrument used
- These are **time-stamped commands** that a **MIDI playback device** interprets.

### ⚙️ **What You Need to Create MIDI Music**
- 🎼 **Notation Software** – Compose sheet music
- ⏱️ **Sequencer Software** – Record, play, and edit sequences
- 🎛️ **Sound Synthesizer** – Built into most devices
- 🎹 **MIDI Keyboard** – Helps record actual notes

### 🧠 **Benefits of MIDI**
- ✨ **Creative Freedom**: Compose from scratch
- ✂️ **Easy Edits**: Change instrument with a number (0–127 via General MIDI system)
- 💾 **Small File Size**: Light on storage, heavy on expression
- 🎯 **Precision**: Quantization fixes off-beat notes
- 🧻 **Printable**: Create printable sheet music

### ⚠️ **Limitations of MIDI**

- 🎧 **Device Dependent**: Playback depends on user’s hardware
- 🥴 **Unpredictable Sound**: Different devices = different results
- 🚫 **Not Ideal for Final Delivery**: Use MIDI for **production**, then convert to **digital audio** for consistent playback

### 🎷 **MIDI Envelopes – The Feel of the Note**
- **Attack** – How quickly sound volume rises
- **Sustain** – How long it lasts
- **Decay** – How fast it fades out

### 💼 **Working with MIDI in Multimedia Projects**
- 🔄 Change a piano to a saxophone? Just change the instrument ID
- 💼 Hire a MIDI composer or collaborate with new talent
- 🔁 Once done, **convert MIDI to digital audio** for reliable output

---

# MIDI vs Digital Audio

| **Aspect**                       | **MIDI**                                                                                      | **Digital Audio**                                                                       |
| -------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| **Definition**                   | Shorthand representation of music (score, notes, instruments).                                | Actual recording of sound in the form of sampled audio data.                            |
| **Data Type**                    | Structured, numeric music instructions.                                                       | Continuous waveform sampled at discrete intervals.                                      |
| **Size**                         | Very compact (200 to 1,000 times smaller than digital audio).                                 | Large file size, especially at CD-quality.                                              |
| **Device Dependency**            | Device dependent—sound depends on the MIDI synthesizer used.                                  | Device independent—sound playback is consistent across devices.                         |
| **Editing**                      | Easily editable down to individual notes; very flexible.                                      | Hard to edit—requires audio editing tools and is less precise.                          |
| **Conversion to Sheet Music**    | Can be converted to and from musical notation easily.                                         | Cannot be converted directly to sheet music.                                            |
| **Instrument Change**            | Instruments can be changed by altering values.                                                | Changing instrument requires re-recording.                                              |
| **Playback Consistency**         | Playback may vary depending on hardware.                                                      | Playback remains mostly consistent regardless of system.                                |
| **Use in Web Pages**             | Loads and plays quickly due to small size.                                                    | Slower to load and stream due to file size.                                             |
| **Tempo Control**                | Can change tempo without affecting pitch.                                                     | Changing tempo usually affects pitch and quality.                                       |
| **Quality Reliance**             | Depends on quality of MIDI sound source.                                                      | Quality depends on recording and sample rate.                                           |
| **Speech Playback**              | Cannot easily be used for spoken dialog.                                                      | Can easily include spoken dialog and other complex audio.                               |
| **Best Used When**               | - Low memory/bandwidth- High-quality MIDI sound- Full control over playback device- No speech | - Consistent playback quality required- Need to include spoken words or natural sounds. |
| **Analogy to Graphics**          | Like **vector graphics** (instruction-based).                                                 | Like **bitmap graphics** (sampled copy of the original).                                |
| **Tools Required**               | MIDI sequencer, notation software, synthesizer, optional MIDI keyboard.                       | Audio recorder or editing software.                                                     |
| **Flexibility in Composition**   | Highly flexible for composing and editing.                                                    | Less flexible for composition once recorded.                                            |
| **Usage in Multimedia Projects** | Excellent for production and editing phase.                                                   | Preferred for delivery due to playback consistency.                                     |

---

# Multimedia System Sounds

Every computer comes with basic system sounds that play during certain events, such as startup, errors, notifications, or button clicks. These sounds are available as soon as the operating system is installed. In Windows, these system sounds are stored as `.wav` files in the `Windows\Media` folder and include familiar tones like `ding.wav`, `tada.wav`, and `notify.wav`. Users can manage and customize these sounds through the Sound Control Panel, where they can assign different audio cues to specific system events or even create themed sound schemes to suit different moods. Additionally, custom `.wav` files can be added to the Media folder and set as system sounds. On macOS, system sound customization is more limited—you can only change the alert sound. To do so, users place their custom `.aif` file into the `~/System/Library/Sounds` directory and then select it in the Sound preferences pane.

---

# Audio File Formats


---

# Vaughan's Law of Multimedia Minimums