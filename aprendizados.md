# O que aprendi: Simulando um Ataque de Brute Force de Senhas com Medusa e Kali Linux

## Sobre o curso

Curso realizado na plataforma DIO (Digital Innovation One), com foco em testes de segurança ofensiva utilizando a ferramenta **Medusa** no ambiente **Kali Linux**, voltado para simulação de ataques de força bruta a serviços de autenticação.

## Principais aprendizados

### 1. Funcionamento de ataques de força bruta
Entendi como ferramentas de automação testam combinações de usuário/senha de forma sistemática contra um serviço de autenticação (SSH, FTP, HTTP, entre outros), até encontrar uma credencial válida.

### 2. Uso prático do Medusa
Aprendi a utilizar os principais parâmetros da ferramenta:
- `-h` → host/IP alvo
- `-u` → usuário a ser testado
- `-P` → caminho da wordlist de senhas
- `-M` → módulo/protocolo do ataque (ex: ssh, ftp, http)

### 3. Importância de wordlists
Compreendi como a qualidade e o direcionamento de uma wordlist impactam diretamente a eficácia de um ataque, e como senhas fracas ou previsíveis facilitam esse tipo de invasão.

### 4. Vetores de vulnerabilidade
Identifiquei os principais fatores que tornam um ambiente vulnerável a esse tipo de ataque:
- Ausência de limite de tentativas de login (rate limiting);
- Falta de bloqueio automático após falhas consecutivas;
- Ausência de autenticação multifator (MFA);
- Senhas fracas ou reutilizadas.

### 5. Medidas de defesa
Aprendi quais contramedidas são mais eficazes para mitigar esse tipo de ameaça:
- Políticas de senha mais rígidas;
- Ferramentas como Fail2ban para bloqueio automático de IPs;
- Autenticação multifator (MFA);
- Monitoramento e geração de alertas a partir de logs de acesso.

### 6. Responsabilidade ética e legal
O curso reforçou que testes desse tipo só podem ser realizados em ambientes próprios ou com autorização formal, respeitando a legislação vigente (Lei Carolina Dieckmann e LGPD).

## Conclusão

Esse aprendizado contribui diretamente para minha atuação como desenvolvedor, permitindo projetar sistemas de autenticação mais seguros desde a concepção, antecipando vetores de ataque comuns antes que cheguem à produção.

---

*Documentação produzida como parte do curso "Simulando um Ataque de Brute Force de Senhas com Medusa e Kali Linux" — DIO (Digital Innovation One).*
