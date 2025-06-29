# Sistema de Gerenciamento de Estoque e Roteirização em C

![Linguagem](https://img.shields.io/badge/Linguagem-C-blue.svg)
![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-green.svg)

## 📖 Sobre o Projeto

Este projeto é um sistema de gerenciamento de estoque desenvolvido em linguagem C pura. Ele foi projetado para rodar em um terminal (console) e permite o controle completo de produtos em um depósito, incluindo cadastro, edição, remoção e relatórios.

O grande diferencial do sistema é a sua capacidade de **roteirização para coleta de produtos**. O layout do depósito é modelado como um **grafo**, onde os locais de armazenamento (blocos) são compostos por ruas interconectadas com distâncias específicas. O sistema utiliza o **Algoritmo de Dijkstra** para calcular a rota mais curta entre a posição atual do operador e a rua onde o produto está armazenado, otimizando o tempo de coleta.

Além disso, o projeto implementa estruturas de dados como **Pilhas** para o bloqueio e estorno de itens e **Filas** para gerenciar uma lista de pedidos a serem processados.

---

## ✨ Funcionalidades

- **Gestão de Produtos (CRUD):**
    - **Cadastrar:** Adicionar novos produtos ao estoque com informações detalhadas.
    - **Editar:** Atualizar informações de produtos existentes.
    - **Remover:** Excluir produtos do sistema.
    - **Relatório:** Listar todos os produtos cadastrados com seus respectivos detalhes.
- **Persistência de Dados:**
    - O estoque é salvo em um arquivo de texto (`estoque.txt`), garantindo que os dados não sejam perdidos ao fechar o sistema.
- **Gerenciamento de Pedidos com Fila:**
    - Adiciona solicitações de produtos a uma fila (`FIFO - First-In, First-Out`).
    - Processa a fila de pedidos, dando baixa no estoque dos itens disponíveis.
- **Bloqueio e Reversão de Estoque com Pilha:**
    - Bloqueia uma quantidade específica de um produto para uma operação.
    - Permite reverter o último bloqueio realizado (`LIFO - Last-In, First-Out`), devolvendo a quantidade ao estoque.
- **Navegação e Roteirização Inteligente:**
    - Mapeamento do depósito em diferentes locais (Bloco D, Bloco F, WMS, etc.).
    - Cada local é representado como um grafo com ruas e distâncias.
    - **Cálculo da Rota Mais Curta:** Utiliza o Algoritmo de Dijkstra para encontrar o caminho mais eficiente para a coleta de um produto.
    - **Navegação Interativa:** Guia o operador rua a rua, desde sua posição inicial até o destino.

---

## 🛠️ Estruturas de Dados Utilizadas

- **Arranjo Dinâmico:** Para armazenar a lista de produtos em estoque, com alocação de memória dinâmica (`malloc` e `realloc`).
- **Grafo (Matriz de Adjacência):** Para modelar o layout das ruas de cada local do depósito e calcular as distâncias para a roteirização.
- **Pilha:** Para controlar as operações de bloqueio de estoque, permitindo uma fácil reversão da última ação.
- **Fila:** Para gerenciar os pedidos de produtos de forma organizada, garantindo que o primeiro a ser solicitado seja o primeiro a ser processado.

---

## 🚀 Como Compilar e Executar

Você precisará de um compilador C (como o GCC) instalado em seu sistema.

### Pré-requisitos

- **GCC (GNU Compiler Collection)** ou outro compilador C.
  - Para Windows, você pode usar o [MinGW](https://www.mingw-w64.org/) ou o WSL.
  - Para Linux, instale com `sudo apt-get install build-essential`.
  - Para macOS, instale as Ferramentas de Linha de Comando do Xcode.

### Passos para Execução

1. **Clone o repositório (ou baixe os arquivos):**
   ```bash
   git clone [https://github.com/seu-usuario/seu-repositorio.git](https://github.com/seu-usuario/seu-repositorio.git)
