### Renovate `regexManagers:dockerfileVersions` applied twice

Our Renovate configuration within `renovate.json` extends two internal presets (`presets/java.json` and `presets/js.json`) which both extend from the same `presets/default.json`.
That default-Preset itself extends from `regexManagers:dockerfileVersions` which adds a Regex Manager for detecting packages within a Dockerfile.
Because we are effectly applying this default-Preset twice the Regex Manager is applied twice and therefore the packages are detected twice which can be seen within the Dependency Dashboard (Screenshot below).

![Screenshot of the Dependency Dashboard showing the packages twice](/dependency-dashboard.png?raw=true "Dependency Dashboard")
