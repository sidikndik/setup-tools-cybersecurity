## Install Visual Studio Code

Tambahkan repo Microsoft:
```bash
sudo apt update
sudo apt install -y wget gpg apt-transport-https
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/ms.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/ms.gpg] https://packages.microsoft.com/repos/vscode stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
```
Install VSCode:
```bash
sudo apt update
sudo apt install -y code
```

## Install Docker

Pastikan paket lama tidak bentrok:
```bash
sudo apt remove -y docker docker-engine docker.io containerd runc
```

Tambahkan repo Docker resmi:
```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg lsb-release

sudo install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/debian/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
"deb [arch=amd64 signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/debian bookworm stable" | \
sudo tee /etc/apt/sources.list.d/docker.list

sudo apt update
```

install
```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Tambahkan user ke grup docker:
```bash
sudo usermod -aG docker $USER
```

logout dulu (restart laptopnya)


## Install Golang 1.25

Download Go 1.25:
```bash
wget https://go.dev/dl/go1.25.0.linux-amd64.tar.gz
```
Hapus instalasi Go lama:
```bash
sudo rm -rf /usr/local/go
```
Install:
```bash
sudo tar -C /usr/local -xzf go1.25.0.linux-amd64.tar.gz
```
Set PATH:
```bash
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.zshrc
source ~/.zshrc
```
cek:
```bash
go version
```

## Install Node.js 24.x

hapus nodejs sebelumnya:
```bash
sudo apt remove -y nodejs npm
sudo apt autoremove -y
```

Jalankan script NodeSource resmi:
```bash
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
```

Install Node.js:
```bash
sudo apt install -y nodejs
```

Cek versi:
```bash
node -v
npm -v
```
