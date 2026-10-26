# dio-agent-cybersec-extension

Agente inteligente voltado à cibersegurança, com foco em análise de vulnerabilidades, identificação de riscos e orientação para correções seguras. O projeto incorpora o **GuardAI**, uma extensão especializada em apoiar atividades de segurança de aplicações e infraestrutura, o qual surge como uma nova feature/extensão do projeto original da DIO: https://github.com/digitalinnovationone/dio-agent

## Objetivo

O `dio-agent-cybersec-extension` busca ampliar as capacidades de um agente de IA para auxiliar em tarefas de cibersegurança, oferecendo análises estruturadas, recomendações práticas e documentação técnica organizada.

O projeto utiliza conhecimentos de segurança da informação para apoiar a identificação de falhas, a avaliação de riscos e a definição de medidas de mitigação.

## GuardAI — Análise de vulnerabilidades

O GuardAI é o componente especializado em análise de vulnerabilidades. Seu objetivo é ajudar a examinar evidências técnicas, identificar possíveis falhas e propor correções com base em boas práticas de segurança.

### Ciclo de análise

O GuardAI utiliza o ciclo **CICLO GuardAI**:

1. **Contextualizar:** compreender o sistema, o ativo analisado e o objetivo da avaliação.
2. **Investigar:** examinar o código, as configurações, os logs ou as evidências fornecidas.
3. **Classificar:** avaliar a gravidade, a probabilidade e o impacto potencial da vulnerabilidade.
4. **Localizar a causa:** explicar a origem técnica da falha e suas possíveis consequências.
5. **Orientar a correção:** recomendar medidas de mitigação e exemplos de correções quando aplicável.
6. **Observar a validação:** indicar como verificar se a correção resolveu o problema.

### Capacidades

- Análise de possíveis vulnerabilidades em código-fonte.
- Identificação de configurações inseguras.
- Avaliação de riscos e impactos.
- Classificação de severidade.
- Recomendações de correção e mitigação.
- Orientações para validação das correções.
- Uso de referências de segurança, como OWASP, CWE, MITRE ATT&CK e CVSS, quando relevantes.
- Produção de relatórios técnicos estruturados.

**Importante:** A qualidade e tempo dos resultados dependem diretamente do modelo escolhido no hermes ou outro tipo de harness.
## Estrutura do projeto

```text
dio-agent-cybersec-extension/
├── AGENTS.md
├── README.md
├── agent/
│   ├── persona.md
│   └── knowledge/
│       └── security-basics.md
└── skills/
    └── vulnerability-analysis/
        ├── SKILL.md
        └── README.md
```

Os caminhos acima representam a estrutura proposta para os arquivos relacionados ao GuardAI. Ajuste-os conforme a estrutura real do repositório.

### Arquivos criados / alterados

| Arquivo | Finalidade |
|---|---|
| `AGENTS.md` | Orientações gerais para o agente e referência às capacidades disponíveis. |
| `agent/persona.md` | Define a identidade operacional, o comportamento e os limites do agente. |
| `agent/knowledge/security-basics.md` | Reúne conceitos fundamentais de segurança da informação. |
| `skills/vulnerability-analysis/SKILL.md` | Define o procedimento de análise de vulnerabilidades do GuardAI. |
| `skills/vulnerability-analysis/README.md` | Documenta o propósito, o uso e as limitações da habilidade. |

## Requisitos

- Git
- Python, caso seja necessário executar scripts ou ferramentas auxiliares do projeto
- Um ambiente compatível com o agente utilizado
- **Hermes Agent:** https://hermes-agent.nousresearch.com/docs

Consulte a documentação do Hermes para obter as instruções de instalação e configuração compatíveis com seu sistema operacional.

## Como utilizar

1. Clone ou baixe o repositório.
2. Verifique se os arquivos do GuardAI estão nos caminhos apresentados na estrutura do projeto.
3. Configure o ambiente do agente conforme a documentação do Hermes.
4. Confirme se o ambiente reconhece as instruções gerais, a persona e a habilidade de análise de vulnerabilidades.
5. Forneça ao agente um código, uma configuração ou outras evidências que você tenha autorização para analisar.
6. Revise as conclusões e valide as correções no ambiente apropriado.

### Exemplo de solicitação

```text
Analise o código fornecido e Identifique possíveis falhas, explique seus impactos, classifique a severidade, apresente recomendações de correção e sugira testes
para validar as mudanças.
```
