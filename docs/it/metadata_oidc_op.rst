.. include:: ../common/common_definitions.rst

.. _MetadataOP:

OpenID Connect Provider Metadata (OP)
+++++++++++++++++++++++++++++++++++++

Un OP DEVE pubblicare all'interno del suo EC un Metadata da *federation_entity* e uno da *openid_provider* come riportato nel seguente esempio:

.. code-block:: json

 {
    "metadata":{
      "federation_entity":{
        ...
      }
      "openid_provider":{
        ...
      }
    }
 }

L'EC di un OP DEVE configurare un metadata di tipo **"federation_entity"** e contenere almeno i seguenti parametri obbligatori:

.. list-table:: 
  :widths: 20 60 20
  :header-rows: 1

  * - **Claim**
    - **Descrizione**
    - **Supportato da**
  * - **organization_name**
    - Vedi Sezione 4.8 di `OIDC-FED`_
    - |spid-icon| |cieid-icon|
  * - **homepage_uri**
    - Vedi Sezione 4.8 di `OIDC-FED`_
    - |spid-icon| |cieid-icon|
  * - **policy_uri**
    - Vedi Sezione 4.8 di `OIDC-FED`_
    - |spid-icon| |cieid-icon|
  * - **logo_uri**
    - URL del logo dell'entità; DEVE essere in formato SVG. Vedi Sezione 4.8 di `OIDC-FED`_
    - |spid-icon| |cieid-icon|
  * - **contacts**
    - PEC istituzionale dell'ente. Vedi Sezione 4.8 di `OIDC-FED`_
    - |spid-icon| |cieid-icon|
  * - **federation_resolve_endpoint**
    - Vedi Sezione :ref:`Endpoint di Federazione <federation_endpoint>` e `OIDC-FED`_ Section 4.6
    - |spid-icon| |cieid-icon|


L'EC di un OP DEVE configurare un metadata di tipo **"openid_provider"** DEVE contenere almeno i seguenti parametri obbligatori:



.. list-table:: 
  :widths: 20 60 20
  :header-rows: 1

  * - **Claim**
    - **Descrizione**
    - **Supportato da**
  * - **issuer**
    - Vedi `OpenID.Discovery#OP_Metadata`_. DEVE essere valorizzato con un HTTPS URL che identifica univocamente l'OP.
    - |spid-icon| |cieid-icon|
  * - **authorization_endpoint**
    - Vedi `OpenID.Discovery#OP_Metadata`_.
    - |spid-icon| |cieid-icon|
  * - **token_endpoint**
    - Vedi `OpenID.Discovery#OP_Metadata`_.
    - |spid-icon| |cieid-icon|
  * - **userinfo_endpoint**
    - Vedi `OpenID.Discovery#OP_Metadata`_.
    - |spid-icon| |cieid-icon|
  * - **introspection_endpoint**
    - Vedi :rfc:`8414#page-4`.
    - |spid-icon| |cieid-icon|
  * - **revocation_endpoint** 
    - Vedi :rfc:`8414#page-4`.
    - |spid-icon| |cieid-icon|
  * - **revocation_endpoint_auth_methods_supported**
    - Vedi :rfc:`8414#page-4`. Il valore supportato è **private_key_jwt**
    - |cieid-icon|
  * - **code_challenge_methods_supported**
    - Vedi :rfc:`8414#page-4`. L'OP DEVE supportare S256 (vedi :rfc:`7636#section-4.3`).
    - |spid-icon| |cieid-icon|
  * - **scopes_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. I valori supportati sono *openid*, *offline_access*, *profile*, *email*. Per maggiori dettagli vedi :ref:`Sezione User Claims <user_claims_scopes>`.
    - |spid-icon| |cieid-icon|
  * - **response_types_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Il valore supportato è **code**. 
    - |spid-icon| |cieid-icon|
  * - **response_modes_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. I valori supportati sono *form_post* e *query*.
    - |spid-icon| |cieid-icon|
  * - **grant_types_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. I valori supportati sono *refresh_token* e *authorization_code*.
    - |spid-icon| |cieid-icon|
  * - **acr_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. I valori supportati sono:
      
      ``https://www.spid.gov.it/SpidL1``
      ``https://www.spid.gov.it/SpidL2``
      ``https://www.spid.gov.it/SpidL3``

    - |spid-icon| |cieid-icon|
  * - **subject_types_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Il valore supportato è **pairwise**. 
    - |spid-icon| |cieid-icon|
  * - **id_token_signing_alg_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi signature :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **id_token_encryption_alg_values_supported**
    - See `OpenID.Discovery#OP_Metadata`_. Vedi key encryption :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **id_token_encryption_enc_values_supported**
    - See `OpenID.Discovery#OP_Metadata`_.  Vedi content encryption :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **userinfo_signing_alg_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi signature :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **userinfo_encryption_alg_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi key encryption :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **userinfo_encryption_enc_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi content encryption :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **request_object_signing_alg_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi signature :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
..    * - **request_object_encryption_alg_values_supported**
..      - Fino a diversa indicazione di AgID, non deve essere incluso.
..      - |spid-icon|
..    * - **request_object_encryption_enc_values_supported**
..      - Fino a diversa indicazione di AgID, non deve essere incluso.
..      - |spid-icon|
  * - **token_endpoint_auth_methods_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Il valore supportato è **private_key_jwt**
    - |spid-icon| |cieid-icon|
  * - **token_endpoint_auth_signing_alg_values_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi signature :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|
  * - **claims_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Vedi :ref:`Attributi Utente <user_claims>` per maggiori dettagli.
    - |spid-icon| |cieid-icon|
  * - **claims_parameter_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Il valore supportato è *true*.
    - |spid-icon| |cieid-icon|
  * - **request_parameter_supported**
    - Vedi `OpenID.Discovery#OP_Metadata`_. Il valore supportato è *true*.
    - |spid-icon| |cieid-icon|
  * - **authorization_response_iss_parameter_supported**
    - Vedi :rfc:`9207#section-3`. Deve valere *true*.
    - |cieid-icon|
  * - **jwks**
    - Vedi `OIDC-FED`_ Section 4.2 e `JWK`_.
    - |spid-icon| |cieid-icon|
  * - **client_registration_types_supported**
    - Vedi `OIDC-FED`_ Section 4.2. Il valore supportato è **automatic**. 
    - |spid-icon| |cieid-icon|
  * - **request_authentication_methods_supported**
    - Vedi `OIDC-FED`_ Section 4.2. Il valore supportato è **request_object**.
    - |spid-icon| |cieid-icon|
  * - **request_authentication_signing_alg_values_supported**
    - Vedi `OIDC-FED`_ Section 4.2. Vedi signature :ref:`supported_algs`.
    - |spid-icon| |cieid-icon|


.. warning::
  Il Metadata **"openid_provider"** DEVE adottare il parametro **jwks** o **signed_jwks_uri** come normato da OID-FED invece del parametro **jwks_uri** come richiesto in `OpenID.Discovery#OP_Metadata`_. 

.. seealso:: 

   - :ref:`Esempio di EC di un OP <Esempio_EN1.2>`

   
