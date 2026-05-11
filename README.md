# hope-agent-linux-repo

apt + dnf/yum repository for [**Hope Agent**](https://github.com/shiwenwen/hope-agent) · Hope Agent 的 apt / dnf / yum 软件源。

## Install · 安装

### Debian / Ubuntu (apt)

```bash
curl -fsSL https://shiwenwen.github.io/hope-agent-linux-repo/pubkey.gpg | \
  sudo gpg --dearmor -o /usr/share/keyrings/hope-agent.gpg
echo "deb [signed-by=/usr/share/keyrings/hope-agent.gpg] https://shiwenwen.github.io/hope-agent-linux-repo/apt stable main" | \
  sudo tee /etc/apt/sources.list.d/hope-agent.list

sudo apt update
sudo apt install hope-agent
```

### Fedora / RHEL / CentOS (dnf / yum)

```bash
sudo curl -fsSL https://shiwenwen.github.io/hope-agent-linux-repo/rpm/hope-agent.repo \
  -o /etc/yum.repos.d/hope-agent.repo
sudo dnf install hope-agent     # or `sudo yum install hope-agent`
```

> The older `sudo dnf config-manager --add-repo …` form has been removed in dnf5 (Fedora 41+); the `curl` variant above works on dnf4 / dnf5 / yum / zypper alike.

### openSUSE (zypper)

```bash
sudo zypper addrepo https://shiwenwen.github.io/hope-agent-linux-repo/rpm/hope-agent.repo
sudo zypper install hope-agent
```

## Key info · 密钥信息

- Algorithm: ed25519
- Fingerprint: `5F80 16D5 0633 E725 909E  9AD7 F0F6 6A31 DFAA EA08`
- Expires: 2027-05-11 (1 year)

## Note · 说明

This repository is **auto-maintained by CI** from the main repo's templates ([`linux-repo/`](https://github.com/shiwenwen/hope-agent/tree/main/linux-repo)). Please file bugs against [shiwenwen/hope-agent](https://github.com/shiwenwen/hope-agent), not here.

本仓库由主仓 CI 自动维护，Bug 反馈请去主仓 [shiwenwen/hope-agent](https://github.com/shiwenwen/hope-agent) 提。

The signing key is intended for repository signing only — it is not the maintainer's personal GPG identity. · 签名密钥只用于仓库签名，不是 maintainer 的个人 GPG 身份。

## Currently supported · 当前支持

- **amd64 / x86_64 only** (arm64 builds may come later)
- **`stable` suite only** (no `unstable` / `testing` channels)

## Links · 链接

- Main repo · 主仓库: https://github.com/shiwenwen/hope-agent
- Releases: https://github.com/shiwenwen/hope-agent/releases
- Issues: https://github.com/shiwenwen/hope-agent/issues
