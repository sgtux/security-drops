## PCI DSS, o que é ? Quando devo me preocupar ?

O Payment Card Industry Data Security Standard é um padrão global, criado a partir de uma iniciativa das principais bandeiras de cartão de crédito (Visa, Master Card, American Express, Discover e JCB), composto por procedimentos e requerimentos mínimos para garantir a segurança de um negócio que precisa lidar com dados de pagamento, aumentando assim a proteção das informações de titulares de cartões de crédito.

Então nós temos alguns desafios divididos em 12 requerimentos e 6 sessões:

* **Construir e manter a segurança de rede e sistemas**

    **1.** Instalar e manter uma configuração de firewall para proteger os dados do titular do cartão.

    - Regras inseridas, alteradas ou removidas devem passar por uma gestão de mudança.
    - Evitar a utilização de regras genéricas.

    **2.** Não utilizar os padrões do fornecedor para senhas do sistema e outros parâmetros de segurança.

    - Modificar as senhas recebidas pelo fabricante.
    - Modificações devem tornar o equipamento/sistema 
    mais seguro do que a forma pré-definida.
    - Seguir as recomendações de segurança do fabricante.

* **Proteger os dados do titular do cartão**

    **3**. Proteger os dados armazenados do titular do cartão.

    - Não armazenar dados sensíveis, como por exemplo dados de autenticação, salvo nos casos em que a empresa é a gestora da conta do titular do cartão.

    - Informações não essenciais, caso sejam armazenadas, deve ser pelo menor tempo possível, somente durante a necessidade e descartadas em seguida.

    **4.** Criptografar a transmissão dos dados do titular do cartão em redes públicas.

    - Os dados que saírem para rede pública devem estar criptografados, utilizando um certificado reconhecido com chave e criptografia forte.

* **Manter um programa de gerenciamento de vulnerabilidade**
    
    **5.** Proteger todos os sistemas contra malware e atualizar regularmente os programas ou software de antivírus.

    **6.** Desenvolver e manter sistemas e aplicativos seguros.

* **Implementar medidas rigorosas de controle de acesso**

    **7.** Restringir o acesso à dados do titular do cartão por necessidade do negócio.

    **8.** Identificar e autenticar o acesso para componentes do sistema.

    **9.** Restrigir o acesso físico à dados do titular do cartão.

* **Monitorar e testar as redes regularmente**

    **10.** Rastrear e monitorar todo o acesso à recursos da rede e de dados do titular do cartão.

    **11.** Testar regularmente os processos e sistemas de segurança.

    - Executar regularmente um scan de vulnerabilidades tanto interno quanto externo, sendo que o externo só pode ser executado por aprovados do PCI (ASVs).


* **Manter uma política de segurança da informação.**

    **12.** Manter uma política que trate da segurança da informação para todos.

**Concluindo**: Esta foi apenas uma abordagem breve e geral sobre o PCI DSS e seus 12 requisitos, e lembrando, se seu negócio é lidar com PCI, esta certificação de conformidade deveria estar em seu radar, pois melhora consideravelmente a credibilidade de seu negócio.