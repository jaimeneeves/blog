# Apaguei uma branch equivocadamente, como recupero?

Para recuperar uma branch deletada no Git, você pode seguir os seguintes passos:

1. Localize o commit mais recente da branch deletada:

Para encontrar o commit mais recente da branch deletada, use o comando:

```bash
git reflog
```

O `git reflog` exibe um histórico de todos os commits que você fez, incluindo os commits das branches deletadas. Procure pelo commit mais recente que estava na branch deletada.

2. Recupere a branch:

Depois de encontrar o commit, você pode criar uma nova branch apontando para esse commit. Suponha que o commit seja `abcd1234`. Use o comando:

```bash
git checkout -b nome-da-nova-branch abcd1234
```

Substitua `nome-da-nova-branch` pelo nome que você deseja dar à nova branch e `abcd1234` pelo identificador do commit que você encontrou no `reflog`.

## Exemplo Completo:

1. Rode o comando `git reflog` e encontre a referência do commit mais recente da branch deletada:

```bash
git reflog
```

Saída (exemplo):

```bash
abcdef1 (HEAD -> master) HEAD@{0}: commit: Último commit na master
abcdef2 HEAD@{1}: checkout: moving from branch-deletada to master
abcdef3 (branch-deletada) HEAD@{2}: commit: Último commit na branch deletada
```

2. Suponha que o commit mais recente da branch deletada é `abcdef3`. Crie uma nova branch a partir desse commit:

```bash
git checkout -b branch-recuperada abcdef3
```

## Dicas:

- Certifique-se de que o commit que você encontrou no `reflog` é o correto.

- Após recuperar a branch, é recomendável revisar os commits para garantir que tudo esteja conforme esperado.

- Adicionar comandos para proteger branches importantes, como configurar proteção de branches no repositório remoto.

## Próximos Passos:

Se precisar de ajuda com qualquer parte específica ou tiver dúvidas sobre funcionalidades adicionais, sinta-se à vontade para perguntar!

