# Painel de Metas · Especialistas

Dashboard estático (HTML + CSS + JS puro, **um único arquivo**) para acompanhar as metas
por especialista: objetivo, realizado, peso, % de atingimento, o que falta, meta por dia e
meta por dia por salão.

## Publicar no GitHub Pages

1. Crie um repositório novo (ex.: `painel-metas`) e envie o arquivo `index.html` (e este README).
2. No repositório: **Settings → Pages → Build and deployment → Source: Deploy from a branch**.
3. Escolha a branch `main` e a pasta `/ (root)` → **Save**.
4. Em ~1 minuto o site fica em `https://SEU-USUARIO.github.io/painel-metas/`.

Não há build, dependências nem servidor: basta o `index.html`.

## Como usar

| Recurso | O que faz |
|---|---|
| **Dias restantes** | Divide o que falta para gerar a *meta por dia*. Muda tudo de uma vez. |
| **Divisor meta salão** | Meta dia ÷ divisor (2 por padrão). |
| **Campos em caixa** | Objetivo, Realizado, Peso e os textos são editáveis — clique e digite. |
| **+ Especialista / + meta / + penetração** | Adiciona blocos e linhas. O `×` remove a linha. |
| **Ver tabela** | Alterna entre cards e a visão consolidada (boa para imprimir). |
| **Exportar / Importar JSON** | Backup dos dados e troca entre máquinas. |
| **Imprimir** | Layout limpo em papel / PDF. |
| **Claro / Escuro** | Alterna o tema. |
| **Restaurar** | Volta aos valores originais da planilha. |

As edições ficam salvas automaticamente no navegador de quem acessa (localStorage).
Isso é **por navegador** — para compartilhar números atualizados com o time, use
**Exportar JSON** e envie o arquivo, ou fixe os valores no `SEED` dentro do `index.html`
e faça commit.

## Fórmulas

```
%              = realizado ÷ objetivo
resta          = objetivo − realizado
meta dia       = resta ÷ dias restantes
meta dia salão = meta dia ÷ divisor
pontos         = peso, quando % ≥ 100
```

## Editar os valores padrão

No fim do `index.html`, o objeto `SEED` guarda os dados iniciais. Alterando ali e dando
commit, todo mundo passa a ver os novos números (quem já tinha dados salvos precisa
clicar em **Restaurar**).

## Sobre o app Streamlit deste repositório

Os arquivos `dashboard_metas.py` e `requirements.txt` (versão anterior, em Python/Streamlit)
continuam neste repositório e não foram removidos. O `index.html` é a versão estática do
painel, que roda direto no navegador e pode ser publicada pelo GitHub Pages.
