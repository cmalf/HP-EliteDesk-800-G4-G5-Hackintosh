# Framebuffer Guide for HP EliteDesk 800 G4/G5 UHD 630

This document defines the recommended **DisplayPort (DP)** framebuffer baseline for the **HP EliteDesk 800 G4/G5** family in both **35W** and **65W** variants.

The recommendations in this guide apply to systems using **Intel UHD 630** and are split by CPU generation:

- **Gen 8** should use `0000923E` as the stable baseline.
- **Gen 9** should use `07009B3E` based on real-world testing provided by **JimiZhou**.

For both generations, the most suitable boot-args for this DP configuration are:

```text
keepsyms=1 igfxonln=1 igfxfw=2
```

## Scope

This framebuffer setup is intended for the following systems:

- HP EliteDesk 800 G4 / G5
- 35W and 65W variants
- Intel UHD 630 iGPU
- DisplayPort output

This is a **DisplayPort-focused** baseline and should not be treated as a universal HDMI or DVI mapping.

## Recommended Baseline

| Generation | Target systems | Recommended `AAPL,ig-platform-id` | Boot-args | Output | Status |
|---|---|---|---|---|---|
| Gen 8 | HP EliteDesk 800 G4/G5 35W/65W | `0000923E` | `keepsyms=1 igfxonln=1 igfxfw=2` | DP | Stable baseline **[Notes](#gen-8)**|
| Gen 9 | HP EliteDesk 800 G4/G5 35W/65W | `07009B3E` | `keepsyms=1 igfxonln=1 igfxfw=2` | DP | Recommended from JimiZhou testing |



## DeviceProperties Path

Apply the values below under:

```text
DeviceProperties -> Add -> PciRoot(0x0)/Pci(0x2,0x0)
```

## Framebuffer Table

| Key | Type | Gen 8 | Gen 9 |
|---|---|---|---|
| `AAPL,GfxYTile` | Data | `01000000` | `01000000` |
| `AAPL,ig-platform-id` | Data | `0000923E` | `07009B3E` |
| `framebuffer-con0-busid` | Data | `01000000` | `01000000` |
| `framebuffer-con0-enable` | Data | `01000000` | `01000000` |
| `framebuffer-con0-flags` | Data | `C7030000` | `C7030000` |
| `framebuffer-con0-index` | Data | `01000000` | `01000000` |
| `framebuffer-con0-type` | Data | `00080000` | `00080000` |
| `framebuffer-con1-busid` | Data | `02000000` | `02000000` |
| `framebuffer-con1-enable` | Data | `01000000` | `01000000` |
| `framebuffer-con1-flags` | Data | `C7030000` | `C7030000` |
| `framebuffer-con1-index` | Data | `02000000` | `02000000` |
| `framebuffer-con1-type` | Data | `00080000` | `00080000` |
| `framebuffer-con2-busid` | Data | `04000000` | `04000000` |
| `framebuffer-con2-enable` | Data | `01000000` | `01000000` |
| `framebuffer-con2-flags` | Data | `C7030000` | `C7030000` |
| `framebuffer-con2-index` | Data | `03000000` | `03000000` |
| `framebuffer-con2-type` | Data | `00080000` | `00080000` |
| `framebuffer-patch-enable` | Data | `01000000` | `01000000` |
| `graphic-options` | Data | `C0000000` | `C0000000` |

## Boot Arguments

Use the following boot-args for **both Gen 8 and Gen 9**:

```text
keepsyms=1 igfxonln=1 igfxfw=2
```

## OpenCore Snippets

### DeviceProperties

```xml
<key>DeviceProperties</key>
<dict>
  <key>Add</key>
  <dict>
    <key>PciRoot(0x0)/Pci(0x2,0x0)</key>
    <dict>
      <key>AAPL,GfxYTile</key>
      <data>AQAAAA==</data>
      <key>AAPL,ig-platform-id</key>
      <data><!-- Gen 8: AACSPg== | Gen 9: BwCbPg== --></data>
      <key>framebuffer-con0-busid</key>
      <data>AQAAAA==</data>
      <key>framebuffer-con0-enable</key>
      <data>AQAAAA==</data>
      <key>framebuffer-con0-flags</key>
      <data>xwMAAA==</data>
      <key>framebuffer-con0-index</key>
      <data>AQAAAA==</data>
      <key>framebuffer-con0-type</key>
      <data>AAgAAA==</data>
      <key>framebuffer-con1-busid</key>
      <data>AgAAAA==</data>
      <key>framebuffer-con1-enable</key>
      <data>AQAAAA==</data>
      <key>framebuffer-con1-flags</key>
      <data>xwMAAA==</data>
      <key>framebuffer-con1-index</key>
      <data>AgAAAA==</data>
      <key>framebuffer-con1-type</key>
      <data>AAgAAA==</data>
      <key>framebuffer-con2-busid</key>
      <data>BAAAAA==</data>
      <key>framebuffer-con2-enable</key>
      <data>AQAAAA==</data>
      <key>framebuffer-con2-flags</key>
      <data>xwMAAA==</data>
      <key>framebuffer-con2-index</key>
      <data>AwAAAA==</data>
      <key>framebuffer-con2-type</key>
      <data>AAgAAA==</data>
      <key>framebuffer-patch-enable</key>
      <data>AQAAAA==</data>
      <key>graphic-options</key>
      <data>wAAAAA==</data>
    </dict>
  </dict>
</dict>
```

### NVRAM Boot-args

```xml
<key>NVRAM</key>
<dict>
  <key>Add</key>
  <dict>
    <key>7C436110-AB2A-4BBB-A880-FE41995C9F82</key>
    <dict>
      <key>boot-args</key>
      <string>keepsyms=1 igfxonln=1 igfxfw=2</string>
    </dict>
  </dict>
</dict>
```

## Generation Notes

### Gen 8

For **Gen 8** systems in the HP EliteDesk 800 G4/G5 family, use:

```text
AAPL,ig-platform-id = 0000923E
```

This is the recommended **stable baseline** for DisplayPort-based UHD 630 systems in this family.

### Gen 9

For **Gen 9** systems in the HP EliteDesk 800 G4/G5 family, use:

```text
AAPL,ig-platform-id = 07009B3E
```

This is the recommended baseline based on testing reported by **JimiZhou**, including improved idle behavior, cleaner GPU activity, and stable VideoToolbox support on DP output.

## Notes

- This mapping is intended for **DisplayPort** setups.
- All three connector types use `00080000`, which corresponds to DP in this baseline.
- For this HP EliteDesk 800 family, the safest baseline is to split framebuffer recommendations by CPU generation rather than forcing a single shared platform-id.
> [!TIP]
> <a id="gen-8"></a>
- For **Gen 8** users, `0000923E` with `keepsyms=1 igfxonln=1 igfxfw=2` remains the recommended stable starting point. <a id="gen-8"></a>
- If a **Gen 8** system shows screen glitches, brief display corruption, or a blank screen when the DisplayPort cable is unplugged and reconnected, or if this behavior happens occasionally, try switching to `07009B3E` while keeping the same boot-args: `keepsyms=1 igfxonln=1 igfxfw=2`.
- `07009B3E` is the more flexible option overall, because it can be used on both **Gen 8** and **Gen 9** systems. For **Gen 8**, keep `0000923E` as the stable default, but use `07009B3E` as the preferred fallback when the default framebuffer does not behave cleanly.


## Troubleshooting

Use the checks below if the system boots but graphics behavior is not clean:

- Confirm that `AAPL,ig-platform-id` matches the correct CPU generation.
- Confirm that the connector type for `con0`, `con1`, and `con2` remains `00080000` for DP.
- Confirm that `boot-args` contains `keepsyms=1 igfxonln=1 igfxfw=2`.
- If graphics acceleration appears present but idle power, WindowServer usage, or GPU Busy remains unusually high, re-check the platform-id first before testing extra boot-args.
- Only add extra boot-args such as `igfxagdc=0` or `darkwake=2`/`darkwake=3` when troubleshooting a specific display-policy or sleep/wake issue.

## Special Thanks

Special thanks to [@JimiZhou](https://github.com/JimiZhou) for the detailed testing, comparative results, and validation work that helped confirm `07009B3E` as the recommended Gen 9 DisplayPort framebuffer baseline for this HP EliteDesk 800 G4/G5 UHD 630 family.
More Detail: [issues/10](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/issues/10).
