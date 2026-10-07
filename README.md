# Enio Aguiar

Desenvolvedor backend (Python, TypeScript, Node.js, FastAPI, PostgreSQL) com foco em APIs e integração com IA. Moro em Aparecida de Goiânia (GO) e busco minha primeira vaga júnior, de preferência remota.

Sou formado em Análise e Desenvolvimento de Sistemas (UNIP). Sempre trabalhei no negócio da minha família e, desde 2025, me dedico a desenvolvimento, criando e mantendo projetos próprios.

[LinkedIn](https://www.linkedin.com/in/enio-aguiar-5776a23a0) · ww.enioaguiar@gmail.com

---

## Projeto principal: LLMPvP

[![LLMPvP](assets/llmpvp.png)](https://www.llmpvp.com)

**[llmpvp.com](https://www.llmpvp.com)** é uma arena ranqueada onde agentes de IA jogam xadrez e Go entre si. Cada pessoa conecta o próprio modelo (OpenAI, Anthropic, Gemini, Ollama local etc.) e a plataforma faz o papel de árbitro: valida os lances, controla o relógio e calcula o rating. A chave de API do modelo nunca passa pelo servidor.

O que eu construí:

- **API REST pública** em FastAPI + PostgreSQL (Supabase), versionada em `/api/v1`, com autenticação por API key, rate limit por janela deslizante e webhooks com proteção contra SSRF
- **Árbitros de xadrez e Go** implementados do zero, matchmaking automático e rating Glicko-2 separado por modalidade
- **Servidor MCP** com 9 ferramentas, publicado no npm ([`llmpvp-plugin`](https://www.npmjs.com/package/llmpvp-plugin)) e no [registro oficial do MCP](https://registry.modelcontextprotocol.io/v0/servers?search=llmpvp), para que agentes de código como Claude Code e Cursor joguem sozinhos. O mesmo pacote instala skill e comandos em 8 CLIs de agentes
- **Sistema anti-trapaça**, calibrado com agentes trapaceiros simulados por um LLM local. Um dos achados: pedir ao modelo no prompt para "consultar o motor com moderação" não funcionou (ele consultou em 22 de 32 lances), então o limite passou a ser imposto no código
- **Frontend** em Next.js com partidas assistidas ao vivo via Supabase Realtime, sem polling
- Login OAuth2 (Google e GitHub), Row Level Security no banco e revisão de segurança com base no OWASP ASVS/Top 10

Repositórios públicos do projeto:

- [`llmpvp-plugin`](https://github.com/EnioAguiar/llmpvp-plugin): servidor MCP e instalador para 8 CLIs de agentes (TypeScript)
- [`llmpvp-adversarial-agents`](https://github.com/EnioAguiar/llmpvp-adversarial-agents): perfis de agentes trapaceiros e servidor de testes usados para calibrar o anti-trapaça (Python, MIT)

O repositório do backend é privado porque contém a lógica de detecção de trapaça. Posso dar acesso para avaliação técnica, é só pedir.

---

## Outros projetos

- **[PRC Data Challenge 2026](https://github.com/EnioAguiar/prc-taxiout-2026)**: competição da EUROCONTROL e da OpenSky Network para prever o tempo de taxiamento de decolagens em 10 aeroportos europeus. Equipe de uma pessoa, com LightGBM e CatBoost. 25º lugar entre 143 equipes no placar público em 3/10/2026, com a competição ainda em andamento.
- **[PolyMarket Bot](https://github.com/EnioAguiar/PolyMarket)**: bot de mercados preditivos em TypeScript, orientado a eventos via WebSocket, com módulo de controle de risco e execução real de ordens na Polymarket (rede Polygon).
- **[CryptoPay](https://github.com/EnioAguiar/gatewaycrypto)**: gateway de pagamentos em cripto no estilo Stripe, com SDK em TypeScript, smart contract em Solidity e monitoramento da blockchain. Roda em testnet (Tron Nile).
- **[PostPulsar](https://github.com/EnioAguiar/post-pulsar)**: SaaS que gerava posts para redes sociais a partir de um artigo, usando a API do Gemini, com Stripe e OAuth2 para cinco redes. Ficou no ar de agosto de 2025 a março de 2026.

---

## Stack

**Uso no dia a dia:** Python, FastAPI, TypeScript, Node.js, PostgreSQL, SQL, Supabase, Docker, Git, Linux

**Também uso:** React, Next.js, Astro, Tailwind CSS, WebSocket, OAuth2, Stripe, LightGBM, CatBoost

**IA:** integração com APIs de LLM (OpenAI, Anthropic, Gemini), modelos locais com Ollama, servidores MCP
