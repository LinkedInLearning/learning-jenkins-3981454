# Learning Jenkins, 03-05: String Parameters

Create a freestyle job with one build step.

Add a string parameter for `VERSION_NUMBER`.

## MacOS, Linux, and Docker

If you are running Jenkins on MacOS, Linux, or Docker:

1. Select the `Execute shell` build step.
2. Enter the following for the command:

```bash
#!/bin/bash
echo "VERSION_NUMBER = $VERSION_NUMBER"
```

## Troubleshooting Errors
