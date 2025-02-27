=======================
SPID/CIE OpenID Connect
=======================

`SPID <https://www.spid.gov.it/>`_ e `CIE id <https://www.cartaidentita.interno.gov.it/>`_ sono i Sistemi Pubblici di Identità Digitale Italiani e 
adottano gli standard `OpenID Connect Core <https://openid.net/specs/openid-connect-core-1_0.html>`_, `International Government Assurance Profile (iGov) for OpenID Connect 1.0 <https://openid.net/specs/openid-igov-openid-connect-1_0-03.html>`_ e `OpenID Connect Federation 1.0 <https://openid.net/specs/openid-connect-federation-1_0.html>`_.

Grazie all'`identità digitale <https://identitadigitale.gov.it/>`_, la Pubblica Amministrazione e i fornitori di servizi privati forniscono 
la chiave per accedere ai servizi online attraverso una credenziale unica.

Questa documentazione contiene le specifiche tecniche consolidate, conformi alle Linee Guida Nazionali, 
per migliorare l'esperienza di integrazione alle Federazioni OIDC SPID e CIE id per i Fornitori di Servizio
pubblici e privati (RP), Identity Providers (OP) e Soggetti Aggregatori (SA). 

In questa documentazione trovi:

 - Gli esempi pratici dei Metadata, delle richieste e delle risposte OpenID Connect.
 - Come effettuare la registrazione automatica dei RP presso gli OpenID Provider.
 - Come un OpenID Provider riconosce e registra dinamicamente un RP.
 - Come utilizzare gli endpoint della API della Federazione.
 - Come autenticare un utente a SPID e CIE ed ottenere i suoi attributi.


Indice dei contenuti
--------------------

.. toctree:: 
   :maxdepth: 2

   standards.rst
   termini_acronimi.rst
   la_federazione_delle_identita.rst
   entity_configuration.rst
   entity_statement.rst
   trust_marks.rst
   soggetti_aggregatori.rst
   trust_negotiation.rst
   federation_endpoint.rst
   errors_federation.rst
   metadata_oidc.rst
   flusso_autenticazione.rst
   authorization_endpoint.rst
   token_endpoint.rst
   userinfo_endpoint.rst
   attributi_utente.rst
   introspection_endpoint.rst
   revocation_endpoint.rst
   logout.rst
   cryptographic_algos.rst
   log_management.rst
   confronto_oidc_cie_e_oidc_igov.rst
   differenze_oidc_fed.rst
   seccons_bcps.rst
   esempi.rst
   avvisi_spid.rst
   diventa_fornitore.rst
   come_contribuire.rst
