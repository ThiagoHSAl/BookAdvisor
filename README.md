# 📚 BookAdvisor IA

**Sistema Inteligente de Recomendação e Enriquecimento Semântico de Obras Literárias**

O **BookAdvisor IA** é um protótipo desenvolvido como trabalho prático para a disciplina de Organização e Tratamento da Informação (UFMG). O sistema atua como um agente inteligente que transforma consultas simples e em linguagem natural em **objetos informacionais complexos**, utilizando técnicas de Web Semântica, APIs de prateleira global e Modelos de Linguagem (LLM).

## 🎯 Objetivo do Projeto
Otimizar a "encontrabilidade" (*discoverability*) de livros no ambiente digital, resolvendo o problema de metadados incompletos ou mal categorizados. A aplicação reduz a assimetria informacional ao fornecer ao usuário não apenas a busca por palavras-chave, mas uma recomendação contextual, embasada e justificada.

## ✨ Principais Funcionalidades

- **NLU (Natural Language Understanding):** O usuário digita como se estivesse conversando. A IA (Google Gemini) atua como um tradutor técnico invisível, convertendo a intenção em filtros otimizados para as APIs, independentemente do idioma digitado.
- **Requisições Paralelas (Assíncronas):** O sistema varre simultaneamente a **Google Books API** e a **Open Library API** em milissegundos para coletar metadados literários e comerciais.
- **Enriquecimento Semântico:** Transformação dos metadados brutos (JSON) para o vocabulário padronizado do **Schema.org** e serialização em **JSON-LD** (*Linked Data*).
- **Ranqueamento Híbrido:** Separação inteligente dos resultados em abas (Mais Relevante, Melhor Avaliado e Mais Recente), protegendo o usuário de recomendações de baixa qualidade informacional.
- **Justificativa Transparente:** O LLM analisa os dados estruturados do livro selecionado e explica de forma empática **o porquê** aquela obra atende à necessidade inicial do usuário.

## 🛠️ Arquitetura e Tecnologias

O projeto foi construído utilizando um ecossistema focado em Python e arquitetura REST:

* **Linguagem:** Python 3.10+
* **Frontend:** [Streamlit](https://streamlit.io/) (Renderização reativa de dados estruturados em componentes visuais).
* **LLM Engine:** Google GenAI SDK (`gemini-3.1-flash-lite-preview`).
* **Integração REST:** `requests` para requisições HTTP (`GET`).
* **Concorrência:** `concurrent.futures.ThreadPoolExecutor` para otimização do tempo de rede.

## 🚀 Como Executar o Projeto Localmente

### 1. Clone o repositório
```bash
git clone [https://github.com/SEU_USUARIO/bookadvisor-ia.git](https://github.com/SEU_USUARIO/bookadvisor-ia.git)
cd bookadvisor-ia
