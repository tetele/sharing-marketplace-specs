# Entities

These are the entities that are being used in the rest of the docs.

## Item-level Entities

### Item

Represents a certain object type/service type that can be traded in the platform.
An item can be any type of good or service, regarded as a blueprint. Think of something like nursing services or a certain face mask etc.
It might be particular, rather than general. For example, a 1 liter Vittel water bottle, rather than a 1l water bottle or a bottle of Vittel.

Properties:
Name | Type | Description
--- | --- | ---
Name | String | The item's name
Category | [ItemCategory](#itemcategory) | The item's category

### ItemCategory

Represents a category of items, in a tree structure. Each category (except the root category) has a parent category.

Properties:
Name | Type | Description
--- | --- | ---
Name | String | The category name
Parent | [ItemCategory](#itemcategory) | The parent category of the current category
