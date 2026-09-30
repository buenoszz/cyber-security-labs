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

<img width="629" height="475" alt="image" src="https://github.com/user-attachments/assets/20f07f6d-4a12-41d0-a71f-4f0b51eab07f" />


3. Criação da Wordlist
Criei um arquivo de texto (senhas.txt) contendo uma lista de possíveis senhas e usuários comuns para realizar o teste de autenticação.

<img width="516" height="101" alt="image" src="https://github.com/user-attachments/assets/06349521-14da-45b3-bb90-4c1a37749d48" />


5. Execução do Ataque de Força Bruta (Medusa)
Utilizei o Medusa no terminal para testar as combinações de usuário e senha contra o serviço de FTP do Metasploitable. O comando utilizado foi semelhante a este:

medusa -h  -u msfadmin -P senhas.txt -M ftp

4. Resultado e Acesso Conquistado 🎉
O Medusa testou as entradas da wordlist e encontrou a senha correspondente com sucesso! Com as credenciais validadas, foi possível estabelecer uma conexão FTP com o alvo.

<img width="1297" height="534" alt="image" src="https://github.com/user-attachments/assets/2916dec1-480a-4a73-97af-83bc6606e292" />

## 📌 O que foi aprendido
* **Identificação de Portas e Serviços:** Compreensão de como o serviço de FTP (porta 21) é executado no Metasploitable e quais respostas ele retorna durante tentativas de autenticação.
* **Validação de Contas Padrão:** Constatação prática de que credenciais padrão de fábrica (como as do ambiente Metasploitable) são o vetor mais rápido de comprometimento em auditorias de segurança.
* **Diferença de Protocolos:** Perceber como cada serviço (`http`, `smbnt` e o FTP) lida com conexões paralelas e restrições de tentativas, exigindo módulos específicos no Medusa para cada tipo de alvo.



