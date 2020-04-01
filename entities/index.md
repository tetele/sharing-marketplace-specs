# Entities

These are the entities that are being used in the rest of the docs.

## User-level Entities

Users are the people that actually trade on this platform.

### User

Represents a person or institution that takes some part in the trading that goes on in this platform.
Depending on the context they are in, users can be requesters, suppliers, investors or a combination of those roles. In different contexts, users can take on different roles.

Requesters are those who are looking for goods or services, suppliers are those who have goods or services to offer, while investors are those who make sure that transactions are paid for in order for the actual trade to happen.

Properties:
Name | Type | Description
--- | --- | ---
Username | String | Any identifier is good for now

## Item-level Entities

Items are the actual things that get traded - goods, services.

### Item

Represents a certain object type/service type that can be traded in the platform.
An item can be any type of good or service, regarded as a blueprint. Think of something like nursing services or a certain face mask etc.
It might be particular, rather than general. For example, a 1 liter Vittel water bottle, rather than a 1l water bottle or a bottle of Vittel.

Properties:
Name | Type | Description
--- | --- | ---
Name | String | The item's name
Category | [`ItemCategory`](#itemcategory) | The item's category
Properties | `0..*` [`ItemProperty`](#itemproperty) | Zero or more properties that pertain to the item. Inverse of `ItemProperty.Item`

### ItemCategory

Represents a category of items, in a tree structure. Each category (except the root category) has a parent category.

Properties:
Name | Type | Description
--- | --- | ---
Name | String | The category name
Parent | [`ItemCategory`](#itemcategory) | The parent category of the current category

### ItemCharacteristic

Defines a certain characteristic that may be common to several items.

Properties:
Name | Type | Description
--- | --- | ---
Name | String | The characteristic's name
UnitOfMeasure | String | The characteristic's UnitOfMeasure (optional)

### ItemProperty

The actual value of a item's characteristic.

Properties:
Name | Type | Description
--- | --- | ---
Item | [`Item`](#item) | The parent item. Inverse of `Item.Properties`
Characteristic | [`ItemCharacteristic`](#itemcharacteristic) | The characteristic whose value is represented
Value | String | The actual value
