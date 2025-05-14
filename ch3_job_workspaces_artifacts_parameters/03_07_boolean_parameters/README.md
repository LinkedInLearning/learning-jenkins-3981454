# 03_07 Boolean parameters

Create a freestyle job with one build step.

Add a boolean parameter called `RUN_TESTS`.

## WINDOWS SYSTEMS

If you are running Jenkins on a Windows system:

1. Select the `Execute Windows batch command` build step
2. Enter the following for the command:

```cmd
@echo OFF
echo "RUN_TESTS = %RUN_TESTS%"
if "%RUN_TESTS%"=="true" (
    echo "RUNNING TESTS!"
) else (
    echo "No tests will be run"
)
```

[Follow this link for more details on Windows.](WINDOWS.md)

## MacOS, Linux, and Docker

If you are running Jenkins on MacOS, Linux, or Docker:

1. Select the `Execute shell` build step.
2. Enter the following for the command:

```bash
#!/bin/bash
echo "RUN_TESTS = $RUN_TESTS"
if [ "$RUN_TESTS" = "true" ];
then
    echo "RUNNING TESTS!";
else
    echo "No tests will be run...";
fi
```

[Follow this link for more details on MacOS, Linux, and Docker.](MAC_LINUX_DOCKER.md)

<!-- FooterStart -->
---
[← 03_06 Choice parameters](../03_06_choice_parameters/README.md) | [03_08 Schedule jobs →](../03_08_schedule_jobs/README.md)
<!-- FooterEnd -->
