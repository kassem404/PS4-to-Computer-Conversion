# Benchmarks

## 1. Geekbench 6.5.0
- Link: https://browser.geekbench.com/v6/cpu/16758539

---

## 2. Glmark2 2023.1

```bash
❯ glmark2
=======================================================
    glmark2 2023.01
=======================================================
    OpenGL Information
    GL_VENDOR:      AMD
    GL_RENDERER:    AMD Radeon Graphics (radeonsi, liverpool, ACO, DRM 3.42, 5.15.15-obsidianx-1.0.0_release)
    GL_VERSION:     4.6 (Compatibility Profile) Mesa 25.1.0-devel (git-d1d2afa3ac)
    Surface Config: buf=32 r=8 g=8 b=8 a=8 depth=24 stencil=0 samples=0
    Surface Size:   800x600 windowed
=======================================================
[build] use-vbo=false: FPS: 3234 FrameTime: 0.309 ms
[build] use-vbo=true: FPS: 5205 FrameTime: 0.192 ms
[texture] texture-filter=nearest: FPS: 4995 FrameTime: 0.200 ms
[texture] texture-filter=linear: FPS: 4852 FrameTime: 0.206 ms
[texture] texture-filter=mipmap: FPS: 4960 FrameTime: 0.202 ms
[shading] shading=gouraud: FPS: 5334 FrameTime: 0.188 ms
[shading] shading=blinn-phong-inf: FPS: 5044 FrameTime: 0.198 ms
[shading] shading=phong: FPS: 5031 FrameTime: 0.199 ms
[shading] shading=cel: FPS: 5169 FrameTime: 0.193 ms
[bump] bump-render=high-poly: FPS: 5193 FrameTime: 0.193 ms
[bump] bump-render=normals: FPS: 5335 FrameTime: 0.187 ms
[bump] bump-render=height: FPS: 4956 FrameTime: 0.202 ms
[effect2d] kernel=0,1,0;1,-4,1;0,1,0;: FPS: 5375 FrameTime: 0.186 ms
[effect2d] kernel=1,1,1,1,1;1,1,1,1,1;1,1,1,1,1;: FPS: 5294 FrameTime: 0.189 ms
[pulsar] light=false:quads=5:texture=false: FPS: 4847 FrameTime: 0.206 ms
[desktop] blur-radius=5:effect=blur:passes=1:separable=true:windows=4: FPS: 2063 FrameTime: 0.485 ms
[desktop] effect=shadow:windows=4: FPS: 2321 FrameTime: 0.431 ms
[buffer] columns=200:interleave=false:update-dispersion=0.9:update-fraction=0.5:update-method=map: FPS: 443 FrameTime: 2.261 ms
[buffer] columns=200:interleave=false:update-dispersion=0.9:update-fraction=0.5:update-method=subdata: FPS: 448 FrameTime: 2.234 ms
[buffer] columns=200:interleave=true:update-dispersion=0.9:update-fraction=0.5:update-method=map: FPS: 626 FrameTime: 1.598 ms
[ideas] speed=duration: FPS: 1896 FrameTime: 0.528 ms
[jellyfish] <default>: FPS: 4328 FrameTime: 0.231 ms
[terrain] <default>: FPS: 972 FrameTime: 1.029 ms
[shadow] <default>: FPS: 3367 FrameTime: 0.297 ms
[refract] <default>: FPS: 1252 FrameTime: 0.799 ms
[conditionals] fragment-steps=0:vertex-steps=0: FPS: 5272 FrameTime: 0.190 ms
[conditionals] fragment-steps=5:vertex-steps=0: FPS: 5372 FrameTime: 0.186 ms
[conditionals] fragment-steps=0:vertex-steps=5: FPS: 5298 FrameTime: 0.189 ms
[function] fragment-complexity=low:fragment-steps=5: FPS: 5354 FrameTime: 0.187 ms
[function] fragment-complexity=medium:fragment-steps=5: FPS: 5400 FrameTime: 0.185 ms
[loop] fragment-loop=false:fragment-steps=5:vertex-steps=5: FPS: 4985 FrameTime: 0.201 ms
[loop] fragment-steps=5:fragment-uniform=false:vertex-steps=5: FPS: 5239 FrameTime: 0.191 ms
[loop] fragment-steps=5:fragment-uniform=true:vertex-steps=5: FPS: 5200 FrameTime: 0.192 ms
=======================================================
                                  glmark2 Score: 4079
=======================================================```

---

# 3. KDiskMark 3.2.0

```bash
KDiskMark (3.2.0): https://github.com/JonMagon/KDiskMark
Flexible I/O Tester (fio-3.39): https://github.com/axboe/fio
--------------------------------------------------------------------------------
* MB/s = 1,000,000 bytes/s [SATA/600 = 600,000,000 bytes/s]
* KB = 1000 bytes, KiB = 1024 bytes

[Read]
Sequential   1 MiB (Q=  8, T= 1):    50.851 MB/s [     49.7 IOPS] < 158255.28 us>
Sequential   1 MiB (Q=  1, T= 1):    52.109 MB/s [     50.9 IOPS] < 20298.90 us>
Random       4 KiB (Q= 32, T= 1):     0.326 MB/s [     81.7 IOPS] < 391023.88 us>
Random       4 KiB (Q=  1, T= 1):     0.303 MB/s [     75.9 IOPS] < 13182.73 us>

[Write]
Sequential   1 MiB (Q=  8, T= 1):    85.271 MB/s [     83.3 IOPS] < 38704.24 us>
Sequential   1 MiB (Q=  1, T= 1):    80.501 MB/s [     78.6 IOPS] <  4524.21 us>
Random       4 KiB (Q= 32, T= 1):    14.712 MB/s [   3678.0 IOPS] < 11072.93 us>
Random       4 KiB (Q=  1, T= 1):     0.960 MB/s [    240.0 IOPS] <    50.96 us>

Profile: Default
Test: 1 GiB (x2) [Measure: 5 sec / Interval: 5 sec]
Date: 2026-02-26 16:29:06
OS: cachyos unknown [linux 5.15.15-obsidianx-1.0.0_release]
Target: / 4% (31.72/748.08 GiB)
