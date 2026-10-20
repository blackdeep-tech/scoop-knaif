# Scoop bucket for knaif

[knaif](https://github.com/blackdeep-tech/knaif) turns plain-language requests into validated
commands for local tools, with a small model running on your own PC.

```powershell
scoop bucket add knaif https://github.com/blackdeep-tech/scoop-knaif
scoop install knaif/knaif
knaif models pull knaif-qwen3-4b-v2     # the AI model, ~2.5 GB
knaif skills deps                       # what each skill still needs
```

Windows x64. `bucket/knaif.json` installs the signed release `.zip` published on
[GitHub Releases](https://github.com/blackdeep-tech/knaif/releases) exactly as published, checked
against its sha256, and puts its `bin` folder on your PATH, as the knaif installer does. FFmpeg is
installed with it, because the ffmpeg skill cannot run without it; Scoop suggests the optional
tools of the documents skill.

**Smart App Control.** With it enforcing, Windows blocks the 7-Zip that Scoop unpacks FFmpeg with,
so the install stops at FFmpeg. Install knaif alone instead; the documents skill works, the ffmpeg
skill needs an FFmpeg that Windows allows:

```powershell
scoop install knaif/knaif --independent
```

Update with `scoop update knaif`; uninstalling with `scoop uninstall knaif` keeps your models in
`~/.knaif`. Issues go to [blackdeep-tech/knaif](https://github.com/blackdeep-tech/knaif/issues).
