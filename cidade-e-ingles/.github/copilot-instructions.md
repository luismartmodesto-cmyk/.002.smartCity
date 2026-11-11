# GitHub Copilot Instructions

## Projeto: Cidade & Inglês

## 1. Contexto do projeto

Estamos desenvolvendo um jogo de construção de cidade combinado com aprendizagem de inglês.

O jogador aprende inglês por meio de atividades curtas. Ao responder corretamente, recebe moedas e XP que pode usar para construir e personalizar sua cidade.

O projeto será desenvolvido em fases:

* **Fase 1: MVP de 7 dias.** Construir uma versão pequena, funcional e demonstrável.
* **Fase 2: Aprimoramento durante 3 semanas.** Corrigir problemas, melhorar usabilidade, balancear a economia e recolher feedback.
* **Fase 3: Expansão.** Após a validação inicial, adicionar novos conteúdos e funcionalidades.

O objetivo não é criar uma cidade completa imediatamente. O objetivo é provar que o ciclo principal funciona.

## 2. Regras fundamentais para o Copilot

1. Não expandir o escopo do MVP sem autorização explícita do fundador.
2. Não implementar funcionalidades que não estejam no escopo aprovado.
3. Não substituir tecnologias ou adicionar frameworks sem justificar a necessidade e solicitar aprovação.
4. Priorizar código simples, organizado, legível e fácil de manter.
5. Evitar abstrações complexas e arquiteturas desnecessárias para um protótipo.
6. Não duplicar funcionalidades já existentes.
7. Antes de modificar arquivos, analisar a estrutura e o código existente.
8. Ao corrigir um bug, evitar alterar funcionalidades que já estejam funcionando.
9. Não inventar regras de gameplay quando houver uma decisão pendente.
10. Se uma regra estiver indefinida, criar uma configuração provisória claramente identificada ou solicitar aprovação.
11. Não considerar uma funcionalidade concluída sem testar seu fluxo principal.
12. Manter o projeto executável durante o desenvolvimento.
13. Não inserir dados pessoais de jogadores.
14. Não usar assets sem licença compatível. Registrar a origem dos assets externos.
15. Não adicionar pagamentos, publicidade, contas ou serviços remotos ao MVP.

## 3. Escopo do MVP de 7 dias

### 3.1 Cidade

Criar uma cena de cidade em grade fixa de 6 × 6.

O jogador poderá:

* Visualizar os terrenos disponíveis.
* Comprar construções.
* Selecionar uma célula.
* Posicionar uma construção.
* Remover construções conforme a regra de reembolso aprovada.
* Reorganizar a cidade.

Regras:

* Cada construção ocupa uma célula.
* Não permitir construções sobrepostas.
* Não exigir estradas no MVP.
* Não permitir expansão do mapa nesta fase.

### 3.2 Construções iniciais

O MVP terá quatro construções:

* Casa
* Loja
* Escola
* Parque

Cada construção deverá possuir dados configuráveis:

* ID
* Nome
* Preço
* Tipo
* Descrição
* Comportamento

Não implementar moradores simulados ou serviços complexos.

As funções propostas são:

* Loja: gerar moedas.
* Escola: abrir a área de atividades de inglês.
* Casa: elemento decorativo.
* Parque: elemento decorativo.

Essas funções são propostas iniciais e devem ser tratadas como configuráveis até aprovação.

### 3.3 Economia

O sistema deverá possuir:

* Saldo de moedas.
* Ganho de moedas por atividades.
* Compra de construções.
* Renda automática das lojas.
* Limite de moedas configurável.
* Proteção contra saldo negativo.
* Proteção contra bloqueio econômico.

Não permitir que o jogador fique sem uma forma de continuar progredindo.

Não implementar inflação ou aumento automático de preços no MVP.

### 3.4 Atividades de inglês

O MVP deverá possuir 30 atividades curtas de nível pré-A1/A1, sujeitas à revisão pedagógica.

Categorias:

* Vocabulário.
* Frases do cotidiano.
* Diálogos curtos.

Tipos de atividade:

* Múltipla escolha.
* Associação palavra-imagem.
* Escolha da resposta em um diálogo.

Não implementar digitação livre no MVP.

Cada atividade deverá possuir:

* ID único.
* Categoria.
* Nível.
* Enunciado.
* Alternativas ou elementos de associação.
* Resposta correta.
* Explicação curta.
* Recompensa.
* Dados necessários para áudio opcional.

O conteúdo deve ser revisado por uma pessoa competente em inglês antes de testes com crianças.

### 3.5 Feedback pedagógico

Quando o jogador responder:

Se estiver correto:

* Mostrar feedback positivo e breve.
* Conceder a recompensa elegível.
* Permitir continuar.

Se estiver incorreto:

* Permitir nova tentativa.
* Mostrar uma dica.
* Mostrar uma explicação curta.
* Não retirar moedas.
* Não bloquear o jogador.

O erro deve ser tratado como parte da aprendizagem.

### 3.6 Recompensas

Cada pergunta poderá conceder moedas e XP apenas na primeira conclusão correta.

O sistema deverá:

* Registrar IDs de perguntas recompensadas.
* Impedir recompensas duplicadas.
* Persistir o registro localmente.
* Permitir que o jogador continue praticando sem receber recompensas infinitas.

Os valores de moedas e XP devem ser configuráveis.

### 3.7 Salvamento

Usar armazenamento local no navegador (`localStorage`) no MVP.

Salvar:

* Saldo de moedas.
* XP.
* Construções.
* Posições das construções.
* IDs das perguntas recompensadas.
* Progresso.
* Preferência de áudio.

O jogo deverá carregar os dados salvos ao iniciar.

Se não existir um salvamento, iniciar um novo jogo com valores padrão configuráveis.

Não implementar contas, backend ou sincronização na nuvem.

### 3.8 Áudio

O áudio será opcional.

Pode ser usado `speechSynthesis` do navegador para pronúncia em inglês.

Incluir:

* Botão “Ouvir”.
* Botão para repetir pronúncia.
* Opção de desligar o áudio.

O texto deverá continuar visível e compreensível sem áudio.

Não implementar gravação de voz, microfone ou reconhecimento de fala no MVP.

### 3.9 Interface

A interface deverá:

* Ser responsiva.
* Funcionar em computador, tablet e celular.
* Possuir botões legíveis.
* Evitar elementos cortados.
* Adaptar menus a telas estreitas.
* Permitir rolagem quando necessário.
* Manter a cidade e o saldo de moedas visíveis.

Estilo visual recomendado:

* Jogo 2D ilustrado minimalista.
* Cores claras.
* Formas legíveis.
* Poucos detalhes visuais.
* Placeholders permitidos durante o desenvolvimento.

## 4. Tecnologia e arquitetura

Tecnologias consideradas:

* HTML
* CSS
* JavaScript
* Phaser para a cena de jogo 2D, sujeito à decisão técnica final.

Não adicionar outra linguagem sem necessidade concreta e aprovação.



A estrutura pode ser adaptada caso o projeto já possua uma organização melhor.

Separar:

* Interface.
* Lógica do jogo.
* Dados.
* Salvamento.
* Assets.

## 5. Funcionalidades fora do MVP

Não implementar durante os primeiros 7 dias:

* Login.
* Backend.
* Banco de dados remoto.
* Sincronização entre dispositivos.
* Multiplayer.
* Ranking.
* Chat.
* Compras com dinheiro real.
* Publicidade.
* Moradores com IA.
* Simulação complexa da cidade.
* Expansão de mapa.
* Ciclo dia/noite.
* Energia.
* Penalidades.
* Upgrades complexos.
* Microfone.
* Reconhecimento de fala.
* Painel administrativo.

Essas funcionalidades só poderão ser consideradas depois do MVP e do feedback.

## 6. Plano de desenvolvimento: 7 dias

### Dia 1: Base do projeto

* Criar estrutura de arquivos.
* Configurar a cena principal.
* Criar grade de cidade.
* Criar interface de moedas.
* Garantir que o jogo abre sem erros.
* Congelar o escopo do MVP.

### Dia 2: Construções

* Implementar casa, loja, escola e parque.
* Implementar compra.
* Implementar posicionamento.
* Impedir sobreposição.
* Implementar remoção conforme regra aprovada.

### Dia 3: Economia e salvamento

* Implementar saldo.
* Implementar renda temporizada das lojas.
* Implementar limites.
* Proteger contra saldo negativo.
* Implementar salvamento e carregamento local.

### Dia 4: Atividades de inglês

* Implementar estrutura de dados das atividades.
* Cadastrar as 30 atividades.
* Implementar múltipla escolha.
* Implementar associação.
* Implementar diálogos curtos.
* Implementar feedback, dicas e novas tentativas.

### Dia 5: Recompensas e interface

* Conectar atividades à economia.
* Implementar recompensa única por pergunta.
* Implementar áudio opcional.
* Ajustar interface responsiva.

### Dia 6: Testes e correções

* Testar compras.
* Testar posicionamento.
* Testar remoção.
* Testar saldo zero e renda.
* Testar atividades.
* Testar recompensas duplicadas.
* Testar salvamento após atualizar a página.
* Testar computador e celular.
* Revisar conteúdo pedagógico.

### Dia 7: Congelamento do MVP

* Corrigir apenas bugs bloqueadores.
* Executar o ciclo completo:
  aprender → ganhar moedas → construir → salvar.
* Registrar limitações conhecidas.
* Preparar demonstração.
* Congelar novas funcionalidades.

## 7. Três semanas de aprimoramento

Depois dos 7 dias iniciais, utilizar três semanas para:

### Semana de aprimoramento 1

* Recolher feedback.
* Identificar problemas de usabilidade.
* Corrigir bugs.
* Ajustar economia.
* Melhorar clareza das atividades.

### Semana de aprimoramento 2

* Melhorar interface e responsividade.
* Refinar feedback pedagógico.
* Melhorar organização do código.
* Testar novamente os fluxos principais.

### Semana de aprimoramento 3

* Resolver problemas restantes.
* Revisar estabilidade.
* Ajustar conteúdo.
* Preparar uma versão mais polida.
* Organizar lista de funcionalidades futuras.

Não adicionar funcionalidades grandes sem antes garantir que o ciclo principal está estável.

## 8. Expansão futura

Após o MVP e o período de aprimoramento, novas funcionalidades poderão ser avaliadas, como:

* Novas construções.
* Mais atividades de inglês.
* Novas categorias.
* Personalização da cidade.
* Novas mecânicas de jogo.
* Novos elementos visuais.
* Progressão e upgrades.

Cada funcionalidade nova deve ser avaliada por:

* Valor para o jogador.
* Complexidade.
* Impacto na estabilidade.
* Compatibilidade com o objetivo pedagógico.

## 9. Critérios de aceite do MVP

O MVP só poderá ser considerado funcional quando:

* O jogo abre sem erro.
* A cidade é exibida.
* As quatro construções podem ser compradas.
* Construções podem ser posicionadas sem sobreposição.
* Construções podem ser removidas conforme regra aprovada.
* A economia não permite saldo negativo.
* Existe uma rota de recuperação econômica.
* As 30 atividades possuem respostas revisadas.
* Acertos e erros recebem feedback correto.
* Uma pergunta não concede recompensa repetida indevidamente.
* O progresso continua após atualizar a página.
* A interface funciona em computador e celular.
* O áudio pode ser desligado.
* O jogo não exige dados pessoais ou cadastro.
* O ciclo aprender → ganhar moedas → construir → salvar funciona de ponta a ponta.

## 10. Como o Copilot deve trabalhar

Ao receber uma tarefa:

1. Explicar brevemente o que será alterado.
2. Analisar os arquivos relevantes.
3. Implementar somente a tarefa solicitada.
4. Evitar alterações desnecessárias.
5. Informar os arquivos modificados.
6. Explicar como testar a mudança.
7. Apontar limitações ou decisões pendentes.

Se uma tarefa exigir alteração de arquitetura, dependências, regras de economia ou expansão de escopo, solicitar aprovação antes de executar.

**Prioridade máxima: entregar um MVP funcional, pequeno, estável e testável em 7 dias.**
