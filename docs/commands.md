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

It seems like Windows Security has blocked the qemu-system-x86_64.exe file, which is a part of the Android SDK emulator. If you trust this file and want to allow it, you can follow these steps12:

1. Open Windows Security: You can do this by searching for “windows security” in the Taskbar search box and clicking on the result1.

2. Go to the Virus & threat protection tab: Once you’ve opened Windows Security, navigate to this tab1.

3. Click on the Protection history option: This will open a window where you can find all the blocked apps1.

4. Choose the file you want to allow: In your case, this would be qemu-system-x86_64.exe1.

5. Click the Actions button and choose the Allow on device option: After opening the app details, you’ll see these options1.

Confirm your choice: You’ll see a User Account Control (UAC) popup window where you have to click the Yes button1.

After following these steps, the qemu-system-x86_64.exe file should no longer be blocked by Windows Security1.

### Eclude Android folders

1. Open Windows Security and go to Virus & threat protection.
2. Under Virus & threat protection settings, select Manage settings.
3. Under Exclusions, select Add or remove exclusions.
4. Select Add an exclusion, and then select from files, folders, file types, or process.

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
