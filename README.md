\# Passive Acoustic Spectrogram Generator



A Python tool to generate high-quality spectrograms for passive acoustic monitoring datasets, optimized for LOW, MID, and HIGH frequency analysis.



Designed for long-term passive acoustic monitoring (PAM) datasets and large audio archives.



\---



\## Features



\* Automatic batch processing of WAV recordings

\* Multi-frequency analysis modes:



&#x20; \* LOW frequency (0–2 kHz)

&#x20; \* MID frequency (1–19 kHz)

&#x20; \* HIGH frequency (20–76 kHz)

\* Chunk-based processing for long recordings

\* Continuous time axis across chunks

\* Raven-like color scale

\* Memory-efficient processing

\* Automatic folder organization



\---



\## Requirements



Python 3.9+



Required packages:



```

numpy

matplotlib

librosa

soundfile

tqdm

```



\### Install dependencies



```bash

pip install numpy matplotlib librosa soundfile tqdm

```



\---



\## Folder Structure



\### Input structure



```

recordings/

│

└── 2014/

&#x20;   ├── REC001.wav

&#x20;   ├── REC002.wav

&#x20;   ├── REC003.wav

```



\### Output structure



```

output/

│

└── 2014/

&#x20;   ├── LOW/

&#x20;   │   └── REC001/

&#x20;   │       ├── chunk\_0.png

&#x20;   │       ├── chunk\_1.png

&#x20;   │

&#x20;   ├── MID/

&#x20;   └── HIGH/

```



\---



\## Usage



Run:



```bash

python generate\_spectrograms.py

```



The program will prompt:



\### 1. Year



```

Enter year (e.g. 2014):

```



This defines the folder to process.



\---



\### 2. Recordings directory



```

Enter recordings directory:

```



Example:



```

/data/recordings

```



\---



\### 3. Output directory



```

Enter output directory:

```



Example:



```

/data/spectrograms

```



\---



\### 4. Frequency mode



```

Choose analysis mode:



1 = LOW frequency  

2 = MID frequency  

3 = HIGH frequency

```



\---



\## Frequency Modes



\### LOW frequency



Designed for:



\* Baleen whales

\* Shipping noise

\* Environmental noise



Settings:



\* Frequency range: 0–2000 Hz

\* Chunk duration: 60 seconds

\* Large FFT window



\---



\### MID frequency



Designed for:



\* Dolphins

\* Fish sounds

\* Anthropogenic noise



Settings:



\* Frequency range: 1000–19000 Hz

\* Chunk duration: 30 seconds

\* Medium FFT window



\---



\### HIGH frequency



Designed for:



\* Porpoises

\* Echolocation clicks

\* Ultrasonic signals



Settings:



\* Frequency range: 20000–76000 Hz

\* Chunk duration: 30 seconds

\* Small FFT window



\---



\## Output



Each recording generates:



```

recording\_name\_chunk\_0.png

recording\_name\_chunk\_1.png

recording\_name\_chunk\_2.png

```



Time axis is continuous:



```

0–60 s

60–120 s

120–180 s

```



\---



\## Spectrogram Settings



Sampling rate:



```

192000 Hz

```



| Mode | n\_fft | hop  |

| ---- | ----- | ---- |

| LOW  | 65536 | 8192 |

| MID  | 8192  | 2048 |

| HIGH | 2048  | 512  |



\---



\## Memory Management



The script:



\* loads chunk-by-chunk

\* frees memory after processing

\* supports large datasets



\---



\## Applications



This tool is designed for:



\* Passive acoustic monitoring

\* Marine mammal detection

\* Bioacoustics research

\* Long-term monitoring

\* Dataset preparation for machine learning



\---



\## Author



Federica Cammarano

Unimib - Marine Sciences



