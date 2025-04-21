# Auditoria de Segurança - Botium Toys

## Escopo e Objetivos da Auditoria

**Escopo:** A auditoria abrange todo o programa de segurança da Botium Toys, incluindo os ativos da empresa, como equipamentos de funcionários, rede interna e sistemas utilizados.

**Objetivos:** O principal objetivo é avaliar os ativos atuais e completar a lista de verificação de controles e conformidade para determinar quais práticas de controle e conformidade precisam ser implementadas para melhorar a postura de segurança da Botium Toys.

## Ativos Gerenciados pelo Departamento de TI

- Equipamentos físicos de escritório e dispositivos usados pelos funcionários (desktops/laptops, smartphones, workstations remotas, etc.).
- Produtos do ponto de venda, tanto na loja física quanto online, armazenados no depósito.
- Gerenciamento de sistemas e serviços (contabilidade, telecomunicações, banco de dados, segurança, e-commerce, gerenciamento de inventário, etc.).
- Acesso à Internet e rede interna.
- Armazenamento de dados e retenção de informações.
- Manutenção de sistemas legados que requerem monitoramento humano.

## Avaliação de Risco

A avaliação revelou que o gerenciamento de ativos é inadequado, faltando controles essenciais e não conformidade com regulamentações tanto nos EUA quanto internacionalmente.

**Pontuação de risco:** 8/10 (Risco elevado devido à falta de controles e não conformidade).

**Comentários adicionais sobre o risco:**
- Acesso irrestrito a dados internos, comprometendo a segurança de dados de clientes.
- Falta de criptografia para informações de cartão de crédito.
- Ausência de controle de acesso baseado no princípio de menor privilégio.
- Não há planos de recuperação de desastres ou backups de dados críticos.
- Conformidade com o GDPR, mas lacunas em outros controles de segurança.

## Lista de Verificação de Controles

### Controles de Segurança

| Control                           | Sim | Não |
|-----------------------------------|-----|-----|
| Least Privilege                   | ✅  | ❌  |
| Planos de Recuperação de Desastres| ❌  | ✅  |
| Políticas de Senha                | ✅  | ❌  |
| Políticas de Controle de Acesso   | ✅  | ❌  |
| Antivírus                         | ✅  | ❌  |
| Firewall                          | ✅  | ❌  |
| Sistema de Detecção de Intrusão (IDS) | ❌  | ✅  |
| Backups                           | ❌  | ✅  |
| Criptografia                      | ❌  | ✅  |

### Controles Físicos

| Control                           | Sim | Não |
|-----------------------------------|-----|-----|
| Câmeras de Vigilância CCTV        | ✅  | ❌  |
| Sistema de Detecção de Incêndio   | ✅  | ❌  |
| Fechamento de Armários de Equipamento | ✅  | ❌  |

## Conformidade com Melhores Práticas

**PCI DSS:**
- Os dados do cartão de crédito estão protegidos de acordo com as melhores práticas de segurança? | ❌
- A Botium Toys segue as políticas de criptografia para transações de cartão de crédito? | ❌

**GDPR:**
- Os dados dos clientes da UE estão sendo mantidos de forma privada e segura? | ✅
- Existe um plano de notificação para clientes da UE em caso de violação de dados? | ✅

**SOC (Tipo 1 e Tipo 2):**
- A empresa tem políticas estabelecidas de acesso a usuários e segurança de dados confidenciais? | ✅
- A integridade dos dados é garantida? | ✅

## Recomendações (Opcional)

- **Implementar Criptografia:** Para proteger dados sensíveis, como informações de cartão de crédito, que ainda não estão sendo criptografados corretamente.
- **Melhorar Políticas de Senha:** Aumentar os requisitos das políticas de senha para atender aos padrões modernos de segurança.
- **Sistema de Detecção de Intrusão (IDS):** Implementar um IDS para detectar e prevenir tráfego malicioso na rede.
- **Backup e Recuperação de Desastres:** Estabelecer uma estratégia robusta de backup e recuperação de dados.
