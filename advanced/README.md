# Q-SITE 2026 IBM Advanced Coding Challenge

This folder contains a completed copy of the [organizer's participant notebook](https://github.com/QSITE-Hacks/Q-SITE-2026-IBM-Advanced-Coding-Challenge), its helper module and reference data, and the locally generated `submission/` artifacts. The notebook keeps `RUN_ON_HARDWARE = False` and uses the organizer's labeled fallback datasets. No IBM Quantum job was submitted from this workspace.

## Verified locally

| Check | Result |
| --- | ---: |
| Two-qubit `RXY` gates vs matrix exponentials | max deviation 1.1e-16 |
| Initial wavepacket vs organizer reference | max deviation 4.2e-11 |
| Calibration round trip at L=6 | fidelity 1.000000000000 |
| Electric layer vs exact evolution | max infidelity 1.8e-15 |
| L=8 truncation shift at t=4 | 0.0101 |
| L=8 Trotter error at dt=1, t=4 | 0.0948 |
| L=34 MPS bond-40 vs bond-64 profile | max difference 0.0008 |
| Physics and matched calibration on FakeKingston | 4,958 CZ each, identical per-edge counts |
| Reduced-noise rehearsal at L=6 | raw RMSE 0.0626 to ODR RMSE 0.0111 |
| Organizer fallback at t=8 | raw window RMSE 0.229 to ODR RMSE 0.125 |
| L=6 initial and t=4 Trotter arrays vs organizer grading references | max deviation 1.5e-14 |
| 68-qubit chain selection on FakeKingston, FakeFez, FakeMarrakesh | valid paths, including paths with an excluded qubit |

The local preview for the fallback main run is **12.1/18**, subject to the organizer's **13.5-point fallback cap**. This is a preview from the notebook, not a platform grade. The fallback canary is from another backend/layout and reports `FAIL`; it cannot assess the prepared Kingston chain.

Every notebook code cell completed sequentially with Python 3.12, Qiskit 2.5.2, Qiskit IBM Runtime 0.49.0, and Aer 0.17.2. The optional organizer module `fallfest_grader.py` was absent from the public repository, so its call is skipped locally; submit through the Q-SITE platform for authoritative grading.

## Use

1. Open `schwinger_hadron_participant.ipynb` from this folder in Jupyter with the packages in `requirements.txt` installed. Keep the adjacent `images/`, `reference_data/`, and `challenge_utils.py` folders/files together.
2. Run all cells with `RUN_ON_HARDWARE = False` first. The plot helper skips the backend map when Graphviz is unavailable; this does not affect the circuits.
3. Submit the answer cells to the Q-SITE platform as instructed in the notebook. Keep fallback job IDs labeled as fallback, as they are here.
4. For a full hardware attempt, create an IBM Quantum Open Plan account using [IBM's setup guide](https://quantum.cloud.ibm.com/docs/en/guides/cloud-setup), then [save the account locally](https://quantum.cloud.ibm.com/docs/en/guides/save-credentials) in your own terminal. Do not paste an API key into this notebook or chat. After connecting, refresh the real backend calibration, rerun layout selection and transpilation, verify the canary, and only then set `RUN_ON_HARDWARE = True`. The main and TREX improvement branches are prepared but have not been tested on a real QPU.

The event site lists the coding challenge deadline as **September 25, 2026, 11:59 PM** in its displayed EST/UTC-5 timezone; confirm the effective local deadline on the [Q-SITE dashboard](https://www.qsitehacks.ca/) before submitting.
