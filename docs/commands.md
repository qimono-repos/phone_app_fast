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
