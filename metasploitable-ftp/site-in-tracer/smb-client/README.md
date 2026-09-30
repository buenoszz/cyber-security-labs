# Laboratório: Enumeração e Força Bruta SMB no Metasploitable

## 🎯 Objetivo
Realizar um processo completo de reconhecimento (enumeração) e testes de autenticação por força bruta em um ambiente de laboratório isolado, focando no serviço SMB (porta 445) da máquina alvo (Metasploitable).

## 🛠️ Ferramentas Utilizadas
* **Kali Linux** (Máquina Atacante)
* **Metasploitable** (Alvo em `192.168.56.104`)
* **Enum4Linux** (Enumeração de informações e usuários do sistema)
* **Medusa** (Módulo `smbnt` para testes de credenciais)
* **Wordlists** (`usuarios.txt` e `senhas.txt`)

🔍 Fase 1: Reconhecimento e Enumeração
Antes de iniciar qualquer teste de credenciais, o primeiro passo foi coletar inteligência sobre o alvo utilizando o Enum4Linux para mapear informações do sistema operacional, políticas e possíveis nomes de usuários válidos. Os dados coletados foram salvos em um arquivo de texto para análise e estruturação das próximas etapas.

💻 Fase 2: Ataque de Força Bruta (Medusa)
Munido com a lista de usuários extraída na fase de enumeração, utilizei o Medusa com o módulo específico para o protocolo SMB (smbnt) para realizar os testes automatizados de login.

No terminal do Kali Linux, executei o seguinte comando:

medusa -h 192.168.56.104 -U usuarios.txt -P senhas.txt -M smbnt -t 2 -T 50

📸 Evidência do Laboratório
O terminal registrou com sucesso a validação da credencial correta (ACCOUNT FOUND), garantindo acesso administrativo ao compartilhamento ADMIN$ do alvo:

<img width="1291" height="552" alt="image" src="https://github.com/user-attachments/assets/d00896af-3c21-4349-9fbf-c7f20251167a" />


📌 O que foi aprendidoA importância da enumeração prévia (com ferramentas como o Enum4Linux) para alimentar testes de força bruta com usuários reais, aumentando a eficiência do processo.
  O funcionamento do protocolo SMB e como serviços de compartilhamento mal configurados ou com credenciais padrão (msfadmin:msfadmin) representam vetores críticos de intrusão.  
  Como auditar e documentar testes de credenciais de forma segura e controlada em laboratórios isolados.
