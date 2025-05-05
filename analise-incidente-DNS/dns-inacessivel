# 📄 Relatório de Incidente de Segurança Cibernética

## ✅ Parte 1 – Análise de Registros do tcpdump (Etapa 3)

### 🔎 Resumo da Análise

Durante a análise dos registros capturados pelo `tcpdump`, foi verificado que o cliente tenta acessar o domínio `yummyrecipesforme.com` por meio de requisições DNS padrão (protocolo UDP, porta 53), direcionadas ao servidor `203.0.113.2`. Todas essas tentativas falham com uma resposta do tipo **ICMP “Port Unreachable”**, indicando que o servidor DNS não está acessível via a porta esperada.

---

### 📡 Protocolos Identificados

- **UDP** – Utilizado para enviar consultas DNS do cliente para o servidor (porta 53).
- **ICMP** – Utilizado pelo servidor para retornar mensagens de erro (especificamente, `port 53 unreachable`).

---

### 🧾 Detalhes do Registro

- Três tentativas consecutivas foram feitas de forma periódica (a cada 2 minutos).
- Todas partiram do IP `192.51.100.15` (cliente) para o IP `203.0.113.2` (servidor DNS).
- Todas as respostas do servidor foram mensagens ICMP de erro com variações no tamanho (`length 254`, `320`, `150`).

---

### ⚠️ Interpretação do Problema

O registro revela que o cliente não conseguiu resolver o nome de domínio devido à **inacessibilidade da porta 53 UDP** no servidor DNS. A repetição do erro ICMP sugere que:

- O servidor DNS não está executando corretamente.
- A porta 53 pode estar fechada por um firewall.
- Há indisponibilidade temporária ou permanente do serviço DNS naquele IP.

---

## ✅ Parte 2 – Análise de Dados e Proposta de Solução (Etapa 4)

### 📅 Momento em que o problema foi relatado

- O primeiro erro foi registrado às **13:24:36.098564**, logo após a primeira tentativa DNS.

---

### 🧠 Cenário e Sintomas

- Usuários reportaram que o site `yummyrecipesforme.com` não carregava.
- Tentativas de acesso resultavam em erro de resolução de nome.
- Ao analisar o tráfego de rede, observou-se a ausência de respostas válidas às requisições DNS.
- Todas as tentativas resultaram em mensagens ICMP “Port Unreachable”.

---

### 📌 Status Atual

- O problema persiste durante todas as tentativas capturadas.
- O servidor DNS de destino **não responde consultas DNS**.
- As mensagens ICMP confirmam falha de comunicação com o serviço DNS.

---

### 🔍 Informações Descobertas

- Todas as requisições DNS foram feitas corretamente pelo cliente.
- O problema está localizado no lado do servidor DNS ou na rede intermediária.
- A porta 53 UDP no IP `203.0.113.2` está indisponível ou bloqueada.
- Não houve qualquer resposta válida (como pacotes DNS do tipo A).

---

### 🛠️ Próximas Etapas para Solução

1. Verificar se o **serviço DNS está ativo** no servidor `203.0.113.2`.
2. Verificar se há algum **firewall ou ACL bloqueando UDP/53**.
3. Testar conectividade com ferramentas como `dig`, `nslookup` ou `telnet` para diagnóstico direto.
4. Substituir temporariamente o servidor DNS no cliente por um funcional (ex: 8.8.8.8).
5. Analisar logs do servidor DNS para identificar falhas internas (ex: bind9, named).

---

### 🧩 Causa Raiz Suspeita

A causa mais provável é que o **serviço DNS no IP 203.0.113.2 está inativo ou inacessível** por bloqueio de porta (firewall), falha de serviço ou configuração incorreta. Isso impossibilita a resolução de nomes de domínio e impede o acesso ao site desejado.

---

