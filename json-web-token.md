## Json Web Tokens são seguros ?

**Para chegarmos próximo à uma resposta vamos entender como é formado um JWT tomando este como exemplo:**

***eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiMSIsImV4cCI6MTYxNTkyOTkzNX0.bNntmh_XuFwh9TsFsXBXafOgTQsgMviDztAgmjQjoiE***

Cada parte é separada por um ponto (.) então podemos concluir que ele é composto por 3 partes. As duas primeiras partes são chamadas de Header e Payload respectivamente e são compostas de uma codificação conhecida como Base64, lembrando que essa codificação não é um hash (porque pode ser revertido) e não é criptografia (porque não precisamos de uma chave para ter acesso à mensagem de origem), podemos decodificar utilizando os seguintes comandos no bash:

Header:
```bash
echo eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9 |base64 -d
{ "alg": "HS256", "typ": "JWT" }
```
Payload:
```bash
echo eyJ1c2VyX2lkIjoiMSIsImV4cCI6MTYxNTkyOTkzNX0 |base64 -d
{ "user_id": "1", "exp": 1615929935 }
```

Como resultado temos no Header o tipo de token e qual algoritmo de hash foi utilizado para gerar a assinatura, já no Payload temos algumas informações (identificador de usuário, expiração do token, e outras que podem ser adicionadas conforme necessidade).

A terceira parte é quem comprova a integridade e autenticidade das informações contidas no token, pois é a assinatura, ou seja, é um Hash gerado a partir da concatenação: Header + Payload + Chave. O token pode ser gerado e validado por qualquer um que tiver posse da chave utilizada (inclusive gerar tokens fraudulentos), por isso o motivo de evitar seu compartilhamento, as vezes precisamos compartilhá-la, porém temos outros algoritmos que resolvem este problema utilizando um par de chaves (pública e privada), mas isso é tema para outro drops.

Concluíndo, a resposta para a pergunta inicial é: **Depende**, porque não podemos garantir a confidencialidade das informações contidas no token, mas podemos saber se a fonte é autentica e os dados são legítimos. Então é necessário avaliar cada caso levando em consideração estes pontos. Muito cuidado com informações que são trafegadas via JWT, pois de certa forma elas são públicas.