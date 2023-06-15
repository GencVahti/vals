# vals

`vals` is a tool for managing configuration values and secrets.

It supports various backends including:

- Vault
- AWS SSM Parameter Store
- AWS Secrets Manager
- AWS S3
- GCP Secrets Manager
- [Google Sheets](#google-sheets)
- [SOPS](https://github.com/mozilla/sops)-encrypted files
- Terraform State
- CredHub(Coming soon)

- Use `vals eval -f refs.yaml` to replace all the `ref`s in the file to actual values and secrets.
- Use `vals exec -f env.yaml -- <COMMAND>` to populate envvars and execute the command.
- Use `vals env -f env.yaml` to render envvars that are consumable by `eval` or a tool like `direnv`


# Install `vals` on ubuntu-22.04 LTS

    wget https://github.com/GencVahti/vals/raw/main/vals
    chmod 755 vals
    mv vals /usr/local/bin/



# CLI

```
vals is a Helm-like configuration "Values" loader with support for various sources and merge strategies

Usage:
  vals [command]

Available Commands:
  eval          Evaluate a JSON/YAML document and replace any template expressions in it and prints the result
  exec          Populates the environment variables and executes the command
  env           Renders environment variables to be consumed by eval or a tool like direnv
  get           Evaluate a string value passed as the first argument and replace any expressiosn in it and prints the result
  ksdecode      Decode YAML document(s) by converting Secret resources' "data" to "stringData" for use with "vals eval"
  version       Print vals version

Use "vals [command] --help" for more information about a comman
```