This project presents a novel **time-domain complex-valued wave equation** for modelling viscoelastic wave propagation in isotropic, homogeneous media with frequency-independent $Q$ attenuation. Building upon the methodology of [Yang & Zhu (2008)](https://doi.org/10.1093/gji/ggy323) for visco-acoustic media, we try to extend their approach to the full elastic case by deriving coupled equations for all three displacement components ($u_x$, $u_y$, $u_z$) that account for both P-wave and S-wave attenuation effects. 

Starting from the 3D equations of motion for an isotropic linear-elastic (Cauchy) medium (assuming a Poisson solid, where $\lambda=\mu$), we can introduce the Kolsky-Futterman [Futterman(1962)](https://doi.org/10.1029/JZ067i013p05279) dispersion relation into the frequency-domain elastic wave equations and employ complex-valued analytical wavefields, $\mathbf{U}=\mathbf{u}+i\mathbf{v}$, to separate attenuation and dispersion effects. The logarithmic dispersion term is approximated using a second-order polynomial (with coefficients $a = 5.7356$, $b = -762.1606$, $d = 4.6054 \times 10^4$) [Yang & Zhu (2008)](https://doi.org/10.1093/gji/ggy323), which enables easy transformation back to the time domain. The resulting formulation yields a time-domain, second-order, complex-valued partial differential equation (PDE) where dispersion and dissipation are naturally decoupled. I implement the equations using  complex-valued finite-difference time-domain (FDTD) schemes with staggered-grid discretisation for spatial derivatives and second-order accuracy in time. Numerical validation against homogeneous and layered homogeneous models demonstrates the method's capability to accurately simulate viscoelastic wave propagation with realistic $Q$ values. 

The derived equation provides a computationally efficient framework for viscoelastic seismic modelling, maintaining the key advantages of its visco-acoustic predecessor: **explicit incorporation of the quality factor ($Q$)** and the **natural separation of dispersion and dissipation effects**. This structure significantly simplifies the derivation of $Q$-gradient kernels for **Viscoelastic Full-Waveform Inversion (FWI)** and provides a straightforward mechanism for **attenuation-compensated Reverse-Time Migration (RTM)**. So, this formulation offers significant advantages for seismic imaging and inversion applications. The PDE was successfully tested using numerical simulations on homogeneous and layered models, confirming its accuracy and feasibility for modelling the complex viscoelastic wavefield.

The file **Time Domain Complex-valued ViscoAcoustic Wave Equation.pdf** presents the detailed derivation of the time-domain complex-valed viscoacoustic wave equation as explained in [Yang & Zhu (2008)](https://doi.org/10.1093/gji/ggy323). Simulation results in the **Images** folder are based on the methodology explained in the abstract above.

### ViscoAcoustic Simulation Results 


![wavelet](./Images/Ricker_Wavelet_Hilbert_Transform.png)
![snapshot](./Images/ViscoAcoustic_Snapshot.png)
![combined snapshot](./Images/Combined_ViscoAcoustic.png)
![viscoacoustic effects analysis](./Images/Viscoacoustic_Effects_Analysis.png)
![seismogram](./Images/Seismogram_Comparison.png)




