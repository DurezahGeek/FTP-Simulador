# Projeto Packet Tracer: Verificação e Configuração de Interfaces de Rede e FTP

## ✅ Objetivo Geral

Realizar a configuração de interfaces de rede entre um PC, um roteador e um servidor, verificar o funcionamento da rede e simular um acesso FTP a uma pasta compartilhada (semelhante a um mount point) utilizando o Cisco Packet Tracer.

---

## 🛠️ Equipamentos Utilizados

- 1 PC (PC0)
- 1 Roteador (Router0)
- 1 Servidor (Server0)
- 1 Switch (opcional)
- Cabos **Copper Straight-Through**

---

## 🔧 Passo a Passo

### 1. Adicionar Equipamentos

1. Adicione os dispositivos à topologia.
2. Conecte-os usando cabos **Copper Straight-Through** da seguinte forma:
- PC ↔ Switch (opcional, ou direto no roteador)
- Servidor ↔ Switch
- Switch ↔ Roteador (FastEthernet0/0, por exemplo)


> 💡 O Switch é opcional, mas recomendado para simular um ambiente corporativo real.

---

### 2. Configurar IPs Manualmente

#### 📍 PC

- IP Address: `192.168.1.2`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.1.1`

#### 📍 Servidor

- IP Address: `192.168.1.3`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.1.1`

#### 📍 Roteador
Abra o CLI e execute os comandos:

```bash
enable
configure terminal
interface fastethernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
```

---

### 3. Verificar Status da Interface de Rede (PC)

#### No PC:

Vá para Desktop → Command Prompt e execute o comando:

```bash
ipconfig
```
✔️ Verifique se o IP, máscara e gateway estão corretos.

---


### 4. Simular Servidor FTP (Server0)

1. Vá para **Server0 → Services → FTP**.
2. Habilite o serviço FTP.
3. Crie um usuário fictício:

| Campo     | Valor       |
|-----------|-------------|
| Username  | usuario     |
| Password  | senha123    |
| Permissão | Read & Write |

📁 A pasta FTP simulada será `/ftp`.

---

### 5. Simular Montagem FTP no PC0

1. No **PC0 → Desktop → Command Prompt**, digite o seguinte comando:

```bash
ftp 192.168.1.3
```

2. Digite o nome de usuário e senha configurados:

```bash
Connected to 192.168.1.3
220 FTP server ready
User (192.168.1.3:(none)): usuario
331 Password required
Password:
230 Logged in
ftp>
```

✔️📁 Agora você está dentro da pasta FTP simulada

## 🖼️ Capturas de Tela

### 🔌 Topologia da Rede
> Estrutura completa com os 1 PC, 1 servidor, switch e roteador conectados.
![Topologia da Rede](https://raw.githubusercontent.com/DurezahGeek/FTP-Simulador/refs/heads/main/src/topologia.png)

---

### 💻 PC – Configuração de Rede
> Mostra o modelo, IP, MAC Address e Gateway configurado no PC.
![PC Detalhes](https://raw.githubusercontent.com/DurezahGeek/FTP-Simulador/refs/heads/main/src/pc.png)

---

### 💻 Servidor – Configuração de Rede
> Mostra o modelo, IP, MAC Address e Gateway configurado no servidor.
![Servidor Detalhes](https://raw.githubusercontent.com/DurezahGeek/FTP-Simulador/refs/heads/main/src/servidor.png)

---

### 📶 Switch Detalhes
> Apresenta o modelo do switch (2960) e as portas que estão conectadas aos dispositivos.
![Switch Detalhes](https://raw.githubusercontent.com/DurezahGeek/FTP-Simulador/refs/heads/main/src/switch.png)

---

### 🌐 Roteador Detalhes
> Informações do roteador (2911), portas conectadas e IP configurado na interface.
![Roteador Detalhes](https://raw.githubusercontent.com/DurezahGeek/FTP-Simulador/refs/heads/main/src/roteador.png)

## 👩‍💻 Autora

Biatriz Gomes

---
