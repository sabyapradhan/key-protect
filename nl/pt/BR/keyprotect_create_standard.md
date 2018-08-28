---

copyright:
  years: 2017, 2018
lastupdated: "2018-06-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}

# Criando chaves padrão
{: #create_standard_keys}

É possível criar uma chave de criptografia padrão com a GUI do {{site.data.keyword.keymanagementserviceshort}} ou programaticamente com a API do {{site.data.keyword.keymanagementserviceshort}}.
{: shortdesc}

## Criando chaves padrão com a GUI
{: #create_standard_key_GUI}

[Depois de criar uma instância do serviço](/docs/services/keymgmt/keyprotect_provision.html), conclua as etapas a seguir para criar uma chave padrão com a GUI do {{site.data.keyword.keymanagementserviceshort}}.

1. [Efetue login no console do {{site.data.keyword.cloud_notm}} ![Ícone de linkexterno](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/){: new_window}.

2. No painel do {{site.data.keyword.cloud_notm}}, selecione sua instância provisionada do {{site.data.keyword.keymanagementserviceshort}}.
3. Para criar uma nova chave, clique em **Incluir chave** e selecione a janela **Gerar uma nova chave**.

    Especifique os detalhes da chave:

    <table>
      <tr>
        <th>Configuração</th>
        <th>Descrição</th>
      </tr>
      <tr>
        <td>Nome</td>
        <td>
          <p>Um alias exclusivo, legível para fácil identificação de sua chave.</p>
          <p>Para proteger sua privacidade, assegure-se de que o nome da chave não contenha informações pessoalmente identificáveis (PII), como seu nome ou local.</p>
        </td>
      </tr>
      <tr></tr>
        <td>Tipo de chave</td>
        <td>O <a href="/docs/services/keymgmt/concepts/keyprotect_envelope.html#key_types">tipo de chave</a> que você gostaria de gerenciar no {{site.data.keyword.keymanagementserviceshort}}. Na lista de tipos de chave, selecione <b>Chave padrão</b>.</td>
      </tr>
      <caption style="caption-side:bottom;">Tabela 1. Descreve as configurações de <b>Gerar nova chave</b></caption>
    </table>

4. Quando você tiver concluído o preenchimento dos detalhes da chave, clique em **Gerar chave** para confirmar. 

## Criando chaves padrão com a API
{: #create_standard_key_API}

Crie uma chave padrão fazendo uma chamada `POST` para o terminal a seguir.

```
https://keyprotect.<region>.bluemix.net/api/v2/keys
```
{: codeblock}

1. [Recupere suas credenciais de serviço e autenticação para trabalhar com chaves no serviço](/docs/services/keymgmt/keyprotect_authentication.html).

2. Chame a API [{{site.data.keyword.keymanagementserviceshort}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/apidocs/639){: new_window} com o comando cURL a seguir.

    ```cURL curl -X POST \ https://keyprotect.<region>.bluemix.net/api/v2/keys \ -H 'authorization: Bearer <IAM_token>' \ -H 'bluemix-instance: <instance_ID>' \ -H 'content-type: application/vnd.ibm.kms.key+json' \ -H 'correlation-id: <correlation_ID>' \ -H 'prefer: <return_preference>' \ -d '{
     "metadata": {
       "collectionType": "application/vnd.ibm.kms.key+json",
       "collectionTotal": 1
     },
     "resources": [
       {
       "type": "application/vnd.ibm.kms.key+json", "name": "<key_alias>", "description": "<key_description>", "expirationDate": "<YYYY-MM-DDTHH:MM:SS.SSZ>", "extractable": <key_type> }
     ]
    }'
    ```
    {: codeblock}

    Para trabalhar com chaves em um espaço e organização do Cloud Foundry especificados na sua conta, substitua `Bluemix-Instance` pelos cabeçalhos `Bluemix-org` e `Bluemix-space` apropriados. [Consulte o doc de referência da API do {{site.data.keyword.keymanagementserviceshort}} para amostras de código ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/apidocs/639){: new_window}.
    {: tip}

    Substitua as variáveis na solicitação de exemplo de acordo com a tabela a seguir.
    <table>
      <tr>
        <th>Variável</th>
        <th>Descrição</th>
      </tr>
      <tr>
        <td><varname>region</varname></td>
        <td>A abreviação da região, como <code>us-south</code> ou <code>eu-gb</code>, que representa a área geográfica na qual reside sua instância de serviço do {{site.data.keyword.keymanagementserviceshort}}. Para obter mais informações, consulte <a href="/docs/services/keymgmt/keyprotect_regions.html#endpoints">Terminais regionais em serviço</a>.</td>
      </tr>
      <tr>
        <td><varname>IAM_token</varname></td>
        <td>Seu token de acesso do {{site.data.keyword.cloud_notm}}. Inclua o conteúdo integral do token <code>IAM</code>, incluindo valor Bearer, na solicitação cURL. Para obter mais informações, veja <a href="/docs/services/keymgmt/keyprotect_authentication.html#retrieve_token">Recuperando um token de acesso</a>.</td>
      </tr>
      <tr>
        <td><varname>instance_ID</varname></td>
        <td>O identificador exclusivo que é designado para sua instância de serviço {{site.data.keyword.keymanagementserviceshort}}. Para obter mais informações, veja <a href="/docs/services/keymgmt/keyprotect_authentication.html#retrieve_instance_ID">Recuperando um ID da instância</a>.</td>
      </tr>
      <tr>
        <td><varname>correlation_ID</varname></td>
        <td>O identificador exclusivo que é usado para rastrear e correlacionar transações.</td>
      </tr>
      <tr>
        <td><varname>return_preference</varname></td>
        <td><p>Opcional: um cabeçalho que altera o comportamento do servidor para operações <code>POST</code> e <code>DELETE</code>.</p><p>Quando você configurar a variável <em>return_preference</em> para <code>return=minimal</code>, o serviço retornará somente os metadados da chave, como o nome da chave e o valor de ID, no corpo da entidade de resposta. Quando você configura a variável para <code>return=representation</code>, o serviço retorna tanto o material da chave quanto os metadados da chave.</p></td>
      </tr>
      <tr>
        <td><varname>key_alias</varname></td>
        <td>
          <p>Um nome exclusivo legível para fácil identificação da sua chave.</p>
          <p>Importante: para proteger sua privacidade, não armazene seus dados pessoais como metadados para sua chave.</p>
        </td>
      </tr>
      <tr>
        <td><varname>key_description</varname></td>
        <td>
          <p>Opcional: uma descrição estendida de sua chave.</p>
          <p>Importante: para proteger sua privacidade, não armazene seus dados pessoais como metadados para sua chave.</p>
        </td>
      </tr>
      <tr>
        <td><varname>YYYY-MM-DD</varname><br><varname>HH:MM:SS.SS</varname></td>
        <td>Opcional: a data e hora em que a chave expira no sistema, no formato RFC 3339. Se o atributo <code>expirationDate</code> for omitido, a chave não expirará. </td>
      </tr>
      <tr>
        <td><varname>key_type</varname></td>
        <td>
          <p>Um valor booleano determina se o material de chave pode sair do serviço.</p>
          <p>Ao configurar o atributo <code>extractable</code> para <code>true</code>, o serviço cria uma chave padrão que pode ser armazenada em seus aplicativos ou serviços.</p>
        </td>
      </tr>
        <caption style="caption-side:bottom;">Tabela 2. Descreve as variáveis que são necessárias para incluir uma chave padrão com a API do {{site.data.keyword.keymanagementserviceshort}}</caption>
    </table>

    Para proteger a confidencialidade de seus dados pessoais, evite inserir informações pessoalmente identificáveis (PII), como seu nome ou local, ao incluir chaves no serviço. Para obter mais exemplos de PII, consulte a seção 2.2 do [NIST Special Publication 800-122 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-122.pdf){: new_window}.
    {: tip}

    Uma resposta `POST /v2/keys` bem-sucedida retorna o valor de ID para a sua chave, junto a outros metadados. O ID é um identificador exclusivo que é designado para sua chave e é usado para chamadas subsequentes para a API do {{site.data.keyword.keymanagementserviceshort}}.

3. Opcional: verifique se a chave foi criada executando a chamada a seguir para obter as chaves em sua instância de serviço do {{site.data.keyword.keymanagementserviceshort}}.

    ```cURL
    curl -X GET \
      https://keyprotect.us-south.bluemix.net/api/v2/keys \
      -H 'accept: application/vnd.ibm.collection+json' \
      -H 'authorization: Bearer <IAM_token>' \
      -H 'bluemix-instance: <instance_ID>' \
      -H 'correlation-id: <correlation_ID>' \
    ```
    {: codeblock}


### O que vem a seguir

- Para saber mais sobre como gerenciar as suas chaves programaticamente, [verifique o documento de referência da API do {{site.data.keyword.keymanagementserviceshort}} para amostras de código ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.bluemix.net/apidocs/639){: new_window}.
- Para ver um exemplo de como chaves armazenadas no {{site.data.keyword.keymanagementserviceshort}} podem funcionar para criptografar e decriptografar dados, [consulte o aplicativo de amostra no GitHub ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/IBM-Bluemix/key-protect-helloworld-python){: new_window}.