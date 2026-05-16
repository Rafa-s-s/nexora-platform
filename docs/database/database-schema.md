# Nexora Database Schema

This document presents the initial database schema for the Nexora Platform.

The structure was designed to support a SaaS model with multiple organizations, WhatsApp conversations, AI-assisted automation, human support, subscriptions and payment control.

## Main Areas

- Organization management
- Administrator access
- WhatsApp conversations
- Message history
- Human support handoff
- FAQ and AI knowledge base
- Donations and volunteers
- Social projects
- LGPD consent records
- SaaS plans, subscriptions and payments

## Database Schema

```dbml
Table Administrador {
  id_admin int [pk]
  id_ong int
  nome varchar
  email varchar
  senha_hash varchar
  nivel_acesso varchar
  ativo boolean
  ultimo_login datetime
  data_criacao datetime
}

Table ONG {
  id_ong int [pk]
  nome varchar
  cnpj varchar
  telefone varchar
  email varchar
}

Table Usuario {
  id_usuario int [pk]
  nome varchar
  telefone_whatsapp varchar
  tipo_usuario varchar
  data_cadastro datetime
}

Table Conversa {
  id_conversa int [pk]
  id_usuario int
  id_ong int
  id_canal int
  data_inicio datetime
  status varchar
  intencao_detectada varchar
}

Table Mensagem {
  id_mensagem int [pk]
  id_conversa int
  direcao varchar
  conteudo text
  tipo_mensagem varchar
  data_envio datetime
}

Table FAQ {
  id_faq int [pk]
  id_ong int
  ativo boolean
  pergunta varchar
  resposta text
}

Table Voluntario {
  id_voluntario int [pk]
  id_usuario int
  id_ong int
  area_interesse varchar
  disponibilidade varchar
  status varchar
}

Table Doacao {
  id_doacao int [pk]
  id_usuario int
  id_ong int
  tipo_doacao varchar
  status varchar
  data_registro datetime
}

Table Atendimento_Humano {
  id_atendimento int [pk]
  id_conversa int
  id_admin int
  motivo varchar
  status varchar
  data_solicitacao datetime
  data_finalizacao datetime
}

Table Configuracao_Bot {
  id_configuracao int [pk]
  id_ong int
  nome_bot varchar
  prompt_base text
  horario_atendimento varchar
  status_ia varchar
}

Table Sessao_Login {
  id_sessao int [pk]
  id_admin int
  token varchar
  ip_acesso varchar
  data_login datetime
  data_expiracao datetime
}

Table Projeto_Social {
  id_projeto int [pk]
  id_ong int
  nome varchar
  descricao text
  status varchar
  data_inicio datetime
  data_fim datetime
}

Table Canal_WhatsApp {
  id_canal int [pk]
  id_ong int
  nome_sessao varchar
  numero_whatsapp varchar
  status varchar
  data_conexao datetime
}

Table Log_Auditoria {
  id_log int [pk]
  id_admin int
  acao varchar
  tabela_afetada varchar
  data_acao datetime
}

Table Consentimento_LGPD {
  id_consentimento int [pk]
  id_usuario int
  id_ong int
  finalidade varchar
  aceitou boolean
  data_consentimento datetime
}

Table Plano {
  id_plano int [pk]
  nome varchar
  descricao text
  preco_mensal decimal
  limite_conversas int
  limite_administradores int
  inclui_ia boolean
  ativo boolean
  data_criacao datetime
}

Table Assinatura {
  id_assinatura int [pk]
  id_ong int
  id_assinatura_gateway varchar
  id_plano int
  status varchar
  data_inicio datetime
  data_fim_teste datetime
  data_proxima_cobranca datetime
  data_cancelamento datetime
}

Table Pagamento {
  id_pagamento int [pk]
  id_assinatura int
  gateway_pagamento varchar
  id_pagamento_gateway varchar
  link_checkout text
  valor decimal
  status varchar
  metodo_pagamento varchar
  data_pagamento datetime
  data_criacao datetime
}

Ref: Assinatura.id_ong > ONG.id_ong
Ref: Assinatura.id_plano > Plano.id_plano
Ref: Pagamento.id_assinatura > Assinatura.id_assinatura
Ref: Conversa.id_canal > Canal_WhatsApp.id_canal
Ref: Projeto_Social.id_ong > ONG.id_ong
Ref: Sessao_Login.id_admin > Administrador.id_admin
Ref: Administrador.id_ong > ONG.id_ong
Ref: Conversa.id_usuario > Usuario.id_usuario
Ref: Conversa.id_ong > ONG.id_ong
Ref: Mensagem.id_conversa > Conversa.id_conversa
Ref: FAQ.id_ong > ONG.id_ong
Ref: Voluntario.id_usuario > Usuario.id_usuario
Ref: Doacao.id_usuario > Usuario.id_usuario
Ref: Atendimento_Humano.id_conversa > Conversa.id_conversa
Ref: Configuracao_Bot.id_ong > ONG.id_ong
Ref: Doacao.id_ong > ONG.id_ong
Ref: Voluntario.id_ong > ONG.id_ong
Ref: Atendimento_Humano.id_admin > Administrador.id_admin
Ref: Canal_WhatsApp.id_ong > ONG.id_ong
Ref: Consentimento_LGPD.id_usuario > Usuario.id_usuario
Ref: Consentimento_LGPD.id_ong > ONG.id_ong
Ref: Log_Auditoria.id_admin > Administrador.id_admin
