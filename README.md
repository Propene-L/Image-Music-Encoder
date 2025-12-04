# Image Music Encoder
Encode a music into an image without notable changes, and decode it

Tools: OpenCV, scipy.fft, jpeglib, librosa, Pillow, sounddevice
Process Flow:
1. **Encoding**
   - convert image to YCbCr
   - read audio and fft
   - keep only positive frequencies and filter high freq components
   - round, convert to int16 and then binary, split in group of 2 digits
   - encode real part to Cb domain and imaginary part to Cr domain
   - reconstruct image
2. **Decoding**
   - split image to YCbCr
   - get the real and imaginary part from Cb and Cr channels
   - merge results to get the fft results in complex terms
   - get full fft and ifft to get audio

Result: 

<img width="600" height="340" alt="res" src="https://github.com/user-attachments/assets/86e7ae8b-5e83-4df3-a7ca-b763562002e2" />

For more information, please refer to docs/ProjectReport.pdf
