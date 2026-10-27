<div align="center">

<img width="100%" src="./assets/banner.svg" alt="Caio Souza — Engenharia, produto e arquitetura de sistemas" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=15&duration=3200&pause=1200&color=A78BFA&center=true&vCenter=true&width=760&height=30&lines=Produto+%C2%B7+Arquitetura+%C2%B7+Entrega;Tecnologia+que+resolve+problema+de+neg%C3%B3cio;IA+aplicada+%C2%B7+Sistemas+que+escalam" alt="" />

<br/>

<img src="https://komarev.com/ghpvc/?username=CaioSouzx00&style=flat-square&color=7C3AED&labelColor=0A0A0F&label=PROFILE+VIEWS" />

</div>

<br/>

> Transformo problema de negócio em sistema que funciona em produção, aguenta crescimento e custa o que deveria custar.

Meu trabalho fica no ponto onde **tecnologia, produto e operação se encontram**: decidir o que construir, como construir e o que **não** construir. Escrevo código, desenho arquitetura e respondo pelo resultado até o deploy.

Hoje construo na **[StackBlackzada](https://github.com/StackBlackzada)**, um estúdio de tecnologia focado em software sob medida e **IA aplicada a processos de negócio**.

<table>
  <tr>
    <td width="33%" valign="top">

**Produto & Estratégia**<br/>
<sub>Escopo enxuto, MVP que valida de verdade e roadmap guiado por impacto, não por moda.</sub>

</td>
    <td width="33%" valign="top">

**Arquitetura & Engenharia**<br/>
<sub>Backend, APIs, microsserviços e dados. Decisões que o time consegue manter daqui a 2 anos.</sub>

</td>
    <td width="33%" valign="top">

**Qualidade & Entrega**<br/>
<sub>CI/CD como gate, testes que protegem o negócio e deploy sem drama.</sub>

</td>
  </tr>
</table>

<br/>

## Como eu trabalho

| Princípio | Na prática |
|:--|:--|
| **Resultado antes de tecnologia** | A stack serve ao problema. Se uma solução simples resolve, ela vence a elegante. |
| **Decisão registrada** | Arquitetura sem justificativa vira dívida. Toda escolha relevante tem o "porquê". |
| **Entrega contínua** | Pequenos incrementos em produção valem mais que um grande lançamento. |
| **Qualidade é automática** | Se depende de disciplina individual, não é processo. Pipeline barra o que não passa. |
| **Segurança desde o desenho** | Auth, autorização e hardening entram no começo, não no fim. |

<br/>

## Stack

<div align="center">
<img src="./assets/stack.svg" width="100%" alt="Stack: back-end, front-end, dados, devops e cloud, IA e automação" />
</div>

<br/>

## Arquitetura

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#1A0B2E','primaryTextColor':'#EDE9FE','primaryBorderColor':'#7C3AED','lineColor':'#A78BFA','secondaryColor':'#2E1065','tertiaryColor':'#0A0A0F','fontFamily':'monospace'}}}%%
flowchart LR
    C([Cliente<br/>Web · Mobile]) --> GW{{API Gateway}}

    subgraph SVC [Serviços]
        direction TB
        S1[Java · Spring Boot<br/>DDD · Clean Architecture]
        S2[PHP · Laravel<br/>MVC · REST]
        S3[Node · Hono RPC<br/>TypeScript]
    end

    GW --> S1
    GW --> S2
    GW --> S3

    S1 --> PG[(PostgreSQL)]
    S2 --> PG
    S2 --> MY[(MySQL)]
    S3 --> MG[(MongoDB)]

    S1 -. eventos .-> EV>Event-driven]
    S3 -. eventos .-> EV
    EV --> AG[n8n · Agentes<br/>NVIDIA NIM]

    classDef core fill:#7C3AED,stroke:#C4B5FD,color:#fff;
    classDef data fill:#0A0A0F,stroke:#7C3AED,color:#EDE9FE;
    class GW,S1 core;
    class PG,MY,MG data;
```

<br/>

## Do commit ao deploy

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#1A0B2E','primaryTextColor':'#EDE9FE','primaryBorderColor':'#7C3AED','lineColor':'#A78BFA','fontFamily':'monospace'}}}%%
flowchart LR
    A[git push] --> B[GitHub Actions]
    B --> C{Testes<br/>unit · integração}
    C -- falhou --> X([Bloqueia o merge])
    C -- passou --> D[Build Docker]
    D --> E[Deploy Fly.io]
    E --> F([Produção])

    classDef ok fill:#7C3AED,stroke:#C4B5FD,color:#fff;
    classDef bad fill:#0A0A0F,stroke:#A78BFA,color:#EDE9FE,stroke-dasharray:4 3;
    class F,E ok;
    class X bad;
```

<br/>

## Projetos

Cada projeto parte de um problema real, com a decisão arquitetural que o sustenta.

| Projeto | Problema que resolve | Decisão-chave | Status |
|:--------|:---------------------|:--------------|:------:|
| **[Investment Aggregator](https://github.com/CaioSouzx00/investment-aggregator)** | Consolidar investimentos em uma visão única e confiável | Java · Spring Boot · PostgreSQL com DDD e Clean Architecture, para o domínio evoluir sem reescrever | ![active](https://img.shields.io/badge/active-7C3AED?style=flat-square&labelColor=0A0A0F) |
| **[Hydrax](https://github.com/CaioSouzx00/hydrax)** | Fluxo transacional com comunicação por e-mail | Laravel · PostgreSQL, MVC + REST pela velocidade de entrega com manutenção simples | ![active](https://img.shields.io/badge/active-7C3AED?style=flat-square&labelColor=0A0A0F) |
| **Automação n8n + NVIDIA NIM** | Atendimento e mensagens sem fila humana | Orquestração event-driven com LLM via API, rodando no Fly.io | ![active](https://img.shields.io/badge/active-7C3AED?style=flat-square&labelColor=0A0A0F) |
| **Backend Moderno** | Contrato de API sem divergência entre front e back | Hono RPC · TypeScript, tipagem ponta a ponta e pronto para edge | ![wip](https://img.shields.io/badge/wip-A78BFA?style=flat-square&labelColor=0A0A0F) |
| **Réplica Spotify** | Exercício de arquitetura de interface | React, componentização e SPA | ![done](https://img.shields.io/badge/done-4C1D95?style=flat-square&labelColor=0A0A0F) |

<br/>

## Em estudo

`Rust` sistemas seguros e concorrência · `FHE` computação sobre dados cifrados · `NVIDIA NIM` agentes com tool calling e skills · `Hardening` OWASP, Auth/AuthZ e segurança de APIs

<br/>

## GitHub

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=CaioSouzx00&show_icons=true&include_all_commits=true&count_private=true&bg_color=0A0A0F&border_color=2E1065&border_radius=8&title_color=A78BFA&icon_color=7C3AED&text_color=D4D4D8&ring_color=7C3AED" />
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=CaioSouzx00&layout=compact&langs_count=8&bg_color=0A0A0F&border_color=2E1065&border_radius=8&title_color=A78BFA&text_color=D4D4D8" />

<br/>

<img src="https://streak-stats.demolab.com?user=CaioSouzx00&background=0A0A0F&border=2E1065&stroke=2E1065&ring=7C3AED&fire=A78BFA&currStreakNum=EDE9FE&sideNums=D4D4D8&currStreakLabel=A78BFA&sideLabels=71717A&dates=71717A&border_radius=8" />

</div>

<br/>

## Contato

<div align="center">

Tem um problema que software pode resolver? Vamos conversar.

[![GitHub](https://img.shields.io/badge/GitHub-CaioSouzx00-0A0A0F?style=for-the-badge&logo=github&logoColor=A78BFA)](https://github.com/CaioSouzx00)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Caio_Souza-0A0A0F?style=for-the-badge&logo=linkedin&logoColor=A78BFA)](https://www.linkedin.com/in/SEU-USUARIO)
[![Email](https://img.shields.io/badge/Email-contato-0A0A0F?style=for-the-badge&logo=gmail&logoColor=A78BFA)](mailto:seu@email.com)

</div>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:7C3AED,55:1A0B2E,100:000000&height=90&section=footer" />

<div align="center">
<sub>Técnico em Informática · ETEC &nbsp;·&nbsp; Goiás, BR</sub>
</div>