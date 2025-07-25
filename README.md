# homebrew-hoprd
Homebrew package for hoprd

## Usage

```bash
brew tap hoprnet/hoprd
brew install hoprd@3.0.0-rc.1

```

## Development

Those instructions are only at development time of the Formula

### Install

- Build hoprd for your architecture and place it in a temp folder
- Build hopli for your architecture and place it in a temp folder
- Change the url of the artifacts at `./Formula/hoprd.rb` to use the temporary artifact
    url "file://#{ENV['HOME']}/Documents/github/hoprnet/dist/bin/hoprd-aarch64-darwin"

```bash
brew install --verbose --debug ./Formula/hoprd@3.0.0-rc.1.rb
brew reinstall --verbose --debug hoprd@3.0.0-rc.1
brew postinstall hoprd@3.0.0-rc.1
```

- Edit manually $(brew --prefix)/etc/hoprd/hoprd.env
- brew services start hoprd

### Uninstall

```bash
brew uninstall --force hoprd@3.0.0-rc.1
```

- Clear cache

```bash
rm -rf $(brew --cache)/*hopr*
rm -rf $(brew --prefix)/Cellar/hoprd
rm -f $(brew --prefix)/bin/hopr{d,li}
rm -rf $(brew --prefix)/etc/hoprd
rm -rf $(brew --prefix)/var/lib/hoprd
rm -f $(brew --prefix)/var/log/hoprd.log
rm -f $(brew --prefix)/var/homebrew/linked/hoprd
brew cleanup -s
```
