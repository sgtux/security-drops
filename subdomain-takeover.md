## Subdomain Takeover

**Para enterdermos a gravidade deste problema precisamos saber o básico de DNS, então vamos lá:**

O protocolo DNS (Sistema de Nomes de Domínio) é responsável por traduzir/resolver um nome de domínio para um endereço ip, como por exemplo, toda vez que digitamos no navegador ***mail.cwi.com.br*** é feito uma consulta à um servidor DNS que irá responder com o ip ***189.114.75.68***. Porém no servidor DNS também podemos configurar apelidos (Alias ou CNAME) para nossas aplicações, então digamos que o domínio ***app-02931.azurewebsites.net*** seja nossa aplicação hospedada na Azure mas queremos que ela sejá acessada por ***blog.cwi.com.br***, então para isso criamos um Alias em nosso servidor DNS e quando for feito uma busca por ***blog.cwi.com.br*** todo o trafego será roteado para nossa aplicação hospedada na Azure.

**Até ai tudo certo, não é ? Então qual o problema disso ?**

O problema está quando removemos essa aplicação da Azure e não removemos o Alias criado no servidor DNS, isso é um prato cheio para um atacante, pois possibilita um ataque de Subdomain Takeover, que é quando o próprio servidor  DNS da empresa roteia um de seus sub domínios para um site maliciodo criado pelo atacante devido à um problema de configuração, então basta o atacante registrar sua aplicação na Azure com o mesmo nome de domínio ***app-02931.azurewebsites.net*** e utilizá-la para coleta de cookies, phishing etc... porque o nosso próprio DNS, mal configurado, irá rotear todo o tráfego de ***blog.cwi.com.br*** para a aplicação do Atacante.

**O SSL vai proteger os cookies seguros ?**

Não, pois basta o Atacante utilizar um certificado válido e terá acesso aos cookies seguros, e ainda aumentará a credibilidade do site malicioso.

**Então fica a dica:**

Mantenha sempre os Aliases do servidor DNS atualizados, e faça essa verificação constantemente, tendo sempre em mente que o atacante está fazendo sempre essa verificação de forma automatizada, esperando para tomar o seu sub domínio imediatamente.