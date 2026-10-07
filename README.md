# rhosprayVoFDPMFoam

OpenFOAM Foundation 7 based two-material five-equation KT/VOF/DPM solver under development.

## Status

Representation-V2 runtime qualification (CRV3-2C) is complete in its frozen one-dimensional serial scope. Full physical qualification and production CFD are incomplete. Production restart is NOT CERTIFIED. DPM serial transactions and two-rank native fixtures have limited offline qualification; global MPI coupling is incomplete.

The MFC Newtonian viscosity/air–n-decane transport work is an independent prototype in `fitting/integration/mfc_viscosity_adoption_v1`; it is NOT integrated into the active solver. Existing EOS is retained. The positive variable-coefficient work kernel passes scoped conservation tests, with dense small-fixture solve only.

## Contents

Current project source, Make configuration, EOS metadata/coefficients, tests, audit tools, technical reports, latest source/progress documents, independent MFC transport implementation and compact qualification records. `DELIVERY_MANIFEST.json` records original source hashes. Historical sealed archives, runtime binaries, generated objects, dense trajectory outputs, active process locks and third-party dependency installations are excluded. This is a source delivery snapshot, not a production release.

## Build environment

Use the project's OpenFOAM Foundation 7 DP/Int32 environment and its configured compiler. Source the OF7 bashrc first, build the `liquidEOS/library` and `fiveEqThermo` libraries with `wmake libso`, then build the root solver with `wmake`. The root Make/options lists additional OpenFOAM libraries. Existing source assumes the audited OF7 APIs; no compatibility with other OpenFOAM forks is claimed. Tests have individual Make configurations and should be used within their recorded fixture scope. External OpenFOAM libraries and their full source are not bundled.

The transport fit script requires NumPy and CoolProp==8.0.0; place a local installation in the prototype's `property_backend` directory as expected by the script. Prototype verification uses a C++17 compiler. This delivery operation did not rerun solver builds or qualification.

## Provenance and licensing

Preserve the original source license notices. OpenFOAM-derived source retains its existing GNU GPL notices. The independent MFC migration pins commit `3dc5b2f2a1b1b9c25672aa09d4fbfabee21a91e8`; its MIT license is preserved in `MFC_LICENSE`. Transport correlations and assumptions are documented in ADOPTION_STATUS.md. Do not infer a new blanket license for all third-party source/data from this snapshot.

## Progress

See SOLVER_OVERALL_PROGRESS_2026-10-07.txt, LATEST_SOLVER_SOURCE_2026-10-07.txt and WORK_LOG_2026-10-06_CRV3.md. Historical milestone wording is append-only; newer stage gates supersede old progress captures within the explicitly documented scope.
