# llama-swap

A minimal repository for the llama-swap project.

## Running llama-swap on windows
```posh
winget install llama-swap
llama-swap -watch-config -config c:\Users\Ismael\code\llama-swap\config.yaml
```

## Files

- `gpt-oss.gbnf` – the grammar file for the GPT-OSS parser. See the [gpt-oss.gbnf](gpt-oss.gbnf) file for details.
- `config.yaml` – configuration file. See the [config.yaml](config.yaml) file for details.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Updater script

`update-llamaswap.ps1` is a PowerShell script that downloads the latest Windows release of llama-swap from GitHub, extracts it, adds it to the user's PATH, and verifies installation.

### Usage

```powershell
.\update-llamaswap.ps1
```

### How it works

- Uses the GitHub API to fetch the latest release of the `mostlygeek/llama-swap` repository.
- Downloads the `windows_amd64.zip` asset.
- Extracts the ZIP into `C:\Users\<User>\apps\llama-swap`.
- Adds the extraction directory to the user’s `PATH` if it isn’t already present.
- Removes the downloaded ZIP to save space.
- Runs `llama-swap.exe --version` to confirm the installation.

Feel free to modify the `$Owner`, `$Repo`, and `$AssetPattern` variables at the top of the script to point to a different repository or asset if needed.