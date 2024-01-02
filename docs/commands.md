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
