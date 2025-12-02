# binaries-in-AGN
# Description
This repository contains the codes and notebook used in <a href="https://arxiv.org/abs/2504.08033">arXiv:2504.08033</a> to study the dynamical evolution of compact objects embedded in AGN accretion disks.
The project makes use of the pAGN library to construct α-disk models following Sirko & Goodman (2003) and Thompson et al. (2005), and implements a physically motivated scattering algorithm for black hole binaries interacting with the disk.

There are two components:\
\
(i) Disk Models\
Computation of the Sirko–Goodman and Thompson AGN disk profiles using <a href="https://github.com/DariaGangardt/pAGN">pAGN</a> \
\
(ii) Scattering Algorithm\
Implements dynamical friction and accretion forces and evolves the orbit over an arbitrary number of scatterings. Updates: semi-major axis, eccentricity, inclination, argument of periapsis.\

# Requirements
The notebook requires:
Python ≥ 3.9
NumPy
SciPy
Matplotlib
pAGN (AGN disk modelling)
Install dependencies via:
<pre><code>pip install numpy scipy matplotlib pagn</code></pre 

# Running the code
(1) Clone the repository
<pre><code>git clone https://github.com/thomasspieksma/BiAGN.git cd BiAGN </code></pre>

(2) Open the notebook:
<pre><code>jupyter notebook</code></pre>

(3) (Optional, first run only)
Generate disk model files using the provided notebook cells.

(4) Choose disk & set parameters
choose disk:
<pre><code>DISK = "SG" # or "Tho"</code></pre>
set initial conditions (example):
<pre><code>M_00 = 1.0
ms_00 = 1e-4 * M_00
a_00 = 1e6 * M_00
e_00 = 0.2
iota_00 = np.pi/3
theta_00 = np.pi/3
N_00 = 20000
process_00 = "friction" # or "accretion"</code></pre>

(5) Run simulation & view plots
run scattering:
<pre><code>results = scatterings(M_00, ms_00, a_00, e_00, iota_00, theta_00, N_00, process=process_00)</code></pre>
unpack results and plot (notebook contains plotting cell). The code will stop early if orbit becomes unbound, inclination drops below thin-disk thre


# Questions
For questions, feedback or suggestions, please email: <a href="mailto:thomas.spieksma@physics.ox.ac.uk">thomas.spieksma@physics.ox.ac.uk</a>.
# Citing
If you make use of this code, please cite the corresponding paper,
<pre><code> @article{Spieksma:2025wex,
    author = "Spieksma, Thomas F. M. and Cannizzaro, Enrico",
    title = "{In the grip of the disk: dragging the companion through an AGN}",
    eprint = "2504.08033",
    archivePrefix = "arXiv",
    primaryClass = "astro-ph.GA",
    month = "4",
    year = "2025"
}</code></pre>
