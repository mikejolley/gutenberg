BlockEditorProvider
===================

BlockEditorProvider is a component which establishes a new block editing context, and serves as the entry point for a new block editor. It is implemented as a [controlled input](https://reactjs.org/docs/forms.html#controlled-components), expected to receive a value of a blocks array, calling `onChange` and/or `onInput` when the user interacts to change blocks in the editor. It is intended to be used as a wrapper component, where its children comprise the user interface through which a user modifies the blocks value.

## Props

### `value`

* **Type:** `Array`
* **Required** `no`

The current array of blocks.

### `onChange`

* **Type:** `Function`
* **Required** `no`

A callback invoked when the blocks have been modified in a persistent manner. Contrasted with `onInput`, a "persistent" change is one which is not an extension of a composed input. Any update to a distinct block or block attribute is treated as persistent.

### `onInput`

* **Type:** `Function`
* **Required** `no`

A callback invoked when the blocks have been modified in a non-persistent manner. Contrasted with `onChange`, a "non-persistent" change is one which is part of a composed input. Any sequence of updates to the same block attribute are treated as non-persistent, except for the first.

### `onBlockAttributesChange`

* **Type:** `Function`
* **Required** `no`

A callback to be invoked when a single block's attributes have been updated. The callback is passed the block's `clientId` and an `attributes` object containing only the updated properties of the attributes. The callback is invoked immediately before `onChange` or `onInput`.

### `children`

* **Type:** `WPElement`
* **Required** `no`

Children elements for which the BlockEditorProvider context should apply.
