

# Getting Started

## Intoduction


### 单词 vocabulary

---

`author`- 编写

`abbreviated /ə'brivɪ'et/ as SFC` - 用 SFC 缩写

`as the name suggests,`- 顾名思义

`encapsulates` - 封装

`be it simple or complex.  `- 无论是简单还是复杂。

`Prerequisites `-  前提；必要条件 

`grasp the basics `- 掌握基础知识

`Prior experience `- 先前的经验

`Progressive /prə'ɡrɛsɪv/ `- 逐步发生的，逐步发展的

`extremely diverse /dɪ'vɝs/ ` - 各式各样的.. 及其多样化

`the things we build on the web may vary drastically /ˈdræstɪklɪ/ in form and scale. `- 在形式和规模上可能有很大的不同。 (vary变化 drastically大大地彻底的)

`With that in mind `- 考虑到这一点

`Vue is designed to be flexible and incrementally  /ɪnkrə'məntl/ adoptable.`- Vue旨在灵活且逐步采用 (增量可采用性)。

`intimidating `- 令人惊恐的;骇人的;令人胆怯的 

`tackle /ˈtækəl/ more ambitious goals `- 实现更远大的目标

`veteran /'vɛtərən/ ` - 老手

`optimal /'ɑptəml/` - 同 optimum 最优的最佳的最适宜的

`leverage /'lɛvərɪdʒ/` - 利用

`you can pick the optimal way to leverage Vue based on the problems you are trying to solve`- 你可以挑选最后方式来利用 vue , 基于你尝试解决的问题

`retain `- 保持

`adapt `- 适合

`defining feature` - 最典型的特征

`if your use case warrants /'wɔrənt/ a build setup. `  - 如果你的案例保证了了 warrants 保证

`dedicated /'dɛdə'ketɪd/ section` dedicated 为…专门设计 You can learn more about the [how and why of SFC](https://vuejs.org/guide/scaling-up/sfc.html) in its dedicated section

`typically` - 一般的

`compile-time transforms` - 编译时转换

`boilerplate/'bɔɪlɚplet/` - 样板文件

`on top of `- 在…上面

`aligns` - 对准, 使成为一条直线 which typically aligns better with a class-based mental model

`effectively /ɪ'fɛktɪvli/` - 实际上,事实上

`In return,` - 反过来

`patterns`-模式

`going over all content ` - 浏览所有内容



---

### Vue can be used in different ways:

1. Enhancing static HTML without a build step - 增强静态html
2. Embed as Web Components on any page - 作为网络组件嵌入在任何 page
3. Single-Page Application (SPA)
4. Server-SideRendering (SSR)
5. Static-Site-Generation (SSG)
6. Targeting desktop, mobile, WebGL or even the terminal

Despite the flexibility, the core knowledge about how Vue works is shared across all these use cases (核心知识在这 6 个使用场景共享). 



### Single-File Components

> A Vue SFC, as the name suggests, encapsulates the component's logic (JavaScript), template (HTML), and styles (CSS) in a single file.

- SFC is a defining feature of Vue, 

### API Style

Vue components can be authored in two different API styles: **Options API** and **Composition API**.

With Composition API,  we define a component’s logic using imported API functions. 

The `setup` attribute is a hint that makes Vue perform compile-time transforms that allow us to use Composition API with less boilerplate. For example, **imports and top-level variables / functions** declared in `<script setup>` are directly usable in the template.

### Which to choose ?

the Options API is implemented on top of the Composition API! 

The **Options API** is centered around (以… 为中心) the concept of a "component instance" (`this` as seen in the example), which typically aligns better (更好的对齐, 更符合) with a class-based mental model for users coming from OOP language backgrounds.

The **Composition API** is centered around declaring reactive state variables directly in a function scope, and composing state from multiple functions together to handle complexity. It is more free-form, and requires understanding of how reactivity works in Vue to be used effectively. In return, its flexibility enables more powerful patterns for organizing and reusing logic.



## Quick Start

### Vocabulary

---

`identical` - 完全一样的

`scaffolding /'skæfəldɪŋ/ tool` - 脚手架工具

`for now` - 眼下, 当下, 暂时如此 simply choose `No` by hitting enter for now (暂时选 No)

`viable/ˈvaɪəbəl/ ` - 可行的

`underlying build tool Vite` - 底层的构建工具

`ship your app to production` - 将你的产品交付生产

`consistency` 连贯性;一致性

`primarily` 主要的

`chromium/'kromɪəm/` 谷歌浏览器的, 铬元素, 金属风格

---

### With build tools
>
>To create a build-tool-enabled Vue project on your machine

```sh
npm init vue@latest
```

### Without build tools

```html
<script src="https://unpkg.com/vue@3"></script>

<div id="app">{{ message }}</div>

<script>
  Vue.createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```

But if we want to use ES modules for consistency , use the following HTML instead:

```html
<script type="importmap">
  // importmap only works in chromium-based browsers like chrome or edge

  {
    "imports": {
      "vue": "https://unpkg.com/vue@3/dist/vue.esm-browser.js"
    }
  }
</script>

<div id="app">{{ message }}</div>

<script type="module">
  import { createApp } from 'vue'

  createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```

### [Serving over HTTP](https://vuejs.org/guide/quick-start.html#serving-over-http)

If we want to split code into separate js files, we need to author like this

```html
<!-- index.html -->
<script type="module">
  import { createApp } from 'vue'
  import MyComponent from './my-component.js'

  createApp(MyComponent).mount('#app')
</script>
```

```js
// my-component.js
export default {
  data() {
    return { count: 0 }
  },
  template: `<div>count is {{ count }}</div>`
}
```



Run `npx serve` from the command line in the same directory where your HTML is. Or it desn’t work.



Use **es6-string-html** in es6 HTML strings, it will get hightlight support







# Essentials

## Create a Vue Application

### Vocabulary

---

`expects` 期望, 需要

`registrations/'rɛdʒɪ'streʃən/`  注册

`descendent/dɪˈsɛndənt/` 子孙 后代



---

### The Root Component

The object we pass to `createApp` is a component, and it’s a root component.

### Mounting the App

An application instance won't render anything until its `.mount()` method is called. 





## Template syntax

### Vocabulary

---

`declaratively/dɪ'klærətɪv/`  声明的

`underlying component` 底层的组件

`syntactically /sin'tæktikli/ ` 语法层面上 syntactically valid HTML(语法合规的 HTML)

`spec-compliant ` 符合规范的

`compliant /kəm'plaɪənt` 服从的, 顺从的

`hood` 盖子, 引擎盖, 罩子

`Under the hood` 藏在表面之下的机制或结构, 在后台

`reactivity[ˌri:æk'tɪvɪti] ` 反应度；反应能力；活动性, 反应性

`intelligently /ɪnˈtelɪdʒəntli/` 聪明的明智的

`DOM manipulations  [məˌnɪpjəˈleɪʃ(ə)n] ` 操作操纵

`Interpolation [ɪnˌtɚpəˈleɪʃən] ` 插入文字

`curly braces` 花括号 `{}`

`corresponding /ˌkɔrəˈspɑndɪŋ/` 相应的

`interprets/ɪnˈtɜrprət/` 解释

`directive /daɪˈrektɪv/` 指示,命令

`arbitrary` 任意的 武断的

`XSS vulnerability/ˌvʌlnərə'biliti/ ` 缺陷弱点

`evaluate /ɪˈvæljuˌeɪt/`【数】求…的值

`asynchronous /ei'siŋkrənəs/` 异步的

`Restricted ` 限制有限的

`explicitly /ɪk'splɪsɪtli/` 明确的, 露骨的

`are expected to` 应该是

`with the exception of ` 除了…之外 exception例外除外

`truthiness` 真实

`denote /dɪˈnoʊt/` 表示

`colon/'kolən/ ` 冒号 `denoted by a colon after the directive name` 

`square brackets` 方括号 `[]`

`Constraints  /kən'strent/` 限制;束缚;约束 

`quotes` 引号

`coerce/kəʊ'ɜːs/ ` 强制胁迫

`modifier` 修饰语, 改良剂

`postfixes` 后缀

`visualized /viʒuə,laizd/` 直观的



---

Render function does not enjoy the same level of compile-time optimizations  as templates.

### Text Interpolation

> using the "Mustache" syntax

### Raw HTML

> using the `v-html` attribute

### Attribute Bindings

> Mustaches can't be used inside HTML attributes, Instead, use `v-bind` directive

```html
v-bind:id="dynamicId" ---Shorthand---> :id="daynamicId"
```

### Dynamically Binding Multiple Attributes

> Binding multiple attributes using a object

```vue
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
}
<div v-bind="objectOfAttrs"></div>
```

### Calling Functions

> Functions called inside binding expressions will be called every time the component updates



### Restricted Globals Access

> explicitly define additional globals for all Vue expressions by adding them to [`app.config.globalProperties`](https://vuejs.org/api/application.html#app-config-globalproperties).



### Dynamic Argument

1. Dynamic arguments are expected to evaluate to a string, with the exception of `null`. The special value `null` can be used to explicitly remove the binding. Any other non-string value will trigger a warning.
2. Dynamic argument expressions have some syntax constraints because certain characters, such as spaces and quotes, are invalid inside HTML attribute names. Use `computed` property
3. When using in-DOM templates (templates directly written in an HTML file), you should also avoid naming keys with uppercase characters, as browsers will coerce attribute names into lowercase



Full directive syntax visualized:

![img](https://vuejs.org/assets/directive.69c37117.png)







## Reactivity Fundamentals

### Vocabulary

---

`verbose/vɝ'bos/` 冗长的, 啰嗦的

`synchronous /ˈsɪŋkrənəs/` 同步的

`update cycle` 更新周期

`exclusively` 专门, 完全的

`consistent` 一致的的

`destructure` 解构

`address` 解决, 处理

`In other words` 换句话说

`Composable` 可组合

`extract` 提取提炼 - extracting logic into Composable Functions.

`Unwrapping` 解包, 展开包装

`drawback` 缺点

`imposed` 被强加

`ergonomics/'ɝgə'nɑmɪks/`  人机工程学

`experimental/ɛk'spɛrɪ'mɛntəl/` 试验性的

`finalize/'faɪnəlaɪz/` 最后确定, 最后敲定

---

### Declaring Reactive State

1. create a reactive object or array with the [`reactive()`](https://vuejs.org/api/reactivity-core.html#reactive) function:

### DOM Update Timing

o wait for the DOM update to complete after a state change, you can use the [nextTick()](https://vuejs.org/api/general.html#nexttick) global API , you need Import from ‘vue’ first

### Deep Reactivity

You can expect changes to be detected even when you mutate nested objects or arrays

Due to deep reactivity, nested objects inside a reactive object are also proxies.



### Reactive Variables with `ref()`

To address the limitations of `reactive()`, Vue also provides a [`ref()`](https://vuejs.org/api/reactivity-core.html#ref) function which allows us to create reactive **"refs"** that can hold any value type

`ref()` takes the argument and returns it wrapped (包裹, 封装) within a ref object with a `.value` property, when holding object types, ref automatically converts its `.value` with `reactive()`. 

A ref containing an object value can reactively replace the entire object:

```js
const objectRef = ref({ count: 0 })

// this works reactively
objectRef.value = { count: 1 }
```



## **[Computed Properties](https://vuejs.org/guide/essentials/computed.html)**

### Vocabulary

---

`be meant for` 注定, 意味着

`bloated/'blotɪd/` (机构组织)臃肿的

`cluttered` 杂乱的凌乱的

`probably/'prɑbəbli/` 或许可能大概

` refactor` 重构

`invocation` 调用

`In cases` 在一些情况下

` in turn ` 反过来

`destructuring` 解构的

`accordingly` 相应的

`be free of ` 远离… 免于…

`responsibility /rɪ,spɑnsə'bɪləti/` 责任

`derive` 衍生, 派生

`snapshot` 快照

----

The `computed()` function expects to be passed a getter function, and the returned value is a **computed ref**. Similar to normal refs, you can access the computed result as `publishedBooksMessage.value`. 

**computed properties are cached based on their reactive dependencies.**In comparison, a method invocation will **always** run the function whenever a re-render happens.

Computed properties are by default getter-only. 

 In the rare cases where you need a "writable" computed property, you can create one by providing both a getter and a setter:

**Getters should be side-effect free** For example, don't make async requests or mutate the DOM inside a computed getter! 

Think of a computed property as declaratively describing how to derive a value based on other values

its only responsibility should be computing and returning that value.

Think of it **as a temporary snapshot** - every time the source state changes, a new snapshot is created. **It does not make sense to mutate a snapshot,** so a computed return value should be treated as read-only and never be mutated\- instead, update the source state it depends on to trigger new computations.

## [**Class and Style Bindings**](https://vuejs.org/guide/essentials/class-and-style.html)

### Vocabulary

---

`meddle/'mɛdl/`  干预干涉 meddle with….

`concatenation /kən'kætə'neʃən/` 不可数名词一连串相关联的事情；接二连三的相关事件 string concatenation 字符串连接

`annoying` 令人厌烦的

`prone/pron/` 易于…的, 有..(不好的)倾向 error-prone: 易出错的

`In addition to ` 除了

`presence` 存在

` Feel free to` 随意

`Fallthrough` 失败落空

`camelCase` `kebab-cased ` `kebab /kɪ'bæb/` 烤串, 烤肉片 肉串上的肉块

` conjunction美 /kən'dʒʌŋkʃən/`  N - 同时发生, 同地发生 in conjunction with  共同, 协力

`appropriate /əˈproʊpriˌeɪt/`合适的



---

### class

In addition to strings, the expressions can also evaluate to objects or arrays.

the `:class` directive can also co-exist with the plain `class` attribute. So given the following state.

The bound object doesn't have to be inline.

 it's also possible to use the object syntax inside array syntax.

When you use the `class` attribute on a component with a single root element, those classes will be **added to the component's root element**, and merged with any existing class already on it.

If your component has multiple root elements, you would need to define which element will receive this class. You can do this using the `$attrs` component property

### Inline-style 







## [Conditional Rendering](https://vuejs.org/guide/essentials/conditional.html)

`chain` 链接

`invisible wrapper.` 无形包装

`properly` 正确的, 得体的

`implicit 美 /ɪm'plɪsɪt/`  含蓄的, 不言明的, 隐式的

`precedence 美 /ˈpresɪdəns/` 优先权

## [List Rendering](https://vuejs.org/guide/essentials/list.html)

`iterate 美 /'ɪtəreɪt/`迭代 重复

`delimiter` 定界符

`enumeration美 /ɪˌnjuməˈreʃən/`

`implicit vs explicit` 

`in-place patch` 就地补丁

`performance gains.` 性能增益

`tightly coupled` 紧密耦合

`as the name suggests`

`Mutation Methods` 突变方法, 指改变原有数组的方法

`heuristics/hjuˈrɪstɪks/` 启发式方法

`overlap /ˈoʊvərˌlæp/` 重叠containing overlapping objects 包含重叠对象

`feasible /ˈfizəb/` 行得通的

`though` 然而

## [Event Handling](https://vuejs.org/guide/essentials/event-handling.html)

`dispatch` 触发调度

`Recall` 回想

`passive` 顺从的, 听之任之的, 消极的 (用在事件处理函数中, 表示不管触发什么函数, 都先做出默认行为)

`in case` 如果, 万一

`cadet美 /kə'dɛt/` 学员

`Symbolic` 符号的

`combination美 /ˌkɑmbɪ'neʃən/` 结合联合混合



## [Form Input Bindings](https://vuejs.org/guide/essentials/forms.html)

`cumbersome美 /ˈkʌmbəsəm/`   复杂而又低效的

`wire up` 给.. 布线, 连接

`typecast` 类型转换

## [Lifecycle Hooks](https://vuejs.org/guide/essentials/lifecycle.html)

`Along the way` 在此过程中

`associates` 关联

`lexically美 /'lɛksɪkl/` 词汇上的

`originate美 /ə'rɪdʒɪnet/` 开创, 来自, 发源

`diagram美 /'daɪəɡræm/` 示意图

## [Watchers](https://vuejs.org/guide/essentials/watchers.html)

`differentiated美 /ˌdɪfə'rɛnʃɪet/` 区分区别

`latter` 后者的

`implication`  可能引起的后果

`terser` 简明的, 简短的

`Callback Flush Timing` 回调刷新时间, flush 有刷新之意



## [Template Refs](https://vuejs.org/guide/essentials/template-refs.html)

`abstract` 抽象

`obtain` 获得

`initialize` 初始化

`account for` 对…负有责任

`populate` 居住于, 填入, 填充

`retrieve` 找回, 挽回, 检索





## [Component Basics](https://vuejs.org/guide/essentials/component-basics.html)

`On the fly` 动态的, 运行中

`specific` 特定的, 具体的

`on the fly` 在计算机运行中

`regardless of` 不管

`pros and cons ` 优缺点, 正面和反面

`subject` 服从

`Pascal美 /'pæskəl/ ` PascalCase 帕斯卡命名法

`case-insensitive` 大小写不敏感

`accessibility` 可访问性；可达性；可接近性

`accessibility feature` 辅助功能

`documents` 记录

`Caveat美 /'kævɪ'æt/` 警告, 注意事项

`retrieve美 /rɪ'triv/` 检索

`hyphen-delimited` 连字符分隔

`hyphen美 /'haɪfn/` 连字符

`delimit` 划定…的边界

`hoist` 提起

`Essentials` 概要, 基本的, 本质的





# Components In-Depth

## [Registration](https://vuejs.org/guide/components/registration.html)

`drawbacks` 缺点

`a.k.a` also known as

`maintainability [menˌteɪnə'bɪlətɪ]` 可维护性

`IDE` integrated development environment



## [Props](https://vuejs.org/guide/components/props.html#props-declaration)



`fallthrough attributes` 透传 attribute

`expected` 预期的

`further` 进一步

`annotation美 /ˌæno'teʃən/` 注解注释

`convention` 传统, 惯例

`practical` 实际的

`not the other way around.` 而不是反过来

`tempting` 诱人的

`unreasonably美 /ʌn'ri:znəbli/` 不合理的

`reason` 推理推断

`specify` 指定, 具体说明

`absent` 缺席的, 不在的

`mimic` 模仿

`casting` 类型转换
