# GuardAI — Fundamentos de Segurança da Informação

## 1. Finalidade

Este documento estabelece os conceitos fundamentais utilizados pelo GuardAI em análises de vulnerabilidades, avaliações de risco e recomendações de segurança.

O agente deve utilizar estes fundamentos para explicar suas conclusões, sem tratar definições gerais como prova de que uma vulnerabilidade específica existe.

## 2. Conceitos fundamentais

### Ativo

Qualquer recurso que tenha valor para uma organização ou usuário, incluindo:

- Aplicações e APIs.
- Servidores, dispositivos e serviços em nuvem.
- Bancos de dados e arquivos.
- Credenciais, tokens e chaves.
- Informações pessoais, financeiras e empresariais.
- Processos operacionais e serviços essenciais.

A criticidade de um ativo depende do seu valor, da função que desempenha e das consequências de sua indisponibilidade ou comprometimento.

### Ameaça

Uma circunstância, evento ou agente capaz de causar dano a um ativo.

Exemplos incluem exploração de falhas, abuso de credenciais, erros operacionais, indisponibilidade de infraestrutura e exposição acidental de dados.

Uma ameaça representa uma possibilidade de dano, não necessariamente uma vulnerabilidade existente.

### Vulnerabilidade

Uma fraqueza de implementação, arquitetura, configuração ou processo que pode ser utilizada para comprometer a segurança.

Exemplos:

- Consultas SQL construídas por concatenação de entradas não confiáveis.
- Verificações de autorização ausentes.
- Segredos armazenados diretamente no código.
- Serviços administrativos expostos sem proteção adequada.
- Dependências vulneráveis em condições relevantes para o sistema.

A presença de uma tecnologia ou configuração não deve ser classificada automaticamente como vulnerabilidade. É necessário avaliar seu comportamento, contexto e controles.

### Exploração

É a utilização de uma vulnerabilidade ou condição insegura para obter um resultado não autorizado.

Uma falha pode existir mesmo quando não foi demonstrada uma exploração. Da mesma forma, demonstrar uma condição em um laboratório não comprova que ela seja explorável da mesma maneira em produção.

### Risco

O risco representa a possibilidade de consequências negativas decorrentes de uma ameaça em determinado contexto.

Sua avaliação deve considerar, pelo menos:

- A probabilidade de o cenário ocorrer.
- O impacto caso ocorra.
- A exposição do ativo.
- Os controles existentes.
- As incertezas da avaliação.

Não confundir risco com vulnerabilidade: uma fraqueza técnica é um dos fatores que podem contribuir para o risco.

### Controle de segurança

Uma medida destinada a prevenir, detectar, limitar ou corrigir eventos que comprometam a segurança.

Exemplos incluem autenticação multifator, autorização por recurso, criptografia, segmentação de rede, monitoramento, backups e testes automatizados.

Um controle somente deve ser considerado eficaz quando seu funcionamento e sua adequação ao cenário forem sustentados por evidências suficientes.

## 3. Tríade CIA

A tríade CIA é composta por confidencialidade, integridade e disponibilidade.

### Confidencialidade

Garante que informações sejam acessíveis somente a entidades autorizadas.

Possíveis violações:

- Exposição de dados pessoais.
- Divulgação de credenciais.
- Leitura indevida de registros financeiros.
- Acesso a arquivos restritos.

Controles relevantes incluem autorização, criptografia, segregação de acesso e gestão de segredos.

### Integridade

Protege a exatidão, a consistência e a legitimidade dos dados e operações.

Possíveis violações:

- Alteração não autorizada de registros.
- Modificação de valores financeiros.
- Manipulação de parâmetros críticos.
- Alteração indevida de configurações.

Controles relevantes incluem validação de regras de negócio, autorização, integridade transacional e auditoria.

### Disponibilidade

Busca garantir que sistemas e informações estejam acessíveis quando necessários.

Possíveis violações:

- Indisponibilidade de uma API.
- Exclusão de arquivos essenciais.
- Esgotamento de recursos.
- Interrupção de um serviço crítico.

Controles relevantes incluem redundância, monitoramento, gestão de capacidade, backups e recuperação de desastres.

Uma mesma vulnerabilidade pode afetar uma, duas ou todas as propriedades da tríade. O agente deve explicar os impactos realmente plausíveis no contexto examinado.

## 4. Probabilidade, impacto e severidade

### Probabilidade

Expressa a avaliação da possibilidade de um cenário de risco ocorrer.

Deve considerar exposição, pré-condições, facilidade de exploração, privilégios necessários, controles existentes e evidências disponíveis.

Não deve ser apresentada como uma frequência estatística exata sem dados que a sustentem.

### Impacto

Representa a gravidade das consequências caso o cenário se concretize.

Considere efeitos técnicos, operacionais, financeiros, legais e reputacionais, conforme o contexto.

### Severidade

Representa uma classificação da gravidade da vulnerabilidade ou de suas consequências, segundo um método definido.

O GuardAI pode utilizar uma matriz qualitativa de impacto e probabilidade para priorização. Se for necessária uma avaliação técnica padronizada, deve considerar o CVSS apropriado à versão utilizada e os dados necessários para calcular a pontuação.

Severidade técnica, risco de negócio e urgência de tratamento são conceitos relacionados, mas não idênticos.

### Risco residual

É o risco que permanece depois da implementação dos controles ou das medidas de mitigação.

Uma correção pode reduzir o risco sem eliminá-lo completamente. O agente deve identificar as condições e limitações que permanecem relevantes.

## 5. Classificações e referências

### CWE

O Common Weakness Enumeration classifica categorias de fraquezas de software e hardware.

Exemplo: CWE-89 descreve a neutralização inadequada de elementos especiais utilizados em comandos SQL, uma categoria associada a SQL Injection.

Utilize o CWE correspondente à causa raiz, e não apenas um identificador semelhante ao nome da vulnerabilidade.

### OWASP

A OWASP publica materiais e projetos voltados à segurança de aplicações e APIs.

O OWASP Top 10 ajuda a compreender categorias de riscos relevantes, mas não substitui uma análise detalhada nem representa uma lista exaustiva de todas as vulnerabilidades.

Use a edição e a classificação adequadas ao contexto.

### MITRE ATT&CK

O MITRE ATT&CK organiza táticas e técnicas observadas em comportamentos adversários.

Ele auxilia a descrever como um adversário pode atuar em determinado cenário. Não é uma classificação de severidade de vulnerabilidades e não substitui o CWE.

Só associe uma técnica ATT&CK quando houver relação defensável com o comportamento analisado. Diferencie uma técnica de exploração de uma fraqueza de implementação.

### CVSS

O Common Vulnerability Scoring System fornece uma metodologia padronizada para avaliar a severidade técnica de vulnerabilidades.

Uma pontuação depende de métricas definidas e da versão utilizada. Não invente pontuações com base apenas no nome de uma falha.

### EPSS

O Exploit Prediction Scoring System estima a probabilidade de exploração de vulnerabilidades publicadas em um horizonte temporal definido pelo modelo.

Não deve ser tratado como uma medida direta do impacto, nem como previsão garantida de que uma vulnerabilidade será explorada em um ambiente específico.

## 6. Vulnerabilidades comuns em aplicações

### SQL Injection

Ocorre quando entradas não confiáveis alteram indevidamente a estrutura ou a semântica de uma consulta SQL.

Causa comum: combinar entradas externas com comandos SQL por concatenação ou interpolação insegura.

Prevenção principal: utilizar consultas parametrizadas e mecanismos adequados do driver ou ORM. Validar entradas conforme as regras de negócio e aplicar o menor privilégio ao usuário do banco.

A parametrização é a proteção principal contra injeção de valores. Identificadores dinâmicos, como nomes de tabelas e colunas, podem exigir listas permitidas e tratamento específico.

Referência de fraqueza: CWE-89.

### Cross-Site Scripting (XSS)

Ocorre quando conteúdo controlável por um atacante é interpretado como código executável no navegador em um contexto inseguro.

Prevenção: codificação de saída conforme o contexto, APIs seguras de manipulação do DOM, sanitização apropriada quando HTML for permitido e políticas de segurança de conteúdo como camada adicional.

Referência comum: CWE-79.

### Falhas de autenticação

Ocorrem quando os mecanismos de verificação de identidade são insuficientes ou podem ser contornados.

Medidas relevantes incluem gestão segura de sessões, proteção contra tentativas automatizadas, autenticação multifator quando apropriada e recuperação de conta segura.

### Falhas de autorização

Ocorrem quando um usuário ou serviço pode realizar operações ou acessar recursos além das permissões concedidas.

Medidas relevantes: verificar autorização no servidor em cada operação sensível, validar permissões por recurso e aplicar o menor privilégio.

A autenticação bem-sucedida não significa que todas as ações estejam autorizadas.

### Exposição de segredos

Inclui chaves, senhas, tokens e credenciais disponibilizados indevidamente em código, registros, imagens de contêineres ou arquivos de configuração.

Medidas relevantes: armazenamento apropriado, controle de acesso, rotação de credenciais expostas e remoção dos segredos dos locais indevidos.

Apagar uma credencial do código atual não invalida automaticamente uma credencial que já foi exposta. Pode ser necessário revogá-la e rotacioná-la.

### Configuração insegura

Inclui permissões excessivas, serviços desnecessariamente expostos, configurações de depuração em produção e controles de segurança desativados.

A correção deve respeitar as necessidades operacionais, evitar interrupções e verificar o estado efetivo do ambiente.

### Dependências vulneráveis

Uma dependência desatualizada pode conter uma vulnerabilidade conhecida, mas o risco depende da versão, do componente afetado, das condições de exploração e dos controles existentes.

Verifique avisos oficiais, versões corrigidas e compatibilidade antes de recomendar atualizações.

## 7. Boas práticas de segurança

### Secure by design

Considere requisitos de segurança desde o desenho do sistema. Identifique ativos, fronteiras de confiança, privilégios e possíveis consequências antes de implementar funcionalidades críticas.

### Defesa em profundidade

Utilize camadas de proteção complementares. Nenhum controle isolado deve ser considerado suficiente para todos os cenários.

### Privilégio mínimo

Conceda a usuários, processos e serviços apenas as permissões necessárias para suas funções.

### Validação de entradas

Verifique se os dados respeitam o formato, o tipo, o intervalo e as regras de negócio esperados.

A validação de entradas não substitui parametrização SQL, codificação de saída ou outros controles específicos do contexto.

### Gestão segura de erros

Forneça mensagens úteis sem revelar detalhes internos desnecessários. Registre informações suficientes para investigar problemas sem expor segredos ou dados sensíveis.

### Gestão de dependências

Mantenha inventário de componentes, monitore avisos de segurança, aplique atualizações compatíveis e teste mudanças antes de implantá-las em produção.

### Logging e monitoramento

Registre eventos relevantes para segurança, preserve a integridade dos registros e limite o acesso a eles.

Não registre senhas, tokens completos, chaves privadas ou dados sensíveis desnecessários.

### Backups e recuperação

Mantenha cópias protegidas e teste a capacidade de recuperação. A existência de um backup não comprova que ele possa ser restaurado corretamente.

### Secure by default

Prefira configurações seguras por padrão, desative serviços desnecessários e evite exposição pública sem justificativa.

### Testes de segurança

Combine revisões de código, testes automatizados, análise de dependências e testes dinâmicos apropriados ao contexto.

Nenhuma ferramenta isolada garante a ausência de vulnerabilidades.

## 8. Princípios de priorização

Ao recomendar ações, o GuardAI deve:

1. Priorizar riscos críticos com consequências relevantes e exposição demonstrada.
2. Considerar a exploração conhecida e o contexto real do ativo.
3. Diferenciar contenção imediata de correção definitiva.
4. Identificar dependências, riscos de regressão e requisitos de reversão.
5. Evitar recomendações genéricas quando uma medida específica puder ser justificada.
6. Declarar o que ainda não foi verificado.
7. Propor critérios claros para confirmar a mitigação.

## 9. Limites do conhecimento

Este documento oferece fundamentos, não prova que uma condição insegura existe em um sistema específico.

O agente deve analisar as evidências disponíveis, consultar fontes confiáveis quando necessário e reconhecer quando não dispõe de informações suficientes.

Quando houver conflito entre uma regra geral e os requisitos técnicos comprovados de um ambiente, deve explicar o conflito e recomendar uma decisão contextualizada, sem abandonar os princípios de segurança.

## 10. Referências oficiais

- CWE: https://cwe.mitre.org/
- MITRE ATT&CK: https://attack.mitre.org/
- OWASP: https://owasp.org/
- OWASP Cheat Sheet Series: https://cheatsheetseries.owasp.org/
- CVSS: https://www.first.org/cvss/
- EPSS: https://www.first.org/epss/
- NIST Cybersecurity Framework: https://www.nist.gov/cyberframework