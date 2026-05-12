# zsh-Volatility3-auto-completion
Little script for getting auto completion for Volatility 3 plugins name

# Install
Here is how I install it:
1. I create a new hidden directory: `mkdir -p ~/.zsh/completions`
2. Download the completion script and place it inside the newly created directory: `curl https://raw.githubusercontent.com/TechieNeurons/zsh-Volatility3-auto-completion/refs/heads/main/_volpy -o ~/.zsh/completions`
3. **!!!! WARNING !!!!** If your Volatility 3 executable path is not: `/opt/volatility3/vol.py` you **MUST** change the line: `local VOL_PATH="/opt/volatility3/vol.py"` to reflect your Volatility 3 executable path
4. Modifying the `~/.zshrc` file:
```bash
# 1. Add this line above the "compinit" line
fpath=(~/.zsh/completions $fpath)

# 2. AFTER the "compinit" line
# Map your executable to the script
# CHANGE '/opt/volatility3/vol.py' to your actual path/filename
# If you renamed it to 'vol3', use 'compdef _volpy vol3'
compdef _volpy /opt/volatility3/vol.py
```
5. Reloading config without reboot of the zsh session: `source ~/.zshrc`