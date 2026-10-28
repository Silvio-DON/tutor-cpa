# 🎓 Tutor da CPA — AI study assistant (Gemini)

Chatbot que ajuda a estudar para a **CPA**, a certificação da ANBIMA para quem quer trabalhar no mercado financeiro. O aluno escolhe um tema, o tutor explica em poucas frases e faz **uma questão de múltipla escolha**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Silvio-DON/tutor-cpa/blob/main/tutor_cpa.ipynb)

## 💡 Como funciona

```
Aluno: "Quero estudar come-cotas"
        ↓
System prompt (regras + tabela oficial de alíquotas)
        ↓
Gemini (temperature 0.2)
        ↓
Explicação em até 4 frases + 1 questão A/B/C/D
```

- **Instruções de sistema (system prompt):** definem o formato da resposta e trazem uma **tabela oficial** (IR regressivo, come-cotas).
- **Redução de alucinação:** o modelo é orientado a usar **somente** os números da tabela e a dizer "não sei" quando não encontrar a resposta.
- **Temperatura baixa (0.2):** respostas mais consistentes entre execuções.
- **Segurança:** a chave da API fica nos *Secrets* do Colab (`userdata.get("API_KEY")`), nunca no código.

## 🧪 Exemplo de saída

> O come-cotas é uma antecipação semestral do Imposto de Renda em fundos de investimento... acontece em maio e novembro... 15% para longo prazo e 20% para curto prazo... não existe em fundo de ações.
>
> **Pergunta:** Qual é a alíquota do come-cotas para fundos de longo prazo e em qual tipo de fundo ele não existe?
> A) 15% e não existe em fundo de ações · B) 20% ... · C) 17,5% ... · D) 22,5% ...

## 🚀 Como rodar

1. Abra o notebook no Colab (botão acima).
2. Em **Secrets** (🔑), crie `API_KEY` com sua chave do [Google AI Studio](https://aistudio.google.com/).
3. Execute as células em ordem.

## 🗺️ Próximos passos

- [ ] **RAG** com o material completo da CPA (chunks + embeddings + busca vetorial)
- [ ] Corrigir a resposta do aluno e explicar o erro
- [ ] Interface web (Streamlit ou Gradio)

## 🧰 Stack

Python · Google Gemini API (`google-genai`) · Prompt engineering · Google Colab

---
Feito por [Silvio Dall'Oglio Neto](https://github.com/Silvio-DON) — Data & AI Engineer in training.
