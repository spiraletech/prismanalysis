# Building PRISM Analysis

The repository is self-contained and reconstructs the current native C++ source before compiling it with MSVC.

## GitHub Actions

Open **Actions → Build PRISM Analysis** and run the workflow manually, or push to `main`.

The workflow:

1. Reassembles the baseline `prism.cpp` from the checked-in source chunks.
2. Applies the True Analyzer patch.
3. Applies the mouse-hover dBFS patch.
4. Applies the CYMATIC / MANDALA / LOTUS semantic-orb patch.
5. Compiles a native Windows x64 GUI executable with MSVC.
6. Publishes `PRISM_LAB_ORBMODES.exe` and the flattened `prism.cpp` as a workflow artifact.

## Native build command

The CI build uses:

```text
cl /nologo /O2 /W3 /EHsc /std:c++17 /MT prism.cpp ^
  /link /SUBSYSTEM:WINDOWS /DYNAMICBASE /NXCOMPAT /HIGHENTROPYVA ^
  user32.lib gdi32.lib ole32.lib winmm.lib kernel32.lib ^
  /OUT:PRISM_LAB_ORBMODES.exe
```

No external runtime service or API key is required by PRISM at runtime.
