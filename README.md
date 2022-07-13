# bootstrap-windows

Stuff related to getting Windows set up

## Windows Terminal

### Install

Download `Microsoft.VCLibs.x64.14.00.Desktop.appx` from [here](https://docs.microsoft.com/en-us/troubleshoot/developer/visualstudio/cpp/libraries/c-runtime-packages-desktop-bridge).

Open Powershell as admin, run:

```powershell
Add-AppxPackage .\Microsoft.VCLibs.x64.14.00.Desktop.appx 
```

Then: `choco install microsoft-windows-terminal`

### Customize

If you want the firacode font, do this in powershell: `choco install firacode`

See my `settings.json` for an example of further customizations. Some of them borrowed from [this file](https://gist.github.com/ChrisFrontDev/d0a3642ac35c31e3aa0e97f983de139c).

## WSL

## Install

Open Powershell as admin and run: `wsl --install`

## Map Network Drives

After mapping network drives to drive letters in Windows, mount them in WSL:

```sh
will@spacewalk:/mnt$ ls
c  d  wsl
will@spacewalk:/mnt$ sudo mkdir /mnt/s
will@spacewalk:/mnt$ sudo mkdir /mnt/m
will@spacewalk:/mnt$ sudo mount -t drvfs S: /mnt/s
will@spacewalk:/mnt$ sudo mount -t drvfs M: /mnt/m
will@spacewalk:/mnt$ ls
c  d  m  s  wsl
will@spacewalk:/mnt$
```

## rsync

Some various rsync commands I've run from WSL to get a more reliable file copy than Windows Explorer:

`rsync -Pavr /mnt/s/client_bk/vhs_project /mnt/c/Users/Will/Desktop`

## License

Distributed under the MIT License. See LICENSE for more information.