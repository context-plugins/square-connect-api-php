
# V1 List Payments Response

## Structure

`V1ListPaymentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `items` | [`?(V1Payment[])`](../../doc/models/v1-payment.md) | Optional | - | getItems(): ?array | setItems(?array items): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\V1ListPaymentsResponseBuilder;
use SquareConnectAPILib\Models\Builders\V1PaymentBuilder;
use SquareConnectAPILib\Models\Builders\V1PaymentTaxBuilder;
use SquareConnectAPILib\Models\Builders\V1MoneyBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\DeviceBuilder;

$v1ListPaymentsResponse = V1ListPaymentsResponseBuilder::init()
    ->items(
        [
            V1PaymentBuilder::init()
                ->additiveTax(
                    [
                        V1PaymentTaxBuilder::init()
                            ->appliedMoney(
                                V1MoneyBuilder::init()
                                    ->amount(196)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->errors(
                                [
                                    ErrorBuilder::init(
                                        'category8',
                                        'code8'
                                    )
                                        ->detail('detail6')
                                        ->field('field4')
                                        ->build()
                                ]
                            )
                            ->feeId('fee_id0')
                            ->inclusionType('inclusion_type8')
                            ->name('name2')
                            ->build(),
                        V1PaymentTaxBuilder::init()
                            ->appliedMoney(
                                V1MoneyBuilder::init()
                                    ->amount(196)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->errors(
                                [
                                    ErrorBuilder::init(
                                        'category8',
                                        'code8'
                                    )
                                        ->detail('detail6')
                                        ->field('field4')
                                        ->build()
                                ]
                            )
                            ->feeId('fee_id0')
                            ->inclusionType('inclusion_type8')
                            ->name('name2')
                            ->build(),
                        V1PaymentTaxBuilder::init()
                            ->appliedMoney(
                                V1MoneyBuilder::init()
                                    ->amount(196)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->errors(
                                [
                                    ErrorBuilder::init(
                                        'category8',
                                        'code8'
                                    )
                                        ->detail('detail6')
                                        ->field('field4')
                                        ->build()
                                ]
                            )
                            ->feeId('fee_id0')
                            ->inclusionType('inclusion_type8')
                            ->name('name2')
                            ->build()
                    ]
                )
                ->additiveTaxMoney(
                    V1MoneyBuilder::init()
                        ->amount(16)
                        ->currencyCode('currency_code2')
                        ->build()
                )
                ->createdAt('created_at6')
                ->creatorId('creator_id8')
                ->device(
                    DeviceBuilder::init()
                        ->id('id6')
                        ->name('name6')
                        ->build()
                )
                ->build(),
            V1PaymentBuilder::init()
                ->additiveTax(
                    [
                        V1PaymentTaxBuilder::init()
                            ->appliedMoney(
                                V1MoneyBuilder::init()
                                    ->amount(196)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->errors(
                                [
                                    ErrorBuilder::init(
                                        'category8',
                                        'code8'
                                    )
                                        ->detail('detail6')
                                        ->field('field4')
                                        ->build()
                                ]
                            )
                            ->feeId('fee_id0')
                            ->inclusionType('inclusion_type8')
                            ->name('name2')
                            ->build(),
                        V1PaymentTaxBuilder::init()
                            ->appliedMoney(
                                V1MoneyBuilder::init()
                                    ->amount(196)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->errors(
                                [
                                    ErrorBuilder::init(
                                        'category8',
                                        'code8'
                                    )
                                        ->detail('detail6')
                                        ->field('field4')
                                        ->build()
                                ]
                            )
                            ->feeId('fee_id0')
                            ->inclusionType('inclusion_type8')
                            ->name('name2')
                            ->build(),
                        V1PaymentTaxBuilder::init()
                            ->appliedMoney(
                                V1MoneyBuilder::init()
                                    ->amount(196)
                                    ->currencyCode('currency_code4')
                                    ->build()
                            )
                            ->errors(
                                [
                                    ErrorBuilder::init(
                                        'category8',
                                        'code8'
                                    )
                                        ->detail('detail6')
                                        ->field('field4')
                                        ->build()
                                ]
                            )
                            ->feeId('fee_id0')
                            ->inclusionType('inclusion_type8')
                            ->name('name2')
                            ->build()
                    ]
                )
                ->additiveTaxMoney(
                    V1MoneyBuilder::init()
                        ->amount(16)
                        ->currencyCode('currency_code2')
                        ->build()
                )
                ->createdAt('created_at6')
                ->creatorId('creator_id8')
                ->device(
                    DeviceBuilder::init()
                        ->id('id6')
                        ->name('name6')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

