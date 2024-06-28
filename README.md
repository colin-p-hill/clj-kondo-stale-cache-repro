# Environment

- Windows 11 Pro
- PowerShell 7.4.2
- deps.clj 1.11.3.1463
- clj-kondo v2024.05.24

# Steps

1. Run `clj-kondo --lint "$(clojure -Spath)" --dependencies --parallel --copy-configs`
2. Run `clj-kondo --lint src`

   Result:
   ```
   src\example\repro.clj:4:2: warning: Unresolved var: insta/transform
   linting took 10ms, errors: 0, warnings: 1
   ```
3. Run `clj-kondo --lint src --cache false`
   
   Result:
   ```
   linting took 9ms, errors: 0, warnings: 0
   ```
