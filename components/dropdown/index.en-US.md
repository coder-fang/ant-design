---
category: Components
group: Navigation
title: Dropdown
cover: https://mdn.alipayobjects.com/huamei_7uahnr/afts/img/A*mBBcQ6goljkAAAAAAAAAAAAADrJ8AQ/original
demo:
  cols: 2
---

A dropdown list.

## When To Use

When there are more than a few options to choose from, you can wrap them in a `Dropdown`. By hovering or clicking on the trigger, a dropdown menu will appear, which allows you to choose an option and execute the relevant action.

### Usage upgrade after 4.24.0

<Alert message="After version 4.24.0, we provide a simpler usage &lt;Dropdown menu={{ items: [...] }} /&gt; with better performance and potential of writing simpler code style in your applications. Meanwhile, we deprecated the old usage in browser console, we will remove it in antd 5.0."></Alert>

```jsx
// works when >=4.24.0, recommended ✅
const items = [
  { label: 'item 1', key: 'item-1' }, // remember to pass the key prop
  { label: 'item 2', key: 'item-2' },
];
return (
  <Dropdown menu={{ items }}>
    <a>Hover me</a>
  </Dropdown>
);

// works when <4.24.0, deprecated when >=4.24.0 🙅🏻‍♀️
const menu = (
  <Menu>
    <Menu.Item>item 1</Menu.Item>
    <Menu.Item>item 2</Menu.Item>
  </Menu>
);
return (
  <Dropdown overlay={menu}>
    <a>Hover me</a>
  </Dropdown>
);
```

## Examples

<!-- prettier-ignore -->
<code src="./demo/deprecated.tsx">Basic usage (deprecated syntactic sugar)</code>
<code src="./demo/basic.tsx">Basic</code>
<code src="./demo/placement.tsx">Placement</code>
<code src="./demo/arrow.tsx">Arrow</code>
<code src="./demo/item.tsx">Other elements</code>
<code src="./demo/arrow-center.tsx">Arrow pointing at the center</code>
<code src="./demo/trigger.tsx">Trigger mode</code>
<code src="./demo/event.tsx">Click event</code>
<code src="./demo/dropdown-button.tsx">Button with dropdown menu</code>
<code src="./demo/custom-dropdown.tsx">Custom dropdown</code>
<code src="./demo/sub-menu.tsx">Cascading menu</code>
<code src="./demo/overlay-open.tsx">The way of hiding menu.</code>
<code src="./demo/context-menu.tsx">Context Menu</code>
<code src="./demo/loading.tsx">Loading</code>
<code src="./demo/selectable.tsx">Selectable Menu</code>
<code src="./demo/menu-full.tsx" debug>Menu full styles</code>
<code src="./demo/render-panel.tsx" debug>\_InternalPanelDoNotUseOrYouWillBeFired</code>

## API

### Dropdown

| Property | Description | Type | Default | Version |
| --- | --- | --- | --- | --- |
| arrow | Whether the dropdown arrow should be visible | boolean \| { pointAtCenter: boolean } | false |  |
| autoFocus | Focus element in `overlay` when opened | boolean | false | 4.21.0 |
| disabled | Whether the dropdown menu is disabled | boolean | - |  |
| destroyPopupOnHide | Whether destroy dropdown when hidden | boolean | false |  |
| dropdownRender | Customize dropdown content | (menus: ReactNode) => ReactNode | - | 4.24.0 |
| getPopupContainer | To set the container of the dropdown menu. The default is to create a div element in body, but you can reset it to the scrolling area and make a relative reposition. [Example on CodePen](https://codepen.io/afc163/pen/zEjNOy?editors=0010) | (triggerNode: HTMLElement) => HTMLElement | () => document.body |  |
| menu | The menu props | [MenuProps](/components/menu/#API) | - | 4.24.0 |
| overlayClassName | The class name of the dropdown root element | string | - |  |
| overlayStyle | The style of the dropdown root element | CSSProperties | - |  |
| placement | Placement of popup menu: `bottom` `bottomLeft` `bottomRight` `top` `topLeft` `topRight` | string | `bottomLeft` |  |
| trigger | The trigger mode which executes the dropdown action. Note that hover can't be used on touchscreens | Array&lt;`click`\|`hover`\|`contextMenu`> | \[`hover`] |  |
| open | Whether the dropdown menu is currently open. Use `visible` under 4.23.0 ([why?](/docs/react/faq#why-open)) | boolean | - | 4.23.0 |
| onOpenChange | Called when the open state is changed. Not trigger when hidden by click item. Use `onVisibleChange` under 4.23.0 ([why?](/docs/react/faq#why-open)) | (open: boolean) => void | - | 4.23.0 |

### Dropdown.Button

Same props from Dropdown. And includes additional props:

| Property | Description | Type | Default | Version |
| --- | --- | --- | --- | --- |
| buttonsRender | Custom buttons inside Dropdown.Button | (buttons: ReactNode\[]) => ReactNode\[] | - |  |
| loading | Set the loading status of button | boolean \| { delay: number } | false |  |
| danger | Set the danger status of button | boolean | - | 4.23.0 |
| icon | Icon (appears on the right) | ReactNode | - |  |
| size | Size of the button, the same as [Button](/components/button/#API) | string | `default` |  |
| type | Type of the button, the same as [Button](/components/button/#API) | string | `default` |  |
| onClick | The same as [Button](/components/button/#API): called when you click the button on the left | (event) => void | - |  |
