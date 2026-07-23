
# Tax Ids

The tax IDs that a Location is operating under.

## Structure

`TaxIds`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `euVat` | `?string` | Optional | The EU VAT number for this location. For example, "IE3426675K".<br>If the EU VAT number is present, it is well-formed and has been<br>validated with VIES, the VAT Information Exchange System. | getEuVat(): ?string | setEuVat(?string euVat): void |
| `frNaf` | `?string` | Optional | The French government uses the NAF (Nomenclature des Activités Françaises) to display and<br>track economic statistical data. This is also called the APE (Activite Principale de l’Entreprise) code.<br>For example, 6910Z. | getFrNaf(): ?string | setFrNaf(?string frNaf): void |
| `frSiret` | `?string` | Optional | The SIRET (Système d'Identification du Répertoire des Entreprises et de leurs Etablissements)<br>number is a 14 digits code issued by the French INSEE. For example, "39922799000021". | getFrSiret(): ?string | setFrSiret(?string frSiret): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\TaxIdsBuilder;

$taxIds = TaxIdsBuilder::init()
    ->euVat('eu_vat8')
    ->frNaf('fr_naf4')
    ->frSiret('fr_siret6')
    ->build();
```

