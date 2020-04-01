# Functional requirements

Here you can find a list of functional requirements that the Sharing Marketplace app will need to cover.

## Supply driven

### Supplier posts offer

A supplier must be able to post [an offer](../entities/index.md#transaction) for certain goods that he can trade or donate.

For each of those items, he must be able to specify:
- the item name
- if using a yet untraded item, an optional [item category](../entities/index.md#itemcategory) (he can choose from an existing list or he can add a new category)
- the [properties](../entities/index.md#itemproperty) of the item (he can use existing [characteristics](../entities/index.md#itemcharacteristic) or he can add new ones; for each characteristic, the supplier must assign a value)
- the quantity of available such item
- the per unit price of the item

The resulting [`Transaction`](../entities/index.md#transaction) is an offer, i.e. the `Transaction.Requester` is null. The `Transaction.Investor` will be the user posting the offer if the total costs are 0, or null if there are any costs involved.
