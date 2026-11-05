# Simulação Ética de Ataque de Força Bruta com Medusa e Kali Linux

## ⚠️ Aviso Legal e Ético

Este projeto tem **finalidade exclusivamente educacional**. Todos os testes foram realizados em ambiente controlado e de laboratório (máquinas virtuais próprias), **sem envolver sistemas de terceiros ou de produção sem autorização expressa**.

Realizar ataques de força bruta contra sistemas sem autorização é **crime** previsto na Lei nº 12.737/2012 (Lei Carolina Dieckmann) e na Lei Geral de Proteção de Dados (LGPD). Use este conteúdo apenas em ambientes de estudo, CTFs ou testes de penetração devidamente autorizados por contrato.

---

## 🎯 Objetivo

Demonstrar, na prática, como um ataque de força bruta de senhas é executado utilizando a ferramenta **Medusa** no **Kali Linux**, compreendendo:

- O funcionamento técnico da ferramenta e seus parâmetros;
- Os vetores de ataque mais comuns contra serviços de autenticação (SSH, FTP, HTTP);
- Os motivos pelos quais esses ataques têm sucesso;
- As principais medidas de mitigação e defesa.

---

## 🖥️ Ambiente Utilizado

| Item | Descrição |
|---|---|
| Sistema atacante | Kali Linux (máquina virtual) |
| Ferramenta | Medusa |
| Sistema-alvo | Máquina virtual própria com serviço SSH exposto propositalmente |
| Rede | Rede local isolada (NAT/Host-only), sem acesso à internet |

---

## 🛠️ Passo a Passo

### 1. Preparação do ambiente
- Criação de uma VM alvo com um serviço SSH ativo e um usuário de teste com senha fraca.
- Verificação de conectividade entre atacante e alvo (`ping`, `nmap`).

### 2. Reconhecimento do serviço
```bash
nmap -p 22 <IP_ALVO>
```
Identificação da porta SSH aberta e do serviço em execução.

### 3. Preparação da wordlist
Utilização de uma wordlist de exemplo contendo senhas fracas e comuns (ex: `rockyou.txt` ou lista personalizada).

```
wordlists/exemplo-wordlist.txt
```

### 4. Execução do ataque com Medusa
```bash
medusa -h <IP_ALVO> -u admin -P wordlists/exemplo-wordlist.txt -M ssh
```

**Parâmetros utilizados:**
- `-h` → host alvo
- `-u` → usuário fixo testado
- `-P` → caminho da wordlist de senhas
- `-M` → módulo/protocolo utilizado (neste caso, ssh)

### 5. Resultado obtido
O Medusa testou sequencialmente as senhas da wordlist contra o usuário informado, retornando a senha correta assim que encontrada, evidenciando a fragilidade da credencial utilizada no ambiente de teste.

---

## 🔍 Análise

O ataque teve sucesso devido a:
- Uso de senha fraca e previsível pelo usuário de teste;
- Ausência de limite de tentativas de login (rate limiting);
- Ausência de bloqueio temporário de conta após falhas consecutivas;
- Falta de autenticação multifator (MFA).

---

## 🛡️ Recomendações de Mitigação

| Medida | Descrição |
|---|---|
| **Políticas de senha fortes** | Exigir senhas complexas e com rotação periódica |
| **Rate limiting** | Limitar número de tentativas de login em um intervalo de tempo |
| **Fail2ban** | Bloquear IPs após múltiplas tentativas falhas |
| **Autenticação multifator (MFA)** | Adicionar uma camada extra além da senha |
| **Monitoramento e logs** | Auditar tentativas de login e gerar alertas automáticos |
| **Alterar portas padrão** | Reduzir exposição a varreduras automatizadas |

---

## 📚 Aprendizados

Este desafio reforçou a importância de pensar em segurança desde a concepção de sistemas (security by design), antecipando vetores de ataque comuns como o de força bruta, e aplicando camadas de defesa que tornem esse tipo de ataque inviável na prática.

---

## 📁 Estrutura do Repositório

```
brute-force-medusa-challenge/
├── README.md
├── docs/
│   ├── setup-ambiente.md
│   ├── comandos-utilizados.md
│   └── resultados.md
├── wordlists/
│   └── exemplo-wordlist.txt
└── mitigacoes/
    └── recomendacoes-seguranca.md
```

---

## 🏷️ Tecnologias e Ferramentas

`Kali Linux` `Medusa` `SSH` `Segurança da Informação` `Pentest` `Cibersegurança`

---

*Projeto desenvolvido como desafio de prática do curso "Simulando um Ataque de Brute Force de Senhas com Medusa e Kali Linux" — DIO (Digital Innovation One).*
