# Euroconnector OpenAPI source code
 - This chapter provides the code samples which could be used while implementing Euroconnector server-side API. 
 - Dedicated only to the Peppol **Access point** (AP) providers.

## API code snippets
 - You can re-use this code 
	 - to define the API methods and describe the request/response data structures
	 - cover some actions with Peppol infrastructure (lookup, validations of the documents)
 - **NOTE:** it does not contain the connection to the AP infrastructure. It should be done individually for the exact AP (data mappings, internal messages and etc.).
 - The UAT version of this API is hosted by the following url: https://euroconnector.uat.fitek.com/api/public/index.html
 
## Alternative API code snippets
 - Open the link https://app.swaggerhub.com/apis/euroconnector/econ-def
 - Export the project by choosing: Export >> Server Stub >> {select the programming language}
 - This will help you to define the API methods 
 
 
 ## Product information
 - [Euroconnector OpenAPI definition](https://app.swaggerhub.com/apis-docs/euroconnector/econ-def)
 - [Product information (EN)](https://www.unifiedpostgroup.com/products/econnector)
 - [Product information (LT)](https://www.unifiedpostgroup.com/lt/products/econnector)
 
 ## Release notes

### Release: v1.1
> 2024-02-09
 - 🆕 The solution enriched with two document types: `MessageLevelResponse` and `InvoiceResponse`. The change reflects to the methods:
   - /Documents/types
   - /Documents/send
   - /Documents/{id}
   - /Documents/search   
   - /Entities/create (AP side  only)
 - description improved in the following methods 
   - /Documents/standards
   - /Documents/types
   - /Documents/send
   - /Documents/search
   - /Entities/create
   - /Entities/search
 - ⚠️ Fixed the `/Entities` messages by adding field `entityInfo.phoneNumber` (it was missing in the previous release). The change reflects to the following methods:
    - /Entities/create
    - /Entities/{id}
    - /Entities/{id}/edit
    - /Entities/{id}/secret-key
    - /Entities/search
 - improved the requests of the `*/search` methods by adding two optional fields: `createdBetween`, `updatedBetween` (schema `dto_DateIsBetween`). Reflects to 
    - /Documents/search
    - /Entities/search
 - improved a few `/Documents/*` methods by adding two optional fields `peppolMessageId` and `documentReference`. Reflects to 
    - /Documents/{id}
    - /Documents/search

### Release: v1.0.1
> 2023-11-06
 - end-point **POST /Authorization/token-create**
   - responses adjusted: 400, 401
 - end-point **GET /Authorization/token-refresh**
   - responses adjusted: 400, 401, 403
 - Enumerator **DocumentStatusEnum** enriched
   - [new, sent, `delivered`, received, error, held, deleted] ⚠️
 - end-point **GET /Documents/received-list** ⚠️
   - `POST` method changed into `GET`
 - end-point **POST /Documents/search**
   - request structure adjustments
 - end-point **GET /Entities/peppol-lookup/{id}**
   - responses adjusted: 200, 400
 - end-point **PUT /Entities/{id}/edit** ⚠️
   - `POST` method changed into `PUT`
   - request structure adjustments
 - end-point **POST /Entities/search**
   - request structure adjustments
 - end-point **GET /Entities/{id}**
   - response adjusted: 200
 - end-point **PUT /Entities/{id}/secret-key**
   - response adjusted: 200

### Release: v1.0
> 2023-10-13
 - initial version
