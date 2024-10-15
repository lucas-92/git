Para usar o git diff e verificar as alterações de um arquivo específico no seu repositório, você pode seguir os passos abaixo:
Verificando alterações não comitadas

    Exibir alterações de um arquivo específico (em relação ao último commit):

    bash

git diff nome_do_arquivo

Esse comando mostra as alterações não comitadas (ainda no seu diretório de trabalho) comparadas ao último commit para o arquivo especificado.

Verificar todas as alterações no diretório:

Se você quiser ver as mudanças para todos os arquivos modificados, apenas execute:

bash

    git diff

Comparando com versões anteriores

    Comparar o arquivo com um commit anterior:

    Para comparar um arquivo com uma versão anterior específica (baseada no hash do commit), você pode usar o comando:

    bash

git diff commit_hash nome_do_arquivo

Onde commit_hash é o identificador do commit que você quer comparar, podendo ser o hash completo ou apenas os primeiros caracteres.

Comparar com o último commit (no stage):

Se você já adicionou o arquivo ao stage (usou git add), mas ainda não comitou, você pode verificar as mudanças em relação ao que está no stage com:

bash

    git diff --staged nome_do_arquivo

Isso vai te mostrar as diferenças entre o estado atual no stage e o último commit.
Exemplos

    Ver alterações de um arquivo app.py antes do commit:

    bash

git diff app.py

Comparar as alterações no arquivo app.py que já estão no stage, antes de commitar:

bash

git diff --staged app.py

Comparar o arquivo app.py com um commit anterior:

bash

    git diff a1b2c3d app.py

Esses comandos vão te ajudar a acompanhar as mudanças nos seus arquivos antes de aplicar um commit.
