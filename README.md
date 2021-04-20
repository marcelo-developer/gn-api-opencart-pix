# Módulo de Integração Gerencianet Pix para OpenCart Brasil #

:warning: **Este módulo é compatível apenas com as versões do OpenCart 3.0.3.3 (Brasil 1.5.0) ou superior.**:warning:

**Em caso de dúvidas, você pode verificar a [Documentação](https://dev.gerencianet.com.br/docs/opencart-pix) da API na Gerencianet e, necessitando de mais detalhes ou informações, entre em contato conosco, via nossos [Canais de Comunicação](https://gerencianet.com.br/central-de-ajuda).**

## Requisitos

#### Utilizando PHP 7.3
    Versão do MySQL: 5.6

#### Utilizando PHP 7.4
    Versão do MySQL: 8.x

####Dependências
Instalação de dependências que podem estar faltando (substitua o x pelo número da versão do seu PHP): 
```
    sudo apt-get install php7.x-dom
    sudo apt-get install php7.x-curl
    sudo apt-get install php7.x-gd
    sudo apt-get install php7.x-xml
    sudo apt-get install php7.x-zip
```

- OpenCart necessita do <code>curl</code> ativado
- É necessário que o <code>Real Brasileiro</code> esteja configurado como moeda padrão no Opencart.

## Instalação
### Automática

1. Faça o download do arquivo [gerencianet.ocmod.zip](auto/).

2. Acesse o menu `Extensions > Extension Installer` (`Extensões > Instalador`), clique no botão **Upload**, selecione o arquivo 'gerencianet.ocmod.zip' (citado na primeira instrução) e aguarde a conclusão da instalação automática.

:warning: Caso você já tenha instalado o módulo da Gerencianet anteriormente, o OpenCart poderá informar que alguns arquivos serão sobrescritos. Não se preocupe, pois a instalação não afetará qualquer arquivo que não seja do módulo da Gerencianet já existente em sua loja. :warning:

:warning: Atenção: Devido ao tamanho do arquivo de instalação do módulo, talvez seja necessário alterar o parâmetro `php_max_upload` do `php.ini` para no mínimo 3mb. :warning:


### Manual

1. Faça o download dos [arquivos da última versão do módulo](manual/).
2. Descompacte os arquivo baixado e realize o upload das pastas **admin**, **catalog** e **lib** para dentro do diretório principal do OpenCart.

:warning: Caso você já tenha instalado o módulo da Gerencianet anteriormente, o OpenCart poderá informar que alguns arquivos serão sobrescritos. Não se preocupe, pois a instalação não afetará qualquer arquivo que não seja do módulo da Gerencianet já existente em sua loja. :warning:


## Configuração

Acesse `Extensions >  Modifications` (`Extensões > Modificações`), selecione o módulo `Gerencianet PIX` e clique no botão `Refresh` (`Atualizar`) no canto superior direito da página.

Ao acessar `Extensions >  Extensions` (`Extensões > Extensões`), você deverá selecionar o tipo de extensão que deseja. Escolha `Payments` (`Pagamentos`). Você já visualizará o módulo da Gerencianet disponível na lista. Clique em `install` (`instalar`) para instalar o módulo e depois em `edit` (`editar`) para iniciar a configuração.

Três abas estarão disponíveis para realizar a configuração do módulo:

* Geral
* PIX
* Status do Pedido

### Configurações Gerais

Nesta aba é necessário informar:
* As **credenciais de Produção e Desenvolvimento** da sua aplicação (obtidas na sua conta Gerencianet)
* O **identificador da conta** (obtido na sua conta Gerencianet)
* **Habilitar modo sandbox**: Determina se o módulo está em modo de testes. No modo de teste você pode gerar cobranças fictícias para testar o fluxo.
* **Ativo**: Determina se o módulo de pagamentos da Gerencianet está Ativo ou Inativo.

### PIX

Nesta aba, as seguintes propriedades podem ser configuradas:

* **Chave PIX**: Determina a qual chave PIX o pagamento será enviado
* **Caminho do certificado**: Deve ser informado o caminho onde se encontra o seu certificado de segurança `.pem`
* **Desconto no Pagamento**: Você pode fornecer desconto para clientes que pagam por meio do PIX.
* **Tempo de Vencimento (horas)**: Determina o tempo de validade do QrCode Gerado
* **Validar mTLS**: Habilita ou desabilita a verificação de segurança utilizando mTLS. Mais informações você encontra [AQUI](https://dev.gerencianet.com.br/docs/api-pix#section-webhook)


### Status do Pedido

Nesta aba é realizada a configuração dos Status de pagamento da Gerencianet com os Status de pagamento de sua loja. Assim, quando houver a alteração do status do pagamento na Gerencianet,  o status do pedido em sua loja será atualizado automaticamente de acordo com as configurações definidas.