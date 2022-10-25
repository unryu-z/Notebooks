- **`Node`** 是一个接口，各种类型的 DOM API 对象会从这个接口继承属性对象属性和对象方法。允许使用相似的方式对待这些不同类型的对象；

- 以下接口都从 `Node` 继承其方法和属性：

  [`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document)、[`Element`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element)、[`Attr`](https://developer.mozilla.org/zh-CN/docs/Web/API/Attr)、[`CharacterData`](https://developer.mozilla.org/zh-CN/docs/Web/API/CharacterData) (which [`Text`](https://developer.mozilla.org/zh-CN/docs/Web/API/Text), [`Comment`](https://developer.mozilla.org/zh-CN/docs/Web/API/Comment), and [`CDATASection`](https://developer.mozilla.org/zh-CN/docs/Web/API/CDATASection) inherit), [`ProcessingInstruction` (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction), [`DocumentFragment`](https://developer.mozilla.org/zh-CN/docs/Web/API/DocumentFragment), [`DocumentType`](https://developer.mozilla.org/zh-CN/docs/Web/API/DocumentType)；

- 在方法和属性不相关的特定情况下，这些接口可能返回 `null`。它们可能会抛出异常

- 会从 其父类型 [`EventTarget`](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget)继承属性和方法；





# 属性

## 获取节点

- [`Node.childNodes`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/childNodes) 只读：返回一个包含了该节点 **所有子节点** 的实时的[`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList)。
  - [`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList) 是动态变化的。如果该节点的子节点发生了变化，[`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList) 对象就会自动更新。
- [`Node.firstChild`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/firstChild) 只读：返回 该节点的 **第一个子节点**；如果该节点没有子节点，则返回 `null`。
- [`Node.lastChild`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/lastChild) 只读：返回 该节点的 **最后一个子节点**；如果该节点没有子节点，则返回 `null`。
- [`Node.previousSibling`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/previousSibling) 只读：返回 与该节点同级的 **前一个节点**；如果没有，则返回 `null`。
- [`Node.nextSibling`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/nextSibling) 只读：返回 与该节点同级的 **下一个节点**；如果没有，则返回 `null`。
- [`Node.parentNode`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/parentNode) 只读：返回一个当前节点的 **父节点**。如果没有这样的节点，这个属性返回 null。
- [`Node.parentElement`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/parentElement) 只读：返回一个当前节点的 **父节点元素** 。如果当前节点 没有父节点 或者 父节点不是一个元素，这个属性返回 null。



- [`Node.ownerDocument`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/ownerDocument) 只读：返回这个元素属于的 [`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document)对象。
  - 如果没有 Document 对象与之关联，返回 null。



- [`Node.textContent`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/textContent)：返回或设置 一个元素内所有子节点及其后代的 **文本内容** (元素内容以文本形式返回)；
- [`Node.nodeType`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/nodeType) 只读：返回一个 与该节点类型对应的无符号短整型的 值，可能的值如下为 `1` ~ `12`；

- [`Node.nodeName`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/nodeName) 只读：返回一个 包含该节点名字的 String原始值。

  - 节点的名字的结构 和 节点类型 不同。比如 [`HTMLElement`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement) 的名字跟它所关联的标签对应，就比如[`HTMLAudioElement`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLAudioElement) 的就是 `'audio'` ，[`Text`](https://developer.mozilla.org/zh-CN/docs/Web/API/Text) 节点对应的是 `'#text'`，[`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document) 节点对应的是 `'#document'`；

  | 常量                               | 值   | 描述                                                         |
  | :--------------------------------- | :--- | :----------------------------------------------------------- |
  | `Node.ELEMENT_NODE`                | `1`  | 一个 [`元素`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element) 节点，例如 `<p>` 和 `<div>`。 |
  | `Node.ATTRIBUTE_NODE`              | `2`  | [`元素`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element) 的耦合 [`属性`](https://developer.mozilla.org/zh-CN/docs/Web/API/Attr)。 |
  | `Node.TEXT_NODE`                   | `3`  | [`Element`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element) 或者 [`Attr`](https://developer.mozilla.org/zh-CN/docs/Web/API/Attr) 中实际的 [`文字`](https://developer.mozilla.org/zh-CN/docs/Web/API/Text) |
  | `Node.CDATA_SECTION_NODE`          | `4`  | 一个 [`CDATASection`](https://developer.mozilla.org/zh-CN/docs/Web/API/CDATASection)，例如 `<!CDATA[[ … ]]>`。 |
  | `Node.PROCESSING_INSTRUCTION_NODE` | `7`  | 一个用于 XML 文档的 [`ProcessingInstruction` (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction) ，例如 `<?xml-stylesheet ... ?>` 声明。 |
  | `Node.COMMENT_NODE`                | `8`  | 一个 [`Comment`](https://developer.mozilla.org/zh-CN/docs/Web/API/Comment) 节点。 |
  | `Node.DOCUMENT_NODE`               | `9`  | 一个 [`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document) 节点。 |
  | `Node.DOCUMENT_TYPE_NODE`          | `10` | 描述文档类型的 [`DocumentType`](https://developer.mozilla.org/zh-CN/docs/Web/API/DocumentType) 节点。例如 `<!DOCTYPE html>` 就是用于 HTML5 的。 |
  | `Node.DOCUMENT_FRAGMENT_NODE`      | `11` | 一个 [`DocumentFragment`](https://developer.mozilla.org/zh-CN/docs/Web/API/DocumentFragment) 节点 |

  以下的常量已被弃用且不再使用：`Node.ENTITY_REFERENCE_NODE`（`5`）、`Node.ENTITY_NODE`（`6`）和 `Node.NOTATION_NODE`（`12`）。

- [`Node.nodeValue`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/nodeValue)：返回或设置当前节点的值。下表就是不同类型的节点所返回的该属性的值。

  | Node                                                         | Value of nodeValue |
  | :----------------------------------------------------------- | :----------------- |
  | [`CDATASection`](https://developer.mozilla.org/zh-CN/docs/Web/API/CDATASection) | CDATA 的文本内容   |
  | [`Comment`](https://developer.mozilla.org/zh-CN/docs/Web/API/Comment) | 注释的文本内容     |
  | [`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document) | null               |
  | [`DocumentFragment`](https://developer.mozilla.org/zh-CN/docs/Web/API/DocumentFragment) | null               |
  | [`DocumentType`](https://developer.mozilla.org/zh-CN/docs/Web/API/DocumentType) | null               |
  | [`Element`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element) | null               |
  | [`NamedNodeMap`](https://developer.mozilla.org/zh-CN/docs/Web/API/NamedNodeMap) | null               |
  | `EntityReference`                                            | null               |
  | `Notation`                                                   | null               |
  | [`ProcessingInstruction` (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/ProcessingInstruction) | 整个标签的文本内容 |
  | [`Text`](https://developer.mozilla.org/zh-CN/docs/Web/API/Text) | 文本节点的内容     |

  如果 `nodeValue` 的值为 `null`，则对它赋值不会有任何效果。



## DOM树 关系

- [`Node.isConnected `](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/isConnected) 只读：返回一个布尔值，用来检测该节点是否已 **连接** (直接或者间接) 到一个上下文对象上，比如通常 DOM 情况下的[`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document)对象，或者在 shadow DOM 情况下的[`ShadowRoot`](https://developer.mozilla.org/zh-CN/docs/Web/API/ShadowRoot)对象。





# 方法

## 获取节点

- [`Node.getRootNode()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/getRootNode)：返回上下文对象的 **根节点**。如果 shadow root 节点存在的话，也可以在返回的节点中包含它。





## 修改 DOM 树

- [`Node.appendChild()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/appendChild)：将指定的 childNode 参数作为 最后一个 **子节点** **添加** 到当前节点。 
  - 如果参数引用了 DOM 树上的现有节点，则节点将从当前位置分离，并附加到新位置。
- [`Node.cloneNode()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/cloneNode)：克隆一个 [`Node`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node)，并且可以选择是否 **克隆** 这个节点下的所有内容。
  - 默认情况下 `true`，节点下的内容会被克隆。
- [`Node.insertBefore()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/insertBefore)：在当前节点下 **增加** 一个 **子节点**，并使该子节点 位于参考节点的前面。
- [`Node.removeChild()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/removeChild)：**移除** 当前节点的一个 **子节点**。这个子节点必须存在于当前节点中。
- [`Node.replaceChild()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/replaceChild)：对选定的节点，**替换** 一个子节点 为 另外一个节点。
- [`Node.normalize()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/normalize)：对该元素下的 所有文本子节点进行整理，合并相邻的文本节点并清除空文本节点。







## DOM树 关系

- [`Node.compareDocumentPosition()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/compareDocumentPosition)：比较当前节点与任意文档中的另一个节点的 **位置关系**。
- [`Node.contains()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/contains)：返回一个 [`Boolean`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Boolean) 布尔值，来表示传入的节点 **是否为** 该节点的 **后代节点**。
- [`Node.hasChildNodes()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/hasChildNodes)：返回一个[`Boolean`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Boolean) 布尔值，来表示该元素 **是否含有 子节点**。







