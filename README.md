# Realizando o 'SQUASH'

A técnica de "squash" no Git permite combinar múltiplos commits em um único commit coeso. Isso é útil para limpar o histórico de commits e criar uma linha do tempo mais organizada e simplificada. Aqui está um resumo de como realizar o squash de commits no Git:

## Demonstração

<ul>
<li>Certifique-se de estar no branch (ramo) onde deseja fazer o squash dos commits.</li>
<li> Execute o comando `git log` para visualizar o histórico de commits e identificar os commits que deseja unir.  . Anote os identificadores (hashes) dos commits ou o número de commits que deseja combinar.</li>
<li>Utilize o seguinte comando para fazer o squash dos commits:</li>
</ul>

`git rebase -i HEAD~N`

Substitua `N` pelo número de commits que deseja unir. Isso abrirá um rebase interativo no seu editor de texto padrão.

<ul>
<li>No editor de texto, você verá uma lista dos commits que especificou na etapa anterior. Cada commit é prefixado com a palavra "pick". Para fazer o squash de um commit, altere "pick" para "squash" ou simplesmente "s" para os commits que deseja combinar.</li>
<li>Salve e feche o editor de texto. Outro editor de texto será aberto, permitindo que você modifique a mensagem do commit resultante do squash. Atualize a mensagem conforme necessário, salve e feche o editor.</li>
<li>O Git aplicará as alterações e fará o squash dos commits em um único commit. Se houver conflitos durante o processo de rebase, será necessário resolvê-los.</li>
<li>Por fim, você pode utilizar o comando `git log` novamente para verificar se os commits foram unidos em um único commit.</li>
</ul>

Lembre-se de que o squash de commits modifica o histórico de commits, então é geralmente recomendado fazer isso em branches locais antes de enviar as alterações para um repositório remoto. Se você já enviou os commits que deseja fazer o squash, será necessário fazer um "force push" no branch modificado para atualizar o repositório remoto.

Por favor, tenha em mente que, embora o squash de commits possa tornar o histórico de commits mais conciso, é importante considerar o impacto potencial na colaboração e rastreabilidade. Se estiver trabalhando em um repositório compartilhado ou colaborando com outras pessoas, certifique-se de comunicar e concordar com o fluxo de trabalho para o squash de commits.

# git revert
<p>
É utilizado para desfazer alterações de commits do repositório. Esse comando pega o commit especificado, inverte as alterações realizadas e cria um "commit de reversão."<br>
Para utilizá-lo podemos primeiro usar o comando git log para exibir o histórico de commits, onde é exibido o código de cada commit. Com o código do commit que desejamos reverter basta realizar o comando:<br>
git revert codigoCommit<br>
De forma semelhante a um merge, a reversão irá criar um novo commit que vai abrir o editor do sistema configurado, exibindo uma nova mensagem de commit. Quando a mensagem de commit for digitada e tiver sido salva, o Git irá continuar a operação.
Fonte: https://www.atlassian.com/br/git/tutorials/undoing-changes/git-revert#:~:text=isso%20na%20hora.-,Como%20funciona,do%20branch%20para%20commits%20especificados.
</p>


#git cherry pick

<p>
O git cherry-pick é um poderoso comando que permite que commits de Git arbitrários sejam coletados como referência e anexados ao HEAD de trabalho atual. "Cherry picking" é o ato de selecionar um commit da ramificação e fazer a aplicação a outra. O git cherry-pick pode ser útil para desfazer alterações.
Fonte: https://www.atlassian.com/br/git/tutorials/cherry-pick#:~:text=O%20git%20cherry%2Dpick%20%C3%A9,ser%20%C3%BAtil%20para%20desfazer%20altera%C3%A7%C3%B5es.
<p>