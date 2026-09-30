# Laboratório: Ataque de Força Bruta em FTP (Metasploitable)

## 🎯 Objetivo
Realizar testes de invasão em um laboratório isolado utilizando o **Metasploitable** como alvo vulnerável, focando no serviço de FTP para testar a robustez de credenciais através de ataque de força bruta.

## 🛠️ Ambiente e Ferramentas
* **Máquina Atacante:** Kali Linux (VirtualBox)
* **Máquina Alvo:** Metasploitable 2 (VirtualBox - rede interna/isolada)
* **Ferramentas utilizadas:** 
  * `Medusa` (Ferramenta de força bruta paralela)
  * Arquivo `.txt` contendo a wordlist personalizada de senhas.

📝 Passo a Passo da Execução
1. Descoberta e Enumeração do Alvo
Primeiro, identifiquei o IP da máquina alvo na rede interna do laboratório e verifiquei quais portas e serviços estavam abertos (com foco na porta 21 do FTP).

2. Criação da Wordlist
Criei um arquivo de texto (senhas.txt) contendo uma lista de possíveis senhas e usuários comuns para realizar o teste de autenticação.

3. Execução do Ataque de Força Bruta (Medusa)
Utilizei o Medusa no terminal para testar as combinações de usuário e senha contra o serviço de FTP do Metasploitable. O comando utilizado foi semelhante a este:

medusa -h  -u msfadmin -P senhas.txt -M ftp

4. Resultado e Acesso Conquistado 🎉
O Medusa testou as entradas da wordlist e encontrou a senha correspondente com sucesso! Com as credenciais validadas, foi possível estabelecer uma conexão FTP com o alvo.
