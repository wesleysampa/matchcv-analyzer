# 🚀 MatchCV Analyzer - Análise de Vagas & Gerador de Currículo ATS-Friendly

> Aplicação web desenvolvida para a **DIO (Digital Innovation One)** para análise de compatibilidade entre perfis profissionais e descrições de vagas de emprego, gerando automaticamente versões de currículos otimizadas para sistemas de triagem automatizada (ATS - *Applicant Tracking Systems*).

---
## 📌 Links do Projeto

* **Aplicação Publicada:** [https://matchcv-analyzer.lovable.app](https://matchcv-analyzer.lovable.app)

## 🎯 Problema que a aplicação resolve

Estimativas do mercado de recrutamento indicam que cerca de 75% dos currículos submetidos para grandes empresas são descartados automaticamente por robôs de triagem (sistemas ATS como Gupy, Workday, Lever e Greenhouse) antes mesmo de chegarem a um recrutador humano. Os principais motivos são:

1. **Ausência de Palavras-Chave Críticas:** O candidato possui as competências necessárias, mas utiliza sinônimos ou termos não mapeados pela vaga.
2. **Incompatibilidade de Formatação:** Uso de colunas duplas, tabelas, gráficos, ícones ou cabeçalhos especiais que tornam o texto ilegível para os parsers automatizados.
3. **Dificuldade na Estruturação do Primeiro Emprego:** Profissionais em início de carreira enfrentam desafios para apresentar competências acadêmicas, projetos e trabalhos voluntários de maneira relevante.

### A solução do MatchCV Analyzer

O **MatchCV Analyzer** elimina essa barreira ao oferecer um ecossistema completo e gratuito de otimização de carreira:
* **Duas Experiências de Entrada:** Modos visuais dedicados para quem busca o **Primeiro Emprego** e para quem já possui **Trajetória Profissional**.
* **Cálculo de Match Score (%):** Comparação em tempo real entre os dados do usuário e os requisitos da vaga desejada.
* **Mapeamento de Lacunas (Keywords Gap Analysis):** Identificação clara das palavras-chave encontradas e faltantes.
* **Gerador de Currículo ATS-Friendly:** Otimização do resumo e das experiências do candidato com exportação em PDF limpo e cópia direta em texto.


## 🧠 Como funciona a análise (da vaga ao currículo)

O fluxo da aplicação foi projetado para ser totalmente intuitivo e sem fricção:

```
[Escolha do Perfil] ➔ [Preenchimento/Ajuste] ➔ [Análise da Vaga] ➔ [Relatório de Match] ➔ [Exportação ATS]
```

### 1. Seleção de Perfil Adaptativo (Onboarding)
* **Meu Primeiro Emprego (Início de Carreira):** Prioriza a exibição de formação acadêmica, projetos acadêmicos/pessoais, atividades extracurriculares, cursos e *soft skills*.
* **Trajetória Profissional (Com Experiência):** Prioriza o histórico corporativo, conquistas mensuráveis, ferramentas técnicas e métricas de impacto.

### 2. Persistência de Dados e Acesso Livre
* A aplicação utiliza `localStorage` para salvar os dados do perfil no navegador do usuário, dispensando a necessidade de login ou criação de conta e evitando perdas de dados ao recarregar a página.

### 3. Processamento e Análise de Vagas (Job Matcher)
* O candidato cola o texto descritivo da vaga de emprego desejada e informa o cargo/empresa.
* O algoritmo analisa o texto da vaga, extrai os requisitos obrigatórios/desejáveis e faz o cruzamento com o perfil cadastrado.
* É exibido um painel analítico contendo:
  * **Match Score (%)**: Medidor radial com codificação visual por cores (Verde $\ge$ 80%, Amarelo 50-79%, Vermelho < 50%).
  * **Badges de Palavras-Chave Encontradas:** Competências que o candidato possui e que a vaga exige.
  * **Badges de Palavras-Chave Faltantes:** Termos críticos identificados na vaga que não estão no perfil.
  * **Plano de Ação da IA:** Sugestões práticas de melhorias no texto para aumentar as chances de aprovação.

### 4. Geração e Exportação do Currículo ATS
* O sistema reformula o conteúdo mantendo o padrão rigoroso exigido pelos robôs de ATS:
  * Tipografia limpa e padrão de sistema.
  * Layout de coluna única sem elementos gráficos, tabelas ou ícones internos.
  * Seções padronizadas (`Resumo`, `Experiência Profissional`, `Educação`, `Habilidades`).
* **Opções de Saída:** Exportação em formato PDF padronizado A4 e botão para cópia de texto limpo para preenchimento rápido em formulários de candidatura.


## 📝 Mega Prompt utilizado & Histórico de evolução

A construção da aplicação no Lovable seguiu um processo iterativo de refinamento de prompt.

### 1. Mega Prompt Inicial (Versão 1.0)
```markdown
# 🚀 Prompt Lovable: MatchCV Analyzer & Resume Architect (Versão Sem Autenticação)
Construa uma aplicação web moderna, limpa e intuitiva usando React, Tailwind CSS e ShadCN UI. O aplicativo deve permitir que os usuários analisem descrições de vagas livremente, calculem pontuações de compatibilidade (match score) e gerem currículos personalizados e otimizados para sistemas ATS imediatamente, sem exigir criação de conta ou login.

## 🎨 Design System & Configuração de Tema

Aplique estas cores exatas na configuração do tema do Tailwind CSS / ShadCN UI:

* **Primary:** `#2563EB` (Azul Royal)
* **Secondary:** `#0F172A` (Grafite / Slate Escuro)
* **Success:** `#16A34A` (Verde)
* **Warning:** `#D97706` (Âmbar)
* **Danger:** `#DC2626` (Vermelho)
* **Background:** `#F8FAFC` (Cinza Claro / Slate)
* **Card:** `#FFFFFF` (Branco Puro)
* **Text:** `#1E293B` (Grafite Escuro)
* **Text Muted:** `#64748B` (Cinza Suave)
* **Border:** `#E2E8F0` (Cinza de Borda)

## 🔐 Estratégia de Acesso Livre & Dados Locais
* **Zero Cadastro:** Sem telas de login, registro ou bloqueios de autenticação.
* **Acesso Instantâneo:** Os usuários podem acessar todas as ferramentas imediatamente ao entrar.
* **Persistência Local:** Armazene o perfil ativo do usuário e os currículos gerados no `localStorage` para que não percam dados ao recarregar a página. Inclua uma opção "Limpar Dados / Reiniciar" na interface.

## 🛠️ Arquitetura do App & Layout

### 1. Cabeçalho / Navegação
* Logo: **MatchCV Analyzer** com o ícone Lucide `BriefcaseCheck`.
* Links/Abas de Navegação: `Início`, `Meu Perfil`, `Analisar Vaga & ATS`, `Currículos Gerados`.
* Ação Rápida: Botão "Novo Currículo" (reinicia a visualização ou cria uma nova sessão de análise).

### 2. Onboarding / Seleção de Modo (Tela Inicial)
Exiba dois cards visuais de destaque com ícones Lucide limpos, animações ao passar o mouse (hover) e bordas sutis para definir o tipo de perfil:

* **Opção 1: "Meu Primeiro Emprego"**
  * Ícone: `GraduationCap` ou `Sparkles`
  * Badge: "Início de Carreira"
  * Descrição: "Focado em formação acadêmica, projetos, trabalhos voluntários, cursos e habilidades comportamentais."
  * Botão: "Começar Sem Experiência" (variante Primary)
* **Opção 2: "Trajetória Profissional"**
  * Ícone: `Briefcase` ou `TrendingUp`
  * Badge: "Com Experiência"
  * Descrição: "Focado em histórico de cargos, conquistas profissionais, ferramentas técnicas e métricas de resultado."
  * Botão: "Começar Com Experiência" (variante Secondary)

## 🔀 Funcionalidades Principais & Telas

### A. Criador de Perfil (Formulário Adaptativo - Salvamento Automático)
* **Campos Compartilhados:** Dados pessoais (Nome, E-mail, Telefone, LinkedIn, Localização), Resumo Profissional, Formação Acadêmica, Certificações, Hard & Soft Skills, Idiomas.
* **Ajustes para Modo Primeiro Emprego:** Destaca projetos acadêmicos, atividades extracurriculares, interesses técnicos e soft skills com assistentes de texto.
* **Ajustes para Modo Com Experiência:** Adiciona Histórico Profissional (Empresa, Cargo, Datas, Conquistas/Tópicos), ferramentas/softwares utilizados e métricas de impacto quantificáveis.

### B. Analisador de Vagas & Scanner ATS
* **Seção de Entrada:** Campo de texto (Textarea) para colar a Descrição da Vaga + Campos para Título do Cargo e Nome da Empresa.
* **Painel Analítico de Match:**
  * **Medidor de Match / Progresso Radial:** Pontuação percentual visual (ex: 85% Match) com codificação por cores (Verde para 80%+, Amarelo para 50-79%, Vermelho para <50%).
  * **Análise de Lacunas de Palavras-Chave:** 
    * Lista de `Badge` para **Palavras-Chave Encontradas** (cor Success).
    * Lista de `Badge` para **Palavras-Chave Faltantes no ATS** (cor Warning/Danger).
  * **Plano de Ação de IA:** Tópicos listando recomendações de melhorias para maximizar a taxa de aprovação nos robôs ATS.
  * **Geração em Um Clique:** Botão "Otimizar e Gerar CV para esta Vaga".

### C. Gerador de Currículo ATS & Exportação
* **Pré-visualização do Currículo Personalizado:** Visualização lado a lado (Esquerda: Insights do Match & Sugestões da IA, Direita: Canvas do Currículo Imprimível em Tempo Real).
* **Regras de Layout ATS:** Tipografia pura, layout em coluna única/limpo, sem ícones ou colunas complexas dentro do currículo imprimível, cabeçalhos de seção padronizados (`Resumo`, `Experiência`, `Educação`, `Habilidades`), fontes padrão do sistema.
* **Controles de Exportação:** Botão "Baixar PDF (A4)" e "Copiar Texto ATS".

## 🧩 Componentes do ShadCN UI a Utilizar
* `Button`, `Card`, `Input`, `Textarea`, `Badge`, `Progress`, `Tabs`, `Dialog`, `Select`, `Tooltip`, `Separator`, `Toast` (Sonner).
* **Ícones Lucide:** `Briefcase`, `GraduationCap`, `Sparkles`, `FileText`, `CheckCircle2`, `AlertCircle`, `Download`, `ArrowRight`, `Search`, `Trash2`, `RefreshCw`.

## 💻 Notas Técnicas
* Torne o layout totalmente responsivo para dispositivos desktop e móveis.
* Navegação fluida passo a passo entre Perfil -> Inserção da Vaga -> Resultado do Match -> Exportação do Currículo.
* Forneça algoritmos simulados (mock) realistas para o cálculo da Pontuação de Match e extração de palavras-chave, garantindo que o site pareça totalmente funcional logo de início.
```

### 2. O que mudou na versão final?
A partir da primeira resposta e das necessidades do projeto, o prompt foi expandido para a versão final contendo as seguintes especificações decisivas:
* **Remoção de Autenticação (Zero Friction):** Foi adicionada a exigência explícita de acesso livre, sem necessidade de login ou formulários de cadastro prévio.
* **Gerenciamento Local de Estado (`localStorage`):** Adicionada a instrução para o Lovable persistir os dados do formulário e dos currículos diretamente na memória do navegador.
* **Componentização ShadCN UI Explícita:** Inclusão detalhada dos componentes exigidos (`Card`, `Badge`, `Progress`, `Tabs`, `Dialog`, `Toast`, `Button`).
* **Regras Estritas para Layout ATS:** Instruções para garantir que a renderização do currículo não utilizasse elementos gráficos ou colunas duplas que quebrassem a leitura por robôs.

## 🔄 Ajustes solicitados após a primeira geração

Após a geração inicial no Lovable, foram realizados os seguintes ajustes estratégicos para aprimorar a experiência do usuário e atender aos critérios de avaliação:

1. **Eliminação do Fluxo de Login / Cadastro:**
   * **Por quê:** Exigir cadastro diminui drasticamente a conversão e o engajamento imediato de avaliadores e recrutadores durante a demonstração do portfólio.
2. **Implementação do Armazenamento em `localStorage`:**
   * **Por quê:** Permite que o usuário atualize a página sem perder as informações preenchidas do seu perfil ou da vaga analisada, mantendo o ecossistema rápido sem necessidade de um banco de dados externo.
3. **Adição do Botão "Reiniciar / Limpar Dados":**
   * **Por quê:** Facilitar o teste da aplicação em diferentes perfis (testar o modo *Primeiro Emprego* e depois o modo *Trajetória Profissional*) sem resíduos da sessão anterior.
4. **Recurso "Copiar Texto ATS":**
   * **Por quê:** Muitas plataformas de emprego exigem que o candidato cole o texto em campos de formulário. O botão copia o currículo formatado em Markdown/Texto simples para agilizar o processo.


## 📸 Evidências de funcionamento

### 1. Tela Inicial e Seleção de Perfil
<p align="center">
  <img width="1902" height="1031" alt="Tela Inicial e Seleção de Perfil" src="https://github.com/user-attachments/assets/7a007b7c-f57b-43d3-ac4e-7decbca696a5">
  <br>
  <em>Figura 1: Tela de apresentação da aplicação com os dois cards visuais para escolha de perfil.</em>
</p>

### 2. Análise da Vaga e Match Score
<p align="center">
  <img width="1920" height="1031" alt="Análise da Vaga e Match Score" src="https://github.com/user-attachments/assets/0c2886d7-39fd-4dba-b505-cb998195208e">
  <br>
  <em>Figura 2: Dashboard analítico exibindo o Match Score, palavras-chave encontradas e faltantes.</em>
</p>

### 3. Currículo ATS Otimizado e Exportação
<p align="center">
  <img width="1920" height="1031" alt="Currículo ATS Otimizado e Exportação" src="https://github.com/user-attachments/assets/30121948-c8c9-45fb-9882-99d19bccf8e8">
  <br>
  <em>Figura 3: Visualização do currículo reformatado no padrão ATS pronto para download em PDF.</em>
</p>


## 🛠️ Tecnologias Utilizadas

* **Desenvolvimento Guiado por IA:** [Lovable.dev](https://lovable.dev)
* **Core Framework:** React + Vite
* **Linguagem:** TypeScript
* **Estilização:** Tailwind CSS
* **Design System & Componentes:** ShadCN UI
* **Biblioteca de Ícones:** Lucide React
