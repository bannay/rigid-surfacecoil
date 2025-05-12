<div id="top"></div>
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/bannay/rigid-surfacecoil">
    <img src="images/logo.png" alt="Logo" width="100" height="100">
  </a>
<br>


<h3 align="center">Rigid Ø20 cm MRI surface RF coil</h3>
</div>

<!-- ABOUT THE PROJECT -->
## **About the project**
 Design and construction of a rigid Ø20 cm surface coil using single layer FR-4. Coil geometry and segmentation are optimized to minimize E-field and reduce PCB manufacturing cost. 

### Designed and simulated with
* [KiCAD 6.02]
* [CST Microwave Studio (EM simulator)]
***

<!-- METHOD -->
## **Design**

<!-- CRITERIA -->
### **Criteria**
* Rigid coil  
* 20 cm diameter  
* Frequency and matching tunable  
* Transmit/receive  

<!-- SEGMENTATION & TUNING -->
### **Coil Segmentation and Tuning**

The coil is intended for use on patients and biological samples with an average relative dielectric constant:

$$
\varepsilon_r = 78
$$

If the coil is used for $^1$H detection at 3 Tesla, the Larmor frequency is:

$$
f_0 = 128.57\ \text{MHz}
$$

This corresponds to a wavelength within the sample or patient of:

$$
\lambda_s = \frac{c}{\sqrt{\varepsilon_r} \cdot f_0} = 26.4\ \text{cm}
$$

A rule of thumb stipulates that the contiguous conductor length of the coil should satisfy:

$$
\frac{\lambda_s}{20} < l < \frac{\lambda_s}{10}
$$

which translates to:

$$
1.32\ \text{cm} < l < 2.64\ \text{cm}
$$

In this example, the coils are intended for $^{13}$C, which has a gyromagnetic ratio approximately four times lower than $^1$H. Thus, at 3 Tesla, the Larmor frequency becomes:

$$
f_0 = 32.15\ \text{MHz}
$$

Applying the same rule of thumb, the maximum conductor length becomes:

$$
5.28\ \text{cm} < l < 10.56\ \text{cm}
$$

The total conductor length is:

$$
l = 2\pi r = 68.83\ \text{cm}
$$

This results in a simulated coil inductance of:

$$
L = 575\ \text{nH}
$$

Given the low resonant frequency, 6 segments were selected:

$$
l_{\text{segment}} \approx 11.47\ \text{cm}
$$

This maintains reasonable tuning capacitor values. Accounting for conductor gaps to solder capacitors, this segmentation adheres to the rule of thumb.

The required lumped capacitance to achieve resonance is:

$$
C = \frac{1}{4\pi^2 f^2 L} = 42.6\ \text{pF}
$$

Given six segments, the total distributed capacitance becomes:

$$
C' = 42.6 \times 6 = 255\ \text{pF}
$$

---

### **Matching**

The ideal matching capacitance has been determined via simulation to be:

$$
C_{\text{match}} = 22\ \text{pF}
$$

This value was verified experimentally (using a human thigh to load the coil). For an unloaded coil, matching capacitance can also be analytically approximated based on the coil's lumped capacitance and DC ohmic resistance.


<p align="right">(<a href="#top">back to top</a>)</p>

***

<!-- CONSTRUCTION & FABRICATION -->
## Construction & Fabrication

<!-- BILL OF MATERIALS -->

### **Bill of materials**

* Capacitors were ceramic non-magnetic, purchased from Knowles Syfer and rated to at least 2kV WVDC. 
* Trimmer capacitors for variable tuning and matching were purchased from Knowles Voltronics (V9000).
* 24 x M5 x 8 mm nylon screws.
* 24 x M5 nylon nuts.
* 24 x M5 washers.

<!-- PCB FABRICATION -->
### **PCB fabrication**

The coil has been designed in CST microwave stuido and exported to KiCAD PCB editor (KiCAD and Gerber files available). The coil is made of 6 x 3 PCB pieces: 
* '1-seg' PCB consists of an arched PCB hosting a single 5 mm thick trace. 
* 'Brace' PCB is an empty FR-4 board which aligns between (under) two neighboring '1-seg' PCBs and mechanically couples them together.
* 'Coupler' PCB has castellated edges and is soldered between (above) two neighboring '1-seg' PCBs to host tuning/matching capacitors and a coaxial cable.

Provided the surface coil is segmented into smaller boards - then fabrication is relatively affordable arriving to 144.45 USD for 12 coils (~12 USD per coil).

The PCBs 1-seg and Brace are mechanically fastened together using nylon screws.

Note, not all couplers need to be solder on if less than 6 segments are required.  

<img src="images/faborder.jpg" alt="faborder" width="504" height="488">
<img src="images/pcb-editor.jpg" alt="pcb-editor" width="504" height="372">

<p align="right">(<a href="#top">back to top</a>)</p>

***

<!-- Images -->
## Images
<img src="images/coil.jpg" alt="coil" width="504" height="405">
<img src="images/benchtest.jpg" alt="benchtest" width="504" height="405">
<img src="images/inbore.jpg" alt="inbore" width="504" height="405">
<img src="images/reflection.jpg" alt="reflection" width="504" height="405">

<p align="right">(<a href="#top">back to top</a>)</p>

***

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<!-- CONTACT -->
## Contact

Mohammed M. Albannay - [@Bannay](https://twitter.com/bannay) - bannay@gmail.com

Project Link: [https://github.com/bannay/rigid-surfacecoil](https://github.com/bannay/rigid-surfacecoil)

<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* [Readme template](https://github.com/othneildrew/Best-README-Template)

<p align="right">(<a href="#top">back to top</a>)</p>

***
