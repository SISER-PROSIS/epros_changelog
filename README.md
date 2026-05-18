# Epros ERP — Changelog

Site estático de release notes. Sem banco de dados, sem build, sem dependências pesadas.

## Estrutura

```
epros-changelog/
├── index.html          # Site principal
├── build.py            # Gera releases/index.json
├── releases/
│   ├── index.json      # Gerado pelo build.py (não editar manualmente)
│   ├── 2025-05-15.md   # Uma release por arquivo
│   └── ...
└── README.md
```

## Como adicionar uma nova release

1. Crie um arquivo em `releases/` com o nome no formato `YYYY-MM-DD.md`:

```md
---
version: "2.5.0"
date: "2025-06-01"
title: "Nome do módulo ou tema"
---

## Novidades

- Descrição de nova funcionalidade

## Melhorias

- Descrição de melhoria

## Correções

- Descrição de correção de bug
```

2. Rode o build para atualizar o índice:

```bash
python build.py
```

3. Faça commit e push. O GitHub Pages publica automaticamente.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub (pode ser privado se quiser URL customizada via CNAME)
2. Vá em **Settings → Pages**
3. Source: **Deploy from a branch** → `main` → `/ (root)`
4. Opcionalmente configure um domínio customizado (ex: `novidades.epros.com.br`)

## Seções reconhecidas

O site detecta automaticamente as seções e aplica cores:

| Seção | Cor |
|---|---|
| `## Novidades` | Verde |
| `## Melhorias` | Roxo |
| `## Correções` | Laranja |

Qualquer outro título de seção funciona, mas sem cor especial.
