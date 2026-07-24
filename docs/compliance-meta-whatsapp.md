# Checklist de Conformidade — Meta WhatsApp Business Platform

Este documento resume as regras da Meta seguidas pela automação para manter o número da clínica **estável, verificado e sem risco de bloqueio**.

## 1. Canal oficial

- [x] Uso exclusivo da **WhatsApp Cloud API**, provida diretamente pela Meta (ou um Business Solution Provider oficial).
- [x] Nenhuma automação via WhatsApp Web não-oficial, engenharia reversa de API ou ferramentas de terceiros não homologadas — essas práticas violam os Termos de Serviço do WhatsApp e podem banir o número.

## 2. Janela de 24 horas

- [x] Dentro das 24h após a última mensagem do paciente: a IA pode responder livremente dentro do escopo definido.
- [x] Fora das 24h: **apenas mensagens de template pré-aprovadas pela Meta** podem ser enviadas (ex.: lembrete de consulta, confirmação de agendamento).
- [x] Nenhum envio de mensagem iniciada pela clínica sem template aprovado.

## 3. Opt-in e consentimento

- [x] O paciente precisa iniciar a conversa ou dar consentimento explícito (ex.: ao preencher um formulário de contato) antes de receber mensagens automatizadas.
- [x] Fica claro, na primeira interação, que o paciente está falando com um **assistente virtual**.

## 4. Política de conteúdo sensível (saúde)

- [x] Nenhuma mensagem promocional relacionada a saúde é enviada sem consentimento explícito — a Meta trata conteúdo de saúde como categoria sensível.
- [x] A automação não coleta nem processa dados de saúde além do estritamente necessário para agendamento administrativo.
- [x] Nenhum uso de dados do paciente para fins diferentes do atendimento (sem venda de dados, sem uso para ads).

## 5. Qualidade e estabilidade do número

- [x] Monitoramento da **taxa de qualidade** do número (quality rating) fornecida pela própria Meta, evitando bloqueios de tier.
- [x] Limite de envio de mensagens respeitando o **tier de mensageria** da conta comercial.
- [x] Sempre disponível a opção de **transferir para um humano**, reduzindo bloqueios ou denúncias por frustração do usuário.
- [x] Templates de mensagem passam pelo processo oficial de aprovação da Meta antes do uso.

## 6. Privacidade e LGPD

- [x] Coleta mínima de dados (princípio da minimização).
- [x] Registro de conversas armazenado com controle de acesso restrito à equipe da clínica.
- [x] Processo definido para o paciente solicitar exclusão de seus dados.

## 7. Resiliência operacional

- [x] Monitoramento do workflow no n8n (execuções com falha geram alerta).
- [x] Fallback: se a IA ou o webhook falhar, a mensagem cai automaticamente em uma fila de atendimento humano, evitando que o paciente fique sem resposta.
