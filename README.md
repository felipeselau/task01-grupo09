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