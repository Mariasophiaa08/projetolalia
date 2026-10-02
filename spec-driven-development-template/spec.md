# ESPECIFICAÇÃO DE SOFTWARE: LALIA

## 1. Visão Geral

- **Objetivo:** O LALIA é um aplicativo pensado para ajudar pessoas que têm dificuldade para se comunicar pela fala. A ideia é facilitar a comunicação usando frases, símbolos e voz, dando mais autonomia para a pessoa se expressar.

- **Atores:**
  - Usuário
  - Responsável ou cuidador

## 2. Modelo de Dados

### Entidade: `PerfilComunicacao`

- `usuario`: Usuário relacionado ao perfil
- `tamanho_botoes`: Tamanho dos botões
- `organizacao_botoes`: Organização dos botões
- `forma_comunicacao`: Forma de comunicação escolhida
- `voz`: Voz usada pelo aplicativo
- `frases`: Frases usadas pelo usuário
- `preferencias`: Preferências do usuário

### Entidade: `Contexto`

- `nome`: Nome do contexto
- `opcoes`: Opções de comunicação disponíveis

Os principais contextos são:

- Casa
- Escola
- Saúde
- Social
- Emergência

### Entidade: `Mensagem`

- `texto`: Texto que será comunicado
- `contexto`: Contexto da mensagem
- `usuario`: Usuário que escolheu a mensagem

## 3. Regras de Negócio e Casos de Teste

### Cenário 1: Escolher uma mensagem

- **Dado** que o usuário está usando o aplicativo
- **Quando** ele escolher um contexto e uma mensagem
- **Então** o aplicativo deve reproduzir a mensagem em voz.

### Cenário 2: Usar o aplicativo na escola

- **Dado** que o usuário escolheu o contexto "Escola"
- **Quando** ele selecionar "Preciso de ajuda"
- **Então** o aplicativo deve falar a mensagem escolhida.

### Cenário 3: Usar o aplicativo na área da saúde

- **Dado** que o usuário escolheu o contexto "Saúde"
- **Quando** ele selecionar "Estou com dor"
- **Então** o aplicativo deve reproduzir essa mensagem em voz.

### Cenário 4: Ajuda da inteligência artificial

- **Dado** que o usuário está em um determinado contexto
- **Quando** ele precisar encontrar uma frase para se comunicar
- **Então** a IA pode sugerir algumas opções relacionadas ao contexto.

A IA serve apenas para ajudar a encontrar opções. A pessoa continua escolhendo o que quer comunicar.

## 4. Rotas

| Rota | Método | Função | Descrição |
| :--- | :--- | :--- | :--- |
| `/` | GET | `inicio` | Mostra a tela inicial. |
| `/contexto/` | GET | `contexto_list` | Mostra os contextos disponíveis. |
| `/contexto/<id>/` | GET | `contexto_detail` | Mostra as opções do contexto escolhido. |
| `/mensagem/<id>/falar/` | POST | `mensagem_falar` | Reproduz a mensagem escolhida. |
| `/perfil/` | GET | `perfil_comunicacao` | Mostra as configurações do usuário. |
| `/perfil/atualizar/` | POST | `perfil_update` | Atualiza as configurações do perfil. |

## 5. Interface do Usuário

- **Tela inicial:** Mostra os contextos que podem ser escolhidos pelo usuário.

- **Contextos disponíveis:**
  - Casa
  - Escola
  - Saúde
  - Social
  - Emergência

- **Opções de comunicação:** Depois de escolher o contexto, aparecem frases e opções que podem ser usadas para se comunicar.

- **Personalização:** O usuário pode ter configurações diferentes para o tamanho dos botões, organização, voz e frases.

- **Acessibilidade:** A interface deve ser simples e fácil de usar, já que o aplicativo foi pensado para pessoas com diferentes dificuldades de comunicação.

## Objetivo do projeto

O principal objetivo do LALIA é facilitar a comunicação de pessoas que possuem dificuldades para falar. O aplicativo procura dar mais autonomia para essas pessoas conseguirem expressar suas necessidades, pensamentos e sentimentos no dia a dia.