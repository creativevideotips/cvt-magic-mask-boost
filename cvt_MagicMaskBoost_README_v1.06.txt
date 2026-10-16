cvt MagicMask Boost - v1.06
Created by Chadwick / Creative Video Tips (https://creativevideotips.com). Free to share, not for resale.

Install: copy only the cvt_MagicMask_<n>_Setup files into
~/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Macros/
and restart DaVinci Resolve. Remove the previous version's files from Macros
first, so the Effects library doesn't list both.
The In and Out macros are not installed: each Setup file already contains its
own copy of both. Keep In/Out here as the source files for editing and for
building custom chains (copy one into Macros only when you need it).

Files
- cvt_MagicMaskBoost_In_1..5_v1.00, In_6_v1.01  (not installed) Crop box + upscale (STEP 1). Upscale filter defaults to Lanczos.
- cvt_MagicMaskBoost_Out_1..6_v1.00  (not installed) Downscale + place back + alpha-only bitmap (STEP 2). Downscale filter defaults to Linear.
- cvt_MagicMask_1..5_Setup_4K_v1.03 Drops In -> Magic Mask -> Out -> Saver in a row at defaults,
                                     inside a teal underlay labelled MagicMaskBoost_1..5_4K.
- cvt_MagicMask_6_Setup_6K_v1.04     The same for pair 6, inside a navy underlay labelled
                                     MagicMaskBoost_6_6K.
Pairs 1-5 upscale to 3840 wide (UHD); pair 6 upscales to 6144 wide (6K).

Notes
- Saver output path starts with the Fusion Path Map entry Savers:
  Create it once: Fusion > Fusion Settings > Path Map > New. From = Savers:  To = your projects folder (keep the trailing slash).
  Resulting path: Savers:<Project Name>/Savers/<Timeline_Clip_Source>/..._saver<n>/..._saver<n>..exr
- Magic Mask node in the Setup files uses stock Resolve defaults (Faster, Use Legacy Magic Mask off).
- Existing nodes in a comp keep their old definitions; add fresh copies after updating files.
- The version is in the file name only. The nodes keep their names
  (cvt_MagicMaskBoost_In_1 etc.), so each Out still finds its In.

Changelog
v1.00: first versioned release; same macros as the 2026-10-15 backup, renamed
       with the version number.
v1.01: Setup macros only - each row now sits in a teal MagicMaskBoost_<n>
       underlay so it's clear which nodes belong together. In/Out stay v1.00.
v1.02: Setup macros only - the nodes now sit on the underlay's centre line
       instead of along its top edge.
v1.03: install change only - just the Setup macros go in Fusion/Macros. The
       separate In/Out macros are no longer installed, since every Setup
       already includes them. No macro files changed.
v1.04: pair 6 only - In_6 (v1.01) and Setup_6 (v1.03) now upscale to 6K
       (6144 wide) instead of 8K (7680 wide). Pairs 1-5 and Out_6 unchanged.
v1.05: pair 6 only - Setup_6 is renamed cvt_MagicMask_6_Setup_6K (v1.04) and
       its underlay is now navy, labelled MagicMaskBoost_6_6K, so the 6K row
       is easy to tell apart from the teal UHD rows.
v1.06: Setups 1-5 are renamed cvt_MagicMask_<n>_Setup_4K (v1.03) and their
       underlays are labelled MagicMaskBoost_<n>_4K, matching the 6K naming
       of pair 6. "4K" here means UHD, 3840 wide. Nodes and settings unchanged.
