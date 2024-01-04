# Console Commands

## Powershell

- Run android emulator

```ps2

emulator -avd pixel4

Start-Job -ScriptBlock { emulator -avd pixel4 > $null 2>&1 }

Get-Job

Stop-Job <id-of-the-job>
```


- Run emulator in a single line

```bash
    emulator -avd pixel6 > /dev/null 2>&1 & clj -M:cljd flutter

     clj -M:cljd flutter > output.log 2>&1 &

```

- Starting the REPL ⚡️ using the below command line

```bash
        
pushd /Users/qimono/source/repos/tdd_shrinker ; clojure -Sdeps '{:deps {nrepl/nrepl {:mvn/version,"1.0.0"},cider/cider-nrepl {:mvn/version,"0.28.5"}}}' -M:cljd ; popd

```

## Testing

- Run all tests

```bash
    clj -M:test 
```

- Add Dart Test

    ```bash
        dart pub add -d test || true 
    ```

## Windows : install Cljure using Scoop

- Install Scoop

https://github.com/littleli/scoop-clojure?tab=readme-ov-file

```ps1
    # if you don't have git version control system installed
# it is required for adding new external buckets to your scoop installer
# you can skip this step otherwise
scoop install git

# add scoop bucket for Java
scoop bucket add java

# add scoop bucket with extras, here there is a dependency on visual studio redistributable 'extras/vcredist2022'
scoop bucket add extras

# add scoop bucket for clojure build
scoop bucket add scoop-clojure https://github.com/littleli/scoop-clojure
# install TCK certified Java runtime and compiler if you need to (optional)
scoop install temurin-lts-jdk

# install official clojure tools
scoop install clj-deps

# update to the newest version
scoop update clj-deps
# After successfully running steps above, you should be able to run Clojure with following:

clj

```

## Windows : install Babashka using Scoop

```ps1
    # this had to be poreviously installed with clojure scoop 
    # scoop bucket add scoop-clojure https://github.com/littleli/scoop-clojure
    # scoop bucket add extras

    scoop install babashka
```
# Windows: Location of sdkmanager

This is the most usual location of the sdkmanager when it is installed via Android Studio

C:\Users\%USERNAME%\AppData\Local\Android\Sdk

# Windows: add emulator executable to path

[Environment]::SetEnvironmentVariable("Path", $Env:Path + ";C:\Users\alber\AppData\Local\Android\Sdk\emulator", "User")

## Windows Security : exclude quemu from threats

The Windows Security Protection History page shows a timeline of events, with the most recent events at the top¹. If you see two entries for the same file (`qemu-system-x86_64.exe`), they represent two different actions taken by Windows Security¹.

The "Quarantined" state means that Windows Security has blocked the file and moved it to a safe location where it can't harm your computer¹. The "Restored" state means that you've chosen to restore the file, and Windows Security has moved it back to its original location¹.

If the "Restored" state appears after the "Quarantined" state in the timeline (i.e., it's closer to the top of the page), it means that the file was restored after being quarantined¹. However, if you don't see an action button for the "Quarantined" state, it might be because the file has already been restored¹.

If you're confident that `qemu-system-x86_64.exe` is safe and you want to prevent Windows Security from blocking it in the future, you can add it to the exclusions list⁴. Here's how:

1. Open Windows Security and go to Virus & threat protection.
2. Under Virus & threat protection settings, select Manage settings.
3. Under Exclusions, select Add or remove exclusions.
4. Select Add an exclusion, and then select from files, folders, file types, or process⁴.

Please note that you should only add an exclusion if you're confident that the file or folder is safe⁴. If you're unsure, it's better to leave the file quarantined to protect your system¹.


Source: Conversation with Bing, 1/4/2024
(1) Protection History - Microsoft Support. https://support.microsoft.com/en-us/windows/protection-history-f1e5fd95-09b4-46d1-b8c7-1059a1e09708.
(2) Add an exclusion to Windows Security - Microsoft Support. https://support.microsoft.com/en-us/windows/add-an-exclusion-to-windows-security-811816c0-4dfd-af4a-47e4-c301afe13b26.
(3) WINDOWS DEFENDER IS NOT REMOVING THREATS - Microsoft Community. https://answers.microsoft.com/en-us/windows/forum/all/windows-defender-is-not-removing-threats/edeee6ed-6117-468d-a25b-8f95a7749112.
(4) How to allow blocked file or app on Microsoft Defender Antivirus. https://pureinfotech.com/allow-blocked-file-app-microsoft-defender-antivirus/.
(5) How to Manage Windows Defender Antivirus Found Threats. https://www.majorgeeks.com/content/page/how_to_manage_windows_defender_antivirus_found_threats.html.

## Recomendation: exclude emulator folder

folder: C:\Users\alber\AppData\Local\Android\Sdk\emulator\qemu\


# GIT

## Basic setup

 git config --global user.email jd@gmail.com

 git config --global user.name JohnDoe

 - set the default branch of new repositories to "trunk"

 git config --global init.defaultBranch trunk

# Flutter

- Disable windows desktop , for mobile development

flutter config --no-enable-windows-desktop

- Add flutter executable to path in windows

[Environment]::SetEnvironmentVariable("Path", $Env:Path + ";C:\Users\alber\flutter\bin", "User")
