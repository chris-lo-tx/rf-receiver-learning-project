Frequency: 101.900 MHz
Bandwidth: 200k 
| Arm length | Signal peak | Noise floor | Audio |
|---:|---:|---:|---|
| 50 cm       |   -37.4dB   |   -67.4dB   |       Clear      |
| 60 cm       |   -36.5dB   |   -60.2dB   |       Very Clear      |
| 70 cm       |   -32.0dB   |   -58.0dB   |      Very Clear       |
| 75 cm       |   -33.0dB   |   -59.0dB   |      Slight distortion/intro of white noise       |
| 80 cm       |   -35.5dB   |   -59.2dB   |      Very Clear       |
| 90 cm       |   -37.5dB   |   -62.3dB   |      Audio seems to be clear, not sure if there is a slight sharpness at times.       |

<img width="1597" height="934" alt="image" src="https://github.com/user-attachments/assets/2473a222-ca6f-4cee-93e5-a15a754aa7de" />

Note: As the antenna arm length was increased, the waterfall showed a brighter or hotter red. (Based on my current app settings.) 
Additionally, other weaker signals that were observed at 50 cm became much clearer as the length increased. 

For 101.9 MHz, the calculated wavelength is approximately:
\[
\lambda=\frac{c}{f}\approx2.944\text{ m}
\]
giving an ideal quarter-wave dipole element length of:
\[
L\approx\frac{\lambda}{4}\approx73.6\text{ cm}.
\]
Received signal strength increased as element length was increased from 50 cm to 70 cm. The strongest observed signal occurred at approximately 70 cm, with a peak near −32 dBFS. Signal strength then gradually decreased as element length was increased beyond approximately 75 cm.
The waterfall also became brighter as antenna length increased, and several weaker signals became easier to observe.
Conclusion: The experiment showed that antenna element length has a measurable effect on received RF signal strength. Maximum observed reception occurred near 70–75 cm, reasonably close to the calculated quarter-wave length of 73.6 cm for 101.9 MHz. The experiment also showed that improving antenna coupling can increase reception of both desired and undesired RF energy. Because the measurements were performed indoors and using SDR display levels rather than direct impedance measurements, they should not be interpreted as a precise measurement of antenna resonance.
