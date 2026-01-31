# Web-Crawler

🛡️ WebCrawler Recon CLI

Mapeamento automatizado da superfície de exposição de aplicações web

Ferramenta de reconhecimento de segurança (recon) desenvolvida em Python para identificar informações expostas, endpoints visíveis e ativos esquecidos em aplicações web públicas.

Este projeto foi criado com foco defensivo, simulando o primeiro passo de um atacante real, porém com o objetivo de prevenir incidentes antes que eles aconteçam.

🎯 Problema que resolve

Na maioria das empresas, a pergunta não é “temos vulnerabilidades?”
A pergunta real é:

O que nossa aplicação está expondo hoje sem perceber?

Quais endpoints, APIs e dados estão visíveis publicamente?

Nossa superfície de ataque está realmente mapeada?

O que um atacante veria em 5 minutos de reconhecimento?

Este projeto existe para responder essas perguntas rapidamente, de forma automatizada e auditável.

🧠 O que a ferramenta faz (visão executiva)

O WebCrawler Recon CLI realiza um mapeamento controlado da aplicação web, coletando informações que frequentemente passam despercebidas em produção, como:

Dados sensíveis expostos acidentalmente

Endpoints de API visíveis no frontend

Comentários HTML esquecidos (debug, TODOs, chaves)

Subdomínios referenciados fora do inventário oficial

Estrutura real de links internos da aplicação

Tudo isso sem explorar vulnerabilidades, apenas analisando o que já está público — exatamente como um atacante faria antes de decidir atacar.

🔍 O que ele identifica na prática

📧 E-mails expostos

☎️ Telefones em páginas públicas

🔗 Endpoints de API (/api/...)

🔐 Tokens comuns (JWT, API keys simples)

💬 Comentários HTML esquecidos

🌐 Subdomínios referenciados

🧭 Mapa de links internos

Os resultados são entregues em JSON estruturado, pronto para análise, auditoria ou integração com outros sistemas.

⚙️ Diferencial técnico (o que mostra maturidade)

O diferencial não é apenas rastrear páginas, mas como isso é feito:

Controle de profundidade (evita ruído e bloqueios)

Delay configurável (respeita ambientes produtivos)

Interface CLI (automatizável e versionável)

Output estruturado (integração com CI/CD, SIEM, auditorias)

Código simples, auditável e fácil de estender

Isso reflete pensamento de engenharia e segurança, não apenas conhecimento de linguagem.

🧩 Onde isso se encaixa no negócio

Essa ferramenta pode ser usada em:

🔁 Pipelines CI/CD (pré-deploy)

🔎 Auditorias internas de segurança

🧱 Hardening de aplicações web

📋 Inventário contínuo de exposição

🛡️ Times de AppSec / DevSecOps

O ganho real é:

Redução de risco

Menos surpresas em auditorias

Menos incidentes causados por descuido

🚀 Uso básico
python crawler.py -u https://example.com


Com mais controle:

python crawler.py -u https://example.com -d 3 --delay 2 -o output/scan.json

📤 Exemplo de output
{
  "target": "https://example.com",
  "emails": ["admin@example.com"],
  "telefones": [],
  "endpoints": ["/api/login"],
  "tokens": [],
  "comentarios": ["TODO: remover token"],
  "subdominios": ["dev.example.com"],
  "urls_visitadas": 14
}

🔒 Considerações de segurança

A ferramenta não realiza exploração

Não faz brute-force

Não contorna proteções

Atua apenas sobre informações publicamente acessíveis

Ideal para uso responsável, interno e preventivo.

🧠 O que este projeto demonstra sobre o autor

Este projeto demonstra alguém que:

entende como ataques começam

pensa em superfície de ataque, não só em código

constrói ferramentas usáveis em ambiente real

prioriza processo, integração e impacto

“Segurança eficaz não começa com exploits, começa com visibilidade.”

📌 Roadmap (evoluções possíveis)

Parsing de arquivos JavaScript externos

Execução assíncrona (aiohttp)

Integração com crt.sh

Suporte a múltiplos alvos

Proxy / Tor

Sistema de plugins

⚠️ Aviso legal

Utilize apenas em domínios onde você possui autorização explícita.
O autor não se responsabiliza por uso indevido.
