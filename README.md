# llama-swap

A minimal repository for the local llama-swap project documentation. To use with [Llama-swap](https://github.com/mostlygeek/llama-swap)

## Includes

- How to get `llama-swap`
- How to keep it up to date with a script
- Configuration of some models used on my humble PC

## Environment this is used on

- AMD Ryzen 5 5600X
- AMD Radeon RX 6800 16GB (Reference design by Sapphire)
- 32 GB DDR4 - 3600 MHz

## Running llama-swap on windows

[update-llamaswap.ps1](update-llamaswap.ps1) can be used to install `llama-swap` on Windows. It will do the steps outlined in the [Updater script](#updater-script) section

```posh
llama-swap -watch-config -config c:\Users\<user>\code\llama-swap\config.yaml
```

## Files

- `gpt-oss.gbnf` – the grammar file for the GPT-OSS parser. See the [gpt-oss.gbnf](gpt-oss.gbnf) file for details.
- `config.yaml` – configuration file. See the [config.yaml](config.yaml) file for details.


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

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
