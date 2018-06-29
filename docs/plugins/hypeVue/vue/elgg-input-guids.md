# `<elgg-input-guids>`

See `elgg-input` docs for a full list of props

## Props

|Property      |Type          |Default                      |Required      |Description                                                    |
|--------------|--------------|-----------------------------|--------------|---------------------------------------------------------------|
|`options`     |Array         |--                           |yes           |An array of select options {value: 'value', label: 'label' }   |
|`source`      |String        |`autocomplete/guids`         |no            |Data source URL                                                |
|`type`        |String        |--                           |no            |Entity type to restrict the search to                          |
|`subtype`     |String        |--                           |no            |Entity subtype to restrict the search to                       |
|`metadata`    |Object        |--                           |no            |Metadata name value pairs                                      |
|`exclude`     |Array         |--                           |no            |GUIDs to exclude from search                                   |
|`config`      |Object        |`{}`                         |no            |Configuration options passed to Select2 instance               |

## Events

|Event                         |Description                                                          |
|------------------------------|---------------------------------------------------------------------|
|`@input(value)`               |Fired when input value is updated                                    |

## Named Slots

|Slot name                     |Description                                                          |
|------------------------------|---------------------------------------------------------------------|
|`input`                       |Replaces input element                                               |

## Example

```html
<elgg-input-select
    v-model="parent.value"
    @input="doSomething"
    :options="[
       {
          value: 'option1',
          label: 'Option Label 1'
       },
       {
          value: 'option2',
          label: 'Option Label 2'
       },
    ]"
/>
```
