# dotenv

This is a modified version of the [official Tilt dotenv extension](https://github.com/tilt-dev/tilt-extensions/blob/master/dotenv/README.md) created by [ln](https://github.com/tachiniererin). Instead of mutating the process environment, this extension _returns_ the environment variables as a dictionary. This allows the use case of, for example, injecting the environment variable dictionary in your Tilt resources.

dotenv reads `.env` or another specified file and loads the key value pairs into the environment. Supports multi-line strings wrapped with double-quotes (`"`).

## Usage

```py
load('ext://dotenv', 'dotenv')

env_local = dotenv(".env.local")

# then, it can be used in a service:
local_resource(
    "app",
    serve_cmd="bun dev",
    env=env_local,
)
```

## Acknowledgments

All original work was created by, and credit goes to, [ln](https://github.com/tachiniererin).
