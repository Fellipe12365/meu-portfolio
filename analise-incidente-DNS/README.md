# 🛡️ Análise de Incidente - Porta DNS Inacessível

Este repositório contém a análise de um incidente de segurança cibernética envolvendo falha de acesso ao site `www.yummyrecipesforme.com` por conta de erro na resolução DNS.

## 📄 Arquivos

- [`relatorio_incidente.md`](./relatorio_incidente.md): Relatório completo em Markdown com análise detalhada do tcpdump, protocolos envolvidos e possíveis causas do erro.
- [`tcpdump_log.png`](./tcpdump_log.png): Captura da ferramenta `tcpdump` que registra a troca de pacotes e mensagens ICMP de erro.

## 🧪 Cenário do Incidente

Usuários relataram erro de "porta de destino inacessível" ao tentar acessar o site. Foi utilizado `tcpdump` para identificar falhas de comunicação DNS. As mensagens ICMP indicaram que a porta UDP 53 no servidor DNS estava inacessível, bloqueando as resoluções de nome.

## 🔍 Objetivo

Investigar e documentar o incidente, compreendendo:

- Quais protocolos foram utilizados.
- Qual serviço foi impactado.
- Mensagens de erro recebidas.
- Causa provável do problema.
- Ações propostas para mitigação.

## 🛠️ Tecnologias e Ferramentas

- `tcpdump`
- Protocolo ICMP
- Protocolo UDP
- DNS (porta 53)

## 📬 Contato

Desenvolvido por Fellipe Mendes Luz – [LinkedIn](https://www.linkedin.com/in/fellipemendesluz) | fellipe.mendes@email.com

---

