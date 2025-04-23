## **Para que seu serviço de e-mail funcione corretamente, é necessário configurar a Zona de DNS com os registros MX, CNAME e TXT. Mas você já se perguntou por que e para que servem esses apontamentos?**

## **Apontamento MX**

![ChatGPT Image 23 de abr. de 2025, 12_11_09.png](attachment:3bfd8d51-dad6-45c3-a6d9-90bf36e20c83:ChatGPT_Image_23_de_abr._de_2025_12_11_09.png)

Os registros **MX (Mail Exchanger)** são essenciais para o funcionamento do serviço de e-mail no domínio. Eles definem **quais servidores estão autorizados a receber mensagens** enviadas para os endereços do domínio — ou seja, são a porta de entrada dos e-mails.

**Como funcionam?**  
Quando um e-mail é enviado para um endereço do seu domínio, os servidores do remetente consultam os registros MX na Zona de DNS. Esses registros informam **quais servidores devem receber o e-mail e em qual ordem**.

1. O servidor de origem consulta o DNS do domínio de destino.  
2. Localiza os registros MX e identifica os servidores válidos.  
3. Encaminha o e-mail conforme a prioridade definida.

**Prioridade dos registros MX**  
Cada registro MX possui uma **prioridade numérica**. O servidor com o **menor valor** tem preferência. Se estiver indisponível, o próximo na ordem será utilizado, garantindo redundância e continuidade na entrega.

**Importância de uma configuração correta**  
Uma configuração incorreta dos MX pode resultar em:

- Falha no recebimento de mensagens;  
- Erros de entrega;

---

## **Apontamento CNAME**

Os apontamentos **CNAME (Canonical Name)** criam aliases (apelidos) para o domínio, permitindo que um subdomínio aponte para outro domínio ou subdomínio.

**Como funcionam?**  
Facilitam a gestão da Zona de DNS ao evitar alterações diretas por IP. Exemplo:

`www.exemplo.com → exemplo.com`

Todo acesso ao subdomínio com `www` será redirecionado para o domínio principal.

**Importância de uma configuração correta**  
Manter os CNAMEs corretamente configurados garante o funcionamento de recursos como:

- Webmail  
- Calendário  
- Autodiscover

**Limitações**

- Não pode ser usado na raiz do domínio (`exemplo.com.br`), apenas em subdomínios (`www.exemplo.com.br`, `blog.exemplo.com.br`);  
- Pode aumentar o tempo de resposta DNS devido à necessidade de redirecionamento.

---

## **Apontamento TXT**

Os registros **TXT** armazenam informações de texto na Zona de DNS. Eles são utilizados principalmente para **verificação de domínio e autenticação de e-mails**, e não para redirecionar tráfego.

**Como funcionam?**  
Permitem adicionar dados visíveis a sistemas externos. Usados, por exemplo, para validar propriedade de domínio e autenticar e-mails — ajudando na proteção contra fraudes.

---

### **SPF (Sender Policy Framework)**

Define **quais IPs e servidores podem enviar e-mails em nome do domínio**. No caso da Locaweb, utilizamos:

`include:_spf.locaweb.com.br`

Esse include já contempla todos os IPs autorizados. Uma configuração incorreta pode causar falha de autenticação SPF e fazer com que as mensagens sejam classificadas como SPAM. A instrução final da política (`-all`, `~all`, `?all`) orienta o servidor de destino sobre o que fazer em caso de falha:

- `-all`: rejeitar a mensagem;  
- `~all`: aceitar com ressalvas;  
- `?all`: deixar a critério do servidor.

---

### **DMARC (Domain-based Message Authentication, Reporting and Conformance)**

O DMARC complementa o SPF e o DKIM, e define a **ação a ser tomada quando um e-mail falhar na autenticação**.

Também permite configurar relatórios de falha para monitoramento contínuo, além de reforçar a política de segurança e evitar spoofing.
