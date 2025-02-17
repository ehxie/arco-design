`````
Component / Data Entry

# Cascader

Display options in a multi-level cascading dropdown component.
`````

%%Content%%

## API

### Cascader

|Property|Description|Type|DefaultValue|Version|
|---|---|---|---|---|
|defaultValue|Initial value|`(string \| string[])[]`|`-`|-|
|inputValue|Input Value|`string`|`-`|2.34.0|
|value|To set value|`(string \| string[])[]`|`-`|-|
|options|The data of options|`T[]`|`[]`|-|
|expandTrigger|Set the way to display the next level menu. One of hover and click|`'click' \| 'hover'`|`click`|-|
|changeOnSelect|Each selection will change valueif set to true.when `mode=multiple`, child node and parent node will not affect each other.|`boolean`|`-`|-|
|showEmptyChildren|Whether to render the next level node when the children of the selected option is an empty array|`boolean`|`-`|-|
|unmountOnExit|Whether destroy popup when hidden.|`boolean`|`-`|-|
|mode|Set mode|`'multiple'`|`-`|-|
|notFoundContent|The content to show when no result matches|`ReactNode`|`-`|-|
|fieldNames|Custom field name for label, value, isLeaf, disabled and children|`FieldNamesType`|`DefaultFieldNames`|-|
|popupVisible|Whether the popup is visible|`boolean`|`-`|-|
|defaultPopupVisible|Whether the popup is visible by default|`boolean`|`-`|-|
|checkedStrategy|Customize the return value<br/> parent:Only return the parent node when all child nodes are selected <br/> child: Return child nodes|`'parent' \| 'child'`|`child`|2.31.0|
|dropdownRender|Customize the popup menu.|`(menu: ReactNode) => ReactNode`|`-`|2.15.0|
|dropdownColumnRender|Customize columns of the menu.|`(menu: ReactNode, level: number) => ReactNode`|`-`|2.15.0, `level` in 2.17.0|
|filterOption|Customize the search logic.|`(inputValue: string, option: NodeProps<T>) => boolean`|`-`|-|
|renderOption|Custom rendering `option`|`(option: NodeProps<T>, level: number) => ReactNode`|`-`|-|
|renderFooter|Custom rendering the `footer` of each level menu.|`(level: number, activeOption: NodeProps<T> \| null) => ReactNode`|`-`|-|
|renderFormat|The return value will be displayed in the input box.|`(valueShow: any[]) => ReactNode`|`-`|-|
|onSearch|Callback when input changed.(reason in `2.34.0`)|`(inputValue: string, reason: InputValueChangeReason) => void`|`-`|2.20.0|
|onChange|Callback when finishing select.|`(value: (string \| string[])[],selectedOptions,extra: { dropdownVisible?: boolean }) => void`|`-`|-|
|onInputValueChange|Callback when inputValue change.|`(inputValue: string, reason: InputValueChangeReason) => void`|`-`|2.34.0|
|getPopupContainer|ParentNode which the selector should be rendered to.|`(node: HTMLElement) => Element`|`-`|-|
|loadMore|To load option lazily|`(pathValue: string[], level: number) => Promise<T[]>`|`-`|-|
|onVisibleChange|Callback when popup shown or hidden.|`(visible: boolean) => void`|`-`|-|
|onClear|Callback when click clear icon.|`(visible: boolean) => void`|`-`|-|
|animation|Whether to add animation for internal label changes|`boolean`|`true`|2.15.0|
|renderTag|Custom tag rendering, `props` is the current tag attribute, `index` is the order of the current tag, `values` is the value of all tags|`(props: {value: any;label: ReactNode;closable: boolean;onClose: (event) => void;},index: number,values: ObjectValueType[]) => React.ReactNode`|`-`|index、values added in 2.15.0|
|className|Additional css class|`string \| string[]`|`-`|-|
|placeholder|Placeholder of element|`string`|`-`|-|
|style|Additional style|`CSSProperties`|`-`|-|
|prefix|Customize select suffix|`ReactNode`|`-`|2.11.0|
|onClick|Callback when the mouse clicks on the drop-down box|`(e) => void`|`-`|-|
|size|Height of element, `24px` `28px` `32px` `36px`|`'mini' \| 'small' \| 'default' \| 'large'`|`-`|-|
|disabled|Whether is disabled|`boolean`|`-`|-|
|loading|Whether is in loading|`boolean`|`-`|-|
|bordered|Whether to render border|`boolean`|`true`|-|
|showSearch|Whether single mode Select is searchable. `{ retainInputValue: true }` to retain the existing content when the search box is focused,`{ retainInputValueWhileSelect: true }` to retain the existing content when multiple selection is selected.|`boolean \| { retainInputValue?: boolean; retainInputValueWhileSelect?: boolean }`|`-`|-|
|error|Error Style|`boolean`|`-`|-|
|allowClear|Whether allow to clear selected options|`boolean`|`-`|-|
|maxTagCount|The maximum number of `tags` is displayed, only valid in `multiple` and `label` mode.|`number`|`-`|-|
|suffixIcon|Customize select suffix icon|`ReactNode`|`-`|-|
|arrowIcon|Customize select arrow icon.|`ReactNode \| null`|`-`|-|
|removeIcon|Customize the delete icon of tags selected in `multiple` and `label` mode.|`ReactNode \| null`|`-`|-|
|clearIcon|Configure the icon of the clear button when `allowClear`.|`ReactNode`|`-`|2.26.0|

## Methods

| Name |     Description     |    Type    | Default Value |
| ------ | :----------: | :--------: | -----: |
| focus  |   Get focus   | `Function` |    `-` |
| blur   | Remove focus | `Function` |    `-` |

**Demo**

```js
<Cascader ref={(ref) => (this.select = ref)} />;

this.select.focus();
this.select.blur();
```

### `OptionProps`

```
interface OptionProps {
  value?: string;
  /** option text */
  label?: string;
  /** whether to disable this option */
  disabled?: boolean;
  /** children nodes */
  children?: OptionProps[];
  /** Is it a leaf node */
  isLeaf?: boolean;
  /** Whether to disable the checkbox (`v2.21.0`) */
  disableCheckbox?: boolean;
  [key: string]: any;
}
```

### `FieldNamesType`

```
type FieldNamesType = {
  /** Custom field name for  label   */
  label?: string;
  /** Custom field name for value  */
  value?: string;
  /** Custom field name for children  */
  children?: string;
  /** Custom field name for disabled  */
  disabled?: string;
  /** Custom field name for isLeaf  */
  isLeaf?: string;
}
```
