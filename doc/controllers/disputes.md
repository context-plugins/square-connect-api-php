# Disputes

```php
$disputesController = $client->getDisputesController();
```

## Class Name

`DisputesController`

## Methods

* [List Disputes](../../doc/controllers/disputes.md#list-disputes)
* [Retrieve Dispute](../../doc/controllers/disputes.md#retrieve-dispute)
* [Accept Dispute](../../doc/controllers/disputes.md#accept-dispute)
* [List Dispute Evidence](../../doc/controllers/disputes.md#list-dispute-evidence)
* [Create Dispute Evidence Text](../../doc/controllers/disputes.md#create-dispute-evidence-text)
* [Delete Dispute Evidence](../../doc/controllers/disputes.md#delete-dispute-evidence)
* [Retrieve Dispute Evidence](../../doc/controllers/disputes.md#retrieve-dispute-evidence)
* [Submit Evidence](../../doc/controllers/disputes.md#submit-evidence)


# List Disputes

Returns a list of disputes associated with a particular account.

```php
function listDisputes(
    ?string $cursor = null,
    ?string $states = null,
    ?string $locationId = null
): ListDisputesResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query.<br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). |
| `states` | `?string` | Query, Optional | The dispute states to filter the result.<br>If not specified, the endpoint returns all open disputes (the dispute status is not `INQUIRY_CLOSED`, `WON`,<br>or `LOST`). |
| `locationId` | `?string` | Query, Optional | The ID of the location for which to return a list of disputes. If not specified, the endpoint returns<br>all open disputes (the dispute status is not `INQUIRY_CLOSED`, `WON`, or `LOST`) associated with all locations. |

## Requires scope

### oauth2

`DISPUTES_READ`

## Response Type

**200**: Success

[`ListDisputesResponse`](../../doc/models/list-disputes-response.md)

## Example Usage

```php
$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->listDisputes();
    echo 'ListDisputesResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Dispute

Returns details about a specific dispute.

```php
function retrieveDispute(string $disputeId): RetrieveDisputeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute you want more details about. |

## Requires scope

### oauth2

`DISPUTES_READ`

## Response Type

**200**: Success

[`RetrieveDisputeResponse`](../../doc/models/retrieve-dispute-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->retrieveDispute($disputeId);
    echo 'RetrieveDisputeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Accept Dispute

Accepts the loss on a dispute. Square returns the disputed amount to the cardholder and
updates the dispute state to ACCEPTED.

Square debits the disputed amount from the seller’s Square account. If the Square account
does not have sufficient funds, Square debits the associated bank account.

```php
function acceptDispute(string $disputeId): AcceptDisputeResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute you want to accept. |

## Requires scope

### oauth2

`DISPUTES_WRITE`

## Response Type

**200**: Success

[`AcceptDisputeResponse`](../../doc/models/accept-dispute-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->acceptDispute($disputeId);
    echo 'AcceptDisputeResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# List Dispute Evidence

Returns a list of evidence associated with a dispute.

```php
function listDisputeEvidence(string $disputeId, ?string $cursor = null): ListDisputeEvidenceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute. |
| `cursor` | `?string` | Query, Optional | A pagination cursor returned by a previous call to this endpoint.<br>Provide this cursor to retrieve the next set of results for the original query.<br>For more information, see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). |

## Requires scope

### oauth2

`DISPUTES_READ`

## Response Type

**200**: Success

[`ListDisputeEvidenceResponse`](../../doc/models/list-dispute-evidence-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->listDisputeEvidence($disputeId);
    echo 'ListDisputeEvidenceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Create Dispute Evidence Text

Uploads text to use as evidence for a dispute challenge.

```php
function createDisputeEvidenceText(
    string $disputeId,
    CreateDisputeEvidenceTextRequest $body
): CreateDisputeEvidenceTextResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute you want to upload evidence for. |
| `body` | [`CreateDisputeEvidenceTextRequest`](../../doc/models/create-dispute-evidence-text-request.md) | Body, Required | An object containing the fields to POST for the request.<br><br>See the corresponding object definition for field details. |

## Requires scope

### oauth2

`DISPUTES_WRITE`

## Response Type

**200**: Success

[`CreateDisputeEvidenceTextResponse`](../../doc/models/create-dispute-evidence-text-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$body = CreateDisputeEvidenceTextRequestBuilder::init(
    'evidence_text0',
    'idempotency_key2'
)->build();

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->createDisputeEvidenceText(
        $disputeId,
        $body
    );
    echo 'CreateDisputeEvidenceTextResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Delete Dispute Evidence

Removes specified evidence from a dispute.

Square does not send the bank any evidence that is removed. Also, you cannot remove evidence after
submitting it to the bank using [SubmitEvidence](https://developer.squareup.com/reference/square_2021-08-18/disputes-api/submit-evidence).

```php
function deleteDisputeEvidence(string $disputeId, string $evidenceId): DeleteDisputeEvidenceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute you want to remove evidence from. |
| `evidenceId` | `string` | Template, Required | The ID of the evidence you want to remove. |

## Requires scope

### oauth2

`DISPUTES_WRITE`

## Response Type

**200**: Success

[`DeleteDisputeEvidenceResponse`](../../doc/models/delete-dispute-evidence-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$evidenceId = 'evidence_id2';

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->deleteDisputeEvidence(
        $disputeId,
        $evidenceId
    );
    echo 'DeleteDisputeEvidenceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Retrieve Dispute Evidence

Returns the evidence metadata specified by the evidence ID in the request URL path

You must maintain a copy of the evidence you upload if you want to reference it later. You cannot
download the evidence after you upload it.

```php
function retrieveDisputeEvidence(string $disputeId, string $evidenceId): RetrieveDisputeEvidenceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute that you want to retrieve evidence from. |
| `evidenceId` | `string` | Template, Required | The ID of the evidence to retrieve. |

## Requires scope

### oauth2

`DISPUTES_READ`

## Response Type

**200**: Success

[`RetrieveDisputeEvidenceResponse`](../../doc/models/retrieve-dispute-evidence-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$evidenceId = 'evidence_id2';

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->retrieveDisputeEvidence(
        $disputeId,
        $evidenceId
    );
    echo 'RetrieveDisputeEvidenceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Submit Evidence

Submits evidence to the cardholder's bank.

Before submitting evidence, Square compiles all available evidence. This includes evidence uploaded
using the [CreateDisputeEvidenceFile](https://developer.squareup.com/reference/square_2021-08-18/disputes-api/create-dispute-evidence-file) and
[CreateDisputeEvidenceText](https://developer.squareup.com/reference/square_2021-08-18/disputes-api/create-dispute-evidence-text) endpoints and
evidence automatically provided by Square, when available.

```php
function submitEvidence(string $disputeId): SubmitEvidenceResponse
```

## Authentication

This endpoint requires [oauth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The ID of the dispute that you want to submit evidence for. |

## Requires scope

### oauth2

`DISPUTES_WRITE`

## Response Type

**200**: Success

[`SubmitEvidenceResponse`](../../doc/models/submit-evidence-response.md)

## Example Usage

```php
$disputeId = 'dispute_id2';

$disputesController = $client->getDisputesController();

try {
    $result = $disputesController->submitEvidence($disputeId);
    echo 'SubmitEvidenceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

