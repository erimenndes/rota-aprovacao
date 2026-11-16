# Rota da Aprovação

Painel de preparação acadêmica em português, desenvolvido para organizar estudo, prática e revisão de Arquitetura de Computadores, Python e Estrutura de Dados.

## Funcionalidades

- Três trilhas com 19 ciclos, 55 tópicos e resumos de consulta.
- Progresso por tópico e ciclo, com checklist de revisão.
- Cronograma de 2, 2,5 ou 3 horas diárias, priorizando Arquitetura.
- Banco de 55 questões autorais de múltipla escolha com comentários.
- Caderno de erros com registro automático e anotações.
- Revisão focada nos tópicos marcados como difíceis ou com menos de 70% de acertos.
- Persistência local e exportação/importação de backup JSON.
- Layout responsivo para computador e celular.

## Tecnologias e arquitetura

HTML5, CSS3 e JavaScript sem framework ou etapa de compilação. Os dados curriculares ficam em `data.js`; navegação, estatísticas, prática e persistência ficam em `app.js`. As telas são renderizadas no navegador e usam navegação por fragmentos de URL.

O projeto demonstra manipulação do DOM, gestão de estado, persistência com localStorage, cálculo de desempenho e validação de backup. Os dados de estudo não são enviados a um servidor. A fonte tipográfica pode ser carregada do Google Fonts; existem fontes alternativas locais.

## Executar localmente

Na pasta do projeto, inicie um servidor estático:

```bash
python -m http.server 8000
```

Abra `http://localhost:8000`. Não é necessário instalar dependências JavaScript. É possível abrir `index.html` diretamente, mas o comportamento do armazenamento em URLs `file:` pode variar entre navegadores.

## Estrutura

| Arquivo | Finalidade |
| --- | --- |
| `index.html` | Estrutura da aplicação |
| `style.css` | Estilos e adaptação de telas |
| `data.js` | Trilhas, resumos e questões |
| `app.js` | Navegação, cronograma, prática, revisão e backup |
| `.nojekyll` | Publicação dos arquivos estáticos sem processamento Jekyll |

## Publicação

Os arquivos estão na raiz e podem ser servidos diretamente por uma hospedagem estática, sem comando de build.

Para GitHub Pages, configure nas opções do repositório a publicação a partir da branch `main`, pasta `/ (root)`. A disponibilidade da hospedagem depende das permissões e do plano da conta. Consulte a [documentação oficial do GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

Para usar domínio próprio, primeiro publique e confirme o endereço padrão. Em seguida, configure o domínio na hospedagem e os registros DNS no provedor. O valor exato depende de o domínio ser raiz ou subdomínio. Não há um domínio pré-configurado neste projeto. Siga a [documentação oficial sobre domínio personalizado](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Personalização

- Edite `courses` e `rawQuestions` em `data.js` para ajustar conteúdo e questões.
- Ajuste `schedule` e as datas de prova em `app.js` e `data.js` para outro período.
- O plano inicial é de 16/11 a 04/12/2026, com 19/11 livre.
- Os dados de Python são organizados a partir dos quatro blocos gerais da ementa; os subtópicos são uma proposta de estudo.

## Persistência e limites

O progresso fica no localStorage de cada navegador e origem. Não existe conta de usuário nem sincronização entre dispositivos. Ao mudar do endereço anterior para um domínio novo, exporte o backup no endereço antigo e importe no novo. As respostas e anotações de quem usa o site não fazem parte do código-fonte.

Marcar um tópico indica estudo realizado, não domínio comprovado. A taxa de acertos é calculada sobre todas as tentativas. As questões são autorais e não reproduzem provas oficiais. O painel não prevê a nota da faculdade.

## Verificações realizadas

- Sintaxe dos scripts validada com `node --check`.
- Fluxo de marcação de tópicos e dificuldades conferido no navegador.
- Resposta incorreta registrada no caderno e no filtro de revisão.
- Anotações preservadas após recarregar a página.
- Distribuição dos blocos conferida para disponibilidade diária de 120 minutos.

## Desenvolvimento

Projeto pessoal de Erisson Meireles, elaborado com assistência de IA. A versão inicial foi construída e verificada com auxílio do ChatGPT. A documentação descreve os recursos implementados e suas limitações.
