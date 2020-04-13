Pd practical 2012-10-11
=======================
 
Hi all,

Here is the binaural mixing program to complete.
Try to finish it for this Thursday, before the next practical.  Please feel free to contact through this email if you have any questions.

I also included a WAV file of an audio example to be processed.  It is a voice that I recorded some years ago.  The recording is completely raw without any effect.  You can use any kind of other sound that you wish as long as it is a mono wav file without effects.


**Some information:**

Stages (1), (2) and (3) are finalized.  You just need to add a stage (4), which will handle the filtering.

You should first use a function to read the arraySrc, like "tabplay~".
To apply the filter you have to use a convolution.  You may apply it in the time or the frequency domain.  The frequency domain is usually more efficient as it allows the use of the FFT (Fast Fourier Transform).  Although "FIR~" is chiefly designed to apply a Finite Impulse Response filter, it is also capable of applying a simple FFT convolution in an effective fashion.

An important point is that HRTF does not provide the intensity decrease with the distance in accordance to the Inverse Square Law (http://en.wikipedia.org/wiki/Inverse-square_law).  You should then use the "dist_m" variable from the stage (2) to apply this effect in the stage (4).
The use a variable in Pd you can use the function "r" (which stands for "receive") followed by the variable name.

The last stage should be a "dac~" module in order to transmit the sound to your audio interface.

Don't forget to tick the "compete audio" option in the main application window in order to hear some sound.

These explanations are rather long, but the stage (4) is rather small and straightforward if you follow these steps.

*Extra:*<br>
- If you wish to observe the shape of the HRTF (HRIR actually) file, you can use Audacity to import it:
- File > Import > Raw Data...
- Use: 32 bit float; Little-endian; mono; 16 bytes offset; 44100 sample rate

Good luck to you all!<br>
Marc