Synthetic Seismic Modelling and Wiener Deconvolution

**Overview:**

This project simulates the fundamental convolutional model of seismic trace, demonstrates how seismic signal is generated from geological boundaries
and how Wiener Deconvolution can be used to recover reflectivity from noisy data.

**Theoretical Background:**

The seismic trace $s(t)$ is modeled as the convolution of a reflectivity series $r(t)$ and a source wavelet $w(t)$:

$$s(t) = r(t) * w(t)$$

**The Challenge:**

In the frequency domain, performing a simple mathematical division $S(f) / W(f)$ leads to instability and "noise explosion" 
because the wavelet (Ricker wavelet used here) value approaches to zero at high frequencies.

**Solution: Wiener Deconvolution**

To handle the challenge, Wiener filter was added in frequency domain. It introduces a stabilization factor $\alpha$
that represents the Noise-to-Signal ratio:

$$G(f) = \frac{W^*(f)}{|W(f)|^2 + \alpha}$$

**Workflow:**

1. Reflectivity Generation: 1D series that represent geological boundaries.
2. Wavelet generation: A zero-phase Ricker Wavelet
3. Convolution: convolved the reflectivity with the wavelet
4. Random noise: added random noise
5. Processing: Transformed the signal to frequency domain using FFT, applied the Wiener Filter to suppress noise.

**Key Results:**

The Final output demonstrates that despite significant noise, Wiener filter can collapse noisy wavelet into distinct spikes that align with original geology.


**References:**

-Shearer, P. M. (2009). Introduction to Seismology. Cambridge University Press. (Physics of the convolutional model).

-Yilmaz, Ö. (2001). Seismic Data Analysis. Society of Exploration Geophysicists. (Mathematical theory of Deconvolution).

-Stein, S., & Wysession, M. (2003). An Introduction to Seismology, Earthquakes, and Earth Structure.

-https://en.wikipedia.org/wiki/Wiener_deconvolution (Accessed: March 2026)
