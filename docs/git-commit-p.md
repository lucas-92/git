O comando git commit -p (ou git commit --patch) permite que você faça um commit interativo, onde o Git exibe as mudanças que você fez e te permite escolher quais partes (ou hunks) dessas mudanças você quer incluir no commit. Isso é útil quando você deseja selecionar apenas partes específicas de um arquivo ou conjunto de mudanças, ao invés de fazer o commit de todas as alterações de uma vez.
Explicando o exemplo:
1. Diferença entre o arquivo original e o modificado:

O Git mostra um diff entre a versão antiga e a nova do arquivo files/hello.py. O trecho abaixo representa isso:

diff

diff --git a/files/hello.py b/files/hello.py
index 7df869a..af6a3fb 100755
--- a/files/hello.py
+++ b/files/hello.py
@@ -1 +1,4 @@
+#!/usr/bin/python
+
+# Imprime Hello World
 print("Hello, World!")

    Linhas começando com + são linhas que foram adicionadas no novo código.
    Linhas sem símbolo são linhas que não mudaram.
    As linhas @@ -1 +1,4 @@ indicam o contexto da mudança:
        -1 indica que na versão antiga o arquivo tem apenas uma linha.
        +1,4 indica que na nova versão o arquivo tem quatro linhas (com três novas linhas adicionadas ao início do arquivo).

2. Escolha de como lidar com o hunk:

O Git agora está pedindo que você decida o que fazer com esse hunk (aquela porção específica de mudança que ele mostrou). Ele exibe a mensagem:

bash

(1/1) Stage this hunk [y,n,q,a,d,e,?]?

Aqui, você tem várias opções para escolher como tratar esse hunk:

    y (yes): Estagia (stage) essa parte das mudanças para o commit.
    n (no): Não inclui essa parte das mudanças no commit.
    q (quit): Sai do modo interativo, sem fazer mais nenhuma seleção.
    a (all): Estagia essa parte e todas as seguintes automaticamente.
    d (do not stage): Ignora esse hunk e todas as seguintes.
    e (edit): Edita o hunk manualmente para selecionar linhas específicas para incluir.
    ?: Mostra uma ajuda com todas as opções disponíveis.

O que está acontecendo nesse exemplo específico:

    O Git detectou que no arquivo hello.py foram feitas modificações que adicionaram um shebang (#!/usr/bin/python), alguns comentários e o código para imprimir "Hello, World!".
    Ele exibe essas mudanças e pergunta se você quer estagiar essas alterações para o próximo commit.
    Você deve decidir se quer ou não incluir essa parte específica (ou todas as mudanças subsequentes) no commit.

Quando usar git commit -p:

Esse comando é útil quando:

    Você fez várias alterações em um arquivo, mas deseja comitar apenas algumas delas, deixando outras para depois.
    Você quer granularidade ao criar commits, mantendo cada commit focado em uma mudança específica.

Por exemplo, se você fez ajustes de formatação e implementou uma nova funcionalidade no mesmo arquivo, mas deseja fazer commits separados para essas alterações, git commit -p te dá essa flexibilidade.
