# Airbnb 克隆第 1 部分

> 本练习的目的是展示新框架 Bootstrap 4 的便利性，我们将克隆 Airbnb（https://www.airbnb.com/）的特定版本。
>
> 请注意，你访问在线的 Airbnb 网站可能与本次浏览中使用的网站不同。

### 预备知识

### 学习

每个 Bootstrap 断点的全屏幕截图如下所示：

**Extra Large ≥1200px**

![airbnb-el](https://tva1.sinaimg.cn/large/006y8mN6ly1g79932mfoij30u01kdhdt.jpg)

**Large ≥ 992px**

![airbnb-l](https://tva1.sinaimg.cn/large/006y8mN6ly1g7993b22b6j30u027bhdt.jpg)

**Medium ≥ 768px**

![airbnb-m](https://tva1.sinaimg.cn/large/006y8mN6ly1g7993p8g2lj30kk22p4qp.jpg)

**Small ≥ 576px**

![airbnb-s](https://tva1.sinaimg.cn/large/006y8mN6ly1g7993u25zoj30g21xtx1v.jpg)

**Extra Small < 576px**

![airbnb-es](https://tva1.sinaimg.cn/large/006y8mN6ly1g799401vosj30a81ltqfg.jpg)

#### 期望

与之前的作业不同，我们不会尝试克隆细致到像素级别。相反，我们只想展示使用 Bootstrap 4 这样的框架构建基本基础架构的速度有多快，所以不要指望最终会100%的精确克隆。

你应该期待的是「看看建站的流程」, 例如工作环境的设置、我们首先处理页面的哪些部分。

**我希望你跟着我一起走一遍，你会学到很多实用的技巧。**

理解？那我们开始吧。

#### 创建文件夹结构

我们首先应该在清晰的文件夹结构中创建适当的文件。我们将所有的文件放在文件夹`airbnb_clone` 。在计算机的某个地方创建`airbnb_clone`文件夹。我喜欢将所有项目保存在同一个文件夹中，方便日后组织项目。但你也可以随着自己的喜好，把项目分别放在不同的地方。

打开代码编辑器（VS Code 或其他你喜欢的编辑器）并在代码编辑器中打开`airbnb_clone` 文件夹。你将看到左侧的文件夹树。创建两个名为`index.html` 和`style.css`的新文件。在 `airbnb_clone` 下创建另一个名为`images`的文件夹，我们将把占位图片放在此文件夹中。

#### **HTML 模板**

我们需要从 HTML 模板开始，因此将以下内容复制到 HTML 文件中。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />

    <!-- Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"
    />

    <link rel="stylesheet" type="text/css" href="./style.css" />

    <title>Airbnb</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script
      src="https://code.jquery.com/jquery-3.3.1.slim.min.js"
      integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
      integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
      integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

我们还包括可选的 JavaScript 文件，因为我们将使用 Bootstrap 的 Navbar 开关在较小的屏幕上显示和隐藏菜单。

确保我们的自定义 CSS 文件也正确引用，你可以通过添加一行 CSS 代码进行测试来实现。我们将为 h1 标签执行此操作。

```css
h1 {
  color: blue;
}
```

保存这两个文件并使用 Google Chrome 打开 HTML 文件。

#### **工作环境设置**

在我的办公室，可以使用外部宽屏显示器。我会将 Google Chrome 放在一边，将文本编辑放在另一边。当我正在处理某些事情时，我通常会打开 Chrome 开发者工具。这使我能够很快看到我的变化的影响。

如果你没有外接的大型显示器，可以学习使用快捷键在应用程序之间切换。Mac OS 上的默认设置是`Command` + `Tab` ，在 Windows 上，它是`Alt` + `Tab` 。

![airbnb-env](https://tva1.sinaimg.cn/large/006y8mN6ly1g7994b1fzjj31z40tc7dy.jpg)

#### **从顶部开始**

我通常的做法是自上而下。这意味着我们要处理的第一个组件是导航栏。

在超大屏幕上，导航栏被扩展。左侧有 logo，右侧有一些站点链接。请注意，AirBnb 的超大断点比 Bootstrap 略小。但是我们将坚持使用 Bootstrap 的默认断点进行此演练。

![airbnb-navbar-1](https://tva1.sinaimg.cn/large/006y8mN6ly1g7994he8wmj30zi02ewg2.jpg)

在大屏幕及以下，导航栏将折叠。隐藏所有站点链接，logo 成为切换隐藏导航菜单的按钮。

![airbnb-nav-2](https://tva1.sinaimg.cn/large/006y8mN6ly1g7994n5ep2j30o8029q45.jpg)

下面是隐藏导航菜单的屏幕截图。

![airbnb-nav-3](https://tva1.sinaimg.cn/large/006y8mN6ly1g7994s6fo0j30o80ks0td.jpg)

#### **超大屏幕的基本导航栏**

Bootstrap 提供了一个我们可以用于此的导航栏系统。前往[导航栏](https://getbootstrap.net/docs/components/navbar/)页面快速查看。

由于超大屏幕上的网站链接与隐藏菜单上的链接截然不同，我们将两者分开。让我们从超大屏幕的基本导航栏开始。

将以下内容添加到 body 元素的开头，请记住删除 h1 标签及其内容。

```html
<!-- nav for xl screens -->

<nav class="navbar navbar-expand-xl py-0">
  <div class="d-none d-xl-flex" id="xlNavbar">
    <a class="navbar-brand" href="#">Airbnb</a>
    <div class="navbar-nav">
      <a class="nav-item nav-link" href="#">Become a host</a>
      <a class="nav-item nav-link" href="#">Earn credit</a>
      <a class="nav-item nav-link" href="#">Help</a>
      <a class="nav-item nav-link" href="#">Sign up</a>
      <a class="nav-item nav-link" href="#">Log in</a>
    </div>
  </div>
</nav>
```

Bootstrap 导航栏开始于带`navbar`类的`<nav>`元素 。我们还需要将`navbar-expand-xl`类 添加到此元素，以指示导航栏在超大屏幕上处于扩展模式。这会影响导航栏内容的 CSS。

在`<nav>`元素内，我们可以添加另一个`div`来包含我们的内容。因为这将是超大屏幕的一部分。我们可以添加类`d-none d-xl-flex`，这样这部分只会显示在超大屏幕上。

Bootstrap 建议我们为品牌使用`navbar-brand` 类，它是可选的，我们现在使用它，以后可以再删除它。

对于站点链接，我们可以使用列表结构或 div 结构。我更喜欢使用 div 结构，因为它比较容易拼写输入。包含站点链接的`div` 应该有一个`navbar-nav` 类。

每个站点链接的链接都需要`nav-item`和`nav-links`类，以便通过 Bootstrap 添加一些简单的样式。

此时，你应该看到一个基本的导航栏，包含一堆链接。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2ob4a38j30zj01ldg5.jpg)

如果你查看 Airbnb 网站，你会注意到网站链接位于右侧。我们可以通过在`navbar-nav` 元素中添加类`ml-auto` ，这会将`margin-left: auto;`添加到元素上，并使该元素远离`<navbar-brand>`元素。

```html
<div class="navbar-nav ml-auto">...</div>
```

但似乎没有任何改变。使用 Chrome 开发者工具检查元素，你会注意到包含我们内容的`` 元素只占用其内容的宽度。这是因为`navbar-expand-xl` 类在`` 元素上设置了`justify-content: flex-start`。我们需要让``元素增长以占据``元素的整个宽度。

将类`flex-grow-1`添加到`<div>`元素。

```html
<div class="d-none d-xl-flex flex-grow-1">...</div>
```

现在你应该有这样的东西:

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2owsyf4j30zi01n3yu.jpg)

尝试缩小浏览器的宽度，导航栏应该会消失。

#### **小屏幕导航栏**

在大屏幕及以下屏幕上，导航栏仅显示 Airbnb 徽标。但你可以单击 logo 以显示和隐藏导航菜单。

Bootstrap 通过两个类`navbar-toggler` 和`navbar-collapse`支持这种类型的隐藏导航菜单。我们在元素上添加`navbar-toggler` ，则用户单击后以打开/关闭隐藏菜单。

`navbar-collapse` 被添加到菜单中以表它将被折叠。请注意，折叠的菜单元素上也需要`collapse`类。有关使用 Bootstrap 显示和隐藏折叠元素的更多信息，请参阅https://getbootstrap.net/docs/components/collapse。

```html
<nav class="navbar navbar-expand-xl py-0">
  <!-- nav for xl screens -->

  <div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
    <a class="navbar-brand" href="#">Airbnb</a>
    <div class="navbar-nav ml-auto">
      <a class="nav-item nav-link" href="#">Become a host</a>
      <a class="nav-item nav-link" href="#">Earn credit</a>
      <a class="nav-item nav-link" href="#">Help</a>
      <a class="nav-item nav-link" href="#">Sign up</a>
      <a class="nav-item nav-link" href="#">Log in</a>
    </div>
  </div>

  <!-- button and collapsed menu -->

  <a class="navbar-toggler navbar-brand" role="button" data-toggle="collapse" href="#navbarMenu" id="navbarMenuToggler">Airbnb</a>

  <div class="collapse navbar-collapse" id="navbarMenu">
    <a class="nav-item nav-link" href="#">Home</a>
    <hr/>
    <a class="nav-item nav-link" href="#">Invite friends</a>
    <a class="nav-item nav-link" href="#">Refer hosts</a>
    <a class="nav-item nav-link" href="#">Airbnb for work</a>
    <hr/>
    <a class="nav-item nav-link" href="#">Host a home<br/><small>Earn up to <b>$12,319 HKD a month</b></small></a>
    <a class="nav-item nav-link" href="#">Host an experience</a>
    <a class="nav-item nav-link" href="#">Sign up</a>
    <a class="nav-item nav-link" href="#">Log in</a>
    <hr/>
    <a class="nav-item nav-link" href="#">Help</a>
  </div>
</nav>
```

toggler link 元素需要两个属性才能起到交互作用。它们是`data-toggle="collapse"`和`href="#navbarMenu"`。JavaScript 使用这些属性来切换显示和隐藏折叠菜单。

请注意，`href` 的值与折叠的`<div>` 元素的 id 相同。这很重要，因为这可以让程序知道按钮应该切换到哪个菜单。

在`navbar-collapse` 元素内，我们添加了许多类似于 Airbnb 官方网站的链接。我们使用了一个名为`<hr>` 的新 HTML 元素，该元素是 horizontal-rule 的缩写，它有效地在整个屏幕的宽度上绘制一条细的水平线。当我们想要在内容之间创建某种分隔样式时，就用这个。

保存文件并刷新页面，你会看到类似这样的内容。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2p2fuhvj30zj02tq4i.jpg)

不要慌，我们可以很快地解决掉。我们看到这么多链接的原因是因为两个菜单都在 xl 屏幕上显示。Bootstrap 将根据 navbar-expand 类指示的断点扩展折叠菜单。由于我们的是 navbar-expand-xl ，折叠的菜单将在超大屏幕上显示。要解决这个问题，我们只需添加一个 CSS 样式就可以在超大断点上隐藏它。

执行此操作时，请删除`h1`的样式。

```css
@media (min-width: 1200px) {
  #navbarMenu {
    display: none !important;
  }
}
```

我们使用 important ，是因为 Bootstrap 在`navbar-collapse`元素上设置`display: flex !important;`，使其在在断点上的展开。我们需要覆盖这个样式。为此，我们需要在具有更高特异性的选择器上设置它，并使用`!important`语句。

现在将浏览器的宽度减小到 1200px 以下，你将看到切换按钮。单击它，折叠菜单将显示自己。

![airbnb-toggler](https://tva1.sinaimg.cn/large/006y8mN6ly1g79atycjg6j30kr0frabc.jpg)

#### 一段小小的 CSS 大有帮助

我们现在已经完成了基本的导航栏。让我们添加一些自定义 CSS，使导航栏看起来更像原始版本。

```css
#xlNavbar .navbar-brand,
#navbarMenuToggler,
#xlNavbar .nav-link {
  line-height: 80px;
}

#xlNavbar .nav-link {
  font-size: 14px;
}

#navbarMenuToggler,
#navbarMenu .nav-link {
  color: #333;
}

#navbarMenu .nav-link {
  padding: 12px 0;
  font-weight: 300;
}
```

我还添加了一些 Bootstrap 的便利类来编辑某些元素的内边距大小和样式。完整的 HTML 代码粘贴在下面。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />

    <!-- Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"
    />

    <link rel="stylesheet" type="text/css" href="./style.css" />

    <title>Airbnb</title>
  </head>
  <body>
    <nav class="navbar navbar-expand-xl py-0">
      <!-- nav for xl screens -->

      <div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
        <a class="navbar-brand py-0 pr-0 pl-2" href="#">Airbnb</a>
        <div class="navbar-nav ml-auto">
          <a class="nav-item nav-link py-0 px-3" href="#">Become a host</a>
          <a class="nav-item nav-link py-0 px-3" href="#">Earn credit</a>
          <a class="nav-item nav-link py-0 px-3" href="#">Help</a>
          <a class="nav-item nav-link py-0 px-3" href="#">Sign up</a>
          <a class="nav-item nav-link py-0 px-3" href="#">Log in</a>
        </div>
      </div>

      <!-- button and collapsed menu -->

      <a
        class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0"
        role="button"
        data-toggle="collapse"
        href="#navbarMenu"
        id="navbarMenuToggler"
        >Airbnb</a
      >

      <div
        class="collapse navbar-collapse pt-0 px-2 pb-4 font-weight-light"
        id="navbarMenu"
      >
        <a class="nav-item nav-link" href="#">Home</a>
        <hr />
        <a class="nav-item nav-link" href="#">Invite friends</a>
        <a class="nav-item nav-link" href="#">Refer hosts</a>
        <a class="nav-item nav-link" href="#">Airbnb for work</a>
        <hr />
        <a class="nav-item nav-link" href="#"
          >Host a home<br /><small
            >Earn up to <b>$12,319 HKD a month</b></small
          ></a
        >
        <a class="nav-item nav-link" href="#">Host an experience</a>
        <a class="nav-item nav-link" href="#">Sign up</a>
        <a class="nav-item nav-link" href="#">Log in</a>
        <hr />
        <a class="nav-item nav-link" href="#">Help</a>
      </div>
    </nav>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script
      src="https://code.jquery.com/jquery-3.3.1.slim.min.js"
      integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
      integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
      integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

你还可以在[HTML CSS: AirBnb Clone Part 1](https://codepen.io/HackerStart/pen/PoYXxMQ)上查看到目前为止的完整代码。

准备继续前进到第 2 部分，我们将克隆首页内容。

# Airbnb 克隆第 2 部分

在第 2 部分中，我们将克隆主角内容（hero content）。我们先来看看它在不同屏幕宽度上的样子。

在 extra large 及以上屏幕下，背景图片占窗口全部视觉高度，表单位于左侧。

![Original airbnb.com](https://tva1.sinaimg.cn/large/006y8mN6ly1g79bcrv6zkj30zj0lzh4l.jpg)

在 large 及以下的屏幕，表单成为块元素。它不再出现在背景图像面上。

![原创airbnb.com-2](https://tva1.sinaimg.cn/large/006y8mN6ly1g79bd2p926j30lb0h3431.jpg)

看看 「Book unique homes and experiences.」标题，它在两个布局的不同位置。对我来说，最简单的实现方法是在两个地方重复这个元素。一个用于`lg`及以下屏幕；另一个将用在表单内部，仅出现在`xl`及以上的屏幕上。

由于主角内容布局在`lg` 及以下更好做，我们先做这个。

### 背景和标题

我们将从标题和背景开始，在大屏幕和下面。

```html
<div id="hero">
  <div class="container-fluid">
    <h2>Book unique homes and experiences.</h2>
  </div>
</div>
```

对于背景图像，决定使用来自 [unsplash.com](http://unsplash.com/) 的免费图像。找到 https://unsplash.com/photos/zAjdgNXsMeg ，下载下来。

图像的原始尺寸太大，我们无法使用，你可以在本地或在调整图片大小的线上网站（如https://www.reduceimages.com/）上调整尺寸。我将尺寸缩小到原来的 30%，使文件大小更易于管理（大约 350 KB）。

将已调整大小的图像放在 images 文件夹中。现在我们可以将它设置为#hero 元素的背景。

```css
#hero {
  background-image: url(./images/luca-bravo-unsplash.jpg);
  background-size: cover;
  background-position: center bottom;
}
```

很酷，现在你应该有这样的东西。

![hero-background](https://tva1.sinaimg.cn/large/006y8mN6ly1g79bsqeuxtj30rr05njt0.jpg)在实际站点上，背景图片看上去比这个高很多，且标题应为白色。让我们为标题添加自定义顶部内边距，以使更高。

```css
#hero h2 {
  padding-top: 168px;
}
```

对于底部内边距和白色，我们可以使用 Bootstrap 类。

```html
<h2 class="pb-3 pb-sm-4 text-white">Book unique homes and experiences.</h2>
```

![hero-background-text](https://tva1.sinaimg.cn/large/006y8mN6ly1g79bwkldkbj30tb09wdn5.jpg)

哇，这看起来好多了。`text-white` 是用于设置颜色属性的 Bootstrap 类。可以在https://getbootstrap.net/docs/utilities/colors/#color上找到更多信息，甚至还提供用于设置基本背景色的类。

### 让背景从顶部开始

再次查看原始网站，会发现 hero 内容从页面顶部开始。导航栏与 hero 背景重叠。最简单的方法是将导航栏的位置值设置为`absolute` ，以便将其从内容的自然顺序中剔除，hero 内容会一直滑到顶部。

我们可以在导航栏上使用 Bootstrap 类`position-absolute` 。它是 Bootstrap 公共样式定位类之一。 https://getbootstrap.net/docs/utilities/position/.

```html
<nav class="navbar navbar-expand-xl py-0 position-absolute"></nav>
```

设置 `position-absolute` 后，导航栏的宽度将缩小到其内容大小。我们需要将宽度设置为 100%值，<mark>以便占用``元素的整个宽度。我们可以使用 Bootstrap 的`w-100`类。有关</mark>宽度和高度公共样式类的选择，请参阅https://getbootstrap.net/docs/utilities/sizing/。

由于导航栏现在与主角背景重叠，站点链接看不清楚，让导航栏文字变白。此外，为了使折叠菜单可读，我们必须给它一个白色背景。将以下类添加到特定元素。

```html
<!-- add text-white to the anchor links -->

<div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
  <a class="navbar-brand py-0 pr-0 pl-2 text-white" href="#">Airbnb</a>
  <div class="navbar-nav ml-auto">
    <a class="nav-item nav-link py-0 px-3 text-white" href="#">Become a host</a>
    <a class="nav-item nav-link py-0 px-3 text-white" href="#">Earn credit</a>
    <a class="nav-item nav-link py-0 px-3 text-white" href="#">Help</a>
    <a class="nav-item nav-link py-0 px-3 text-white" href="#">Sign up</a>
    <a class="nav-item nav-link py-0 px-3 text-white" href="#">Log in</a>
  </div>
</div>

<!-- add text-white to the navbar-toggler -->

<a
  class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0 text-white"
  role="button"
  data-toggle="collapse"
  href="#navbarMenu"
  id="navbarMenuToggler"
  >Airbnb</a
>

<!-- add bg-white to the navbarMenu -->

<div
  class="collapse navbar-collapse pt-0 px-2 pb-4 font-weight-light bg-white"
  id="navbarMenu"
></div>
```

![hero-to-top-1](https://tva1.sinaimg.cn/large/006y8mN6ly1g79cn62rvgj30zj07ewn0.jpg)

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2s5c5whj30g707un1v.jpg)

![hero-to-top-2](https://tva1.sinaimg.cn/large/006y8mN6ly1g79cnfdnctj30g70lgact.jpg)

### 修复导航菜单

navbarMenu 扩展后位于导航栏之下。但在原始网站中，白色背景覆盖整个导航栏，左侧和右侧没有间隙。

<mark>这意味着我们</mark>需要重新定位 navbarMenu，类似于我们对`` 元素所做的操作。首先我们将position-absolute类添加到 navbarMenu，然后我们添加一些位置属性。

```html
<div
  class="collapse navbar-collapse px-2 pb-4 font-weight-light bg-white position-absolute"
  id="navbarMenu"
></div>
```

```css
#navbarMenu {
  top: 0;
  left: 0;
  right: 0;
  padding-top: 88px;
}
```

刷新并单击 toggler，菜单将显示并覆盖 toggler。左右的 paddings 现在也关闭了。我们先修复 paddings，将`px-2` 更改为`px-4` 。

```html
<div
  class="collapse navbar-collapse px-4 pb-4 font-weight-light bg-white position-absolute"
  id="navbarMenu"
></div>
```

现在要让 toggler 显示在菜单的顶部，我们需要给它一个更高的 z-index 值。另外需要注意的是，当你通过单击 toggler 折叠菜单时，Bootstrap 将向 toggler 元素添加一个名为`collapsed` 的类。

单击 toggler 并展开菜单时，将删除`collapsed`类。这是 Bootstrap 的 JavaScript 代码所做的事情，用于表示目标元素是否已折叠。我们可以使用它在 toggler 元素上定义自定义 CSS，具体取决于目标的折叠状态。

就我们的情况，我们将设置 toggler 的 z-index 值并将其颜色更改为红色，以便我们可以在菜单展开时在白色背景上看到它。要了解有关 Bootstrap 折叠组件的更多信息，请参阅https://getbootstrap.net/docs/components/collapse/。

由于最初并未添加`collapsed`类，仅在我们展开和折叠菜单之后才添加此类，我们必须先将`collapsed`类添加到 HTML。注意：*这是我在开发者工具中，通过单击 toggler 观察元素时才发现 `collapsed`类是否添加到 toggler 元素的。*

首先，删除`navbar-toggler` 上的`text-white` 类，并添加类`position-relative` 和`collapsed` 。请记住，`z-index` 的运用是需要条件的，与其相关的属性就是 position 属性。当设置`position:static`或者没有设置 position 属性的时候，改变 z-index 不会产生任何效果。。

```html
<a class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0 position-relative collapsed" role="button" data-toggle="collapse" href="#navbarMenu" id="navbarMenuToggler">Airbnb</a>
```

然后我们将添加 CSS 来更改 z-index 和颜色。虽然我们在这里，让我们为颜色添加一个短暂的过渡，使它看起来更好。

```css
#navbarMenuToggler {
  color: rgb(255, 90, 95);
  transition: color 0.25s;
  z-index: 1;
}

#navbarMenuToggler.collapsed {
  color: #fff;
}
```

点击菜单并查看过渡，是不是还不错？

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2slb7rdj30n80jjwfl.jpg)

### 修复网格间距(gutter)

如果仔细查看原始网站，Airbnb 在容器上的左右内边距为 24px 。但是 Bootstrap 的默认容器内边距为 15px 。我们可以通过在 CSS 文件中设置自定义内边距值来更改此设置。

```css
.container-fluid,
.container {
  padding-left: 24px;
  padding-right: 24px;
}
```

一旦设定后后，hero 中的标题元素将与导航栏 toggler 对齐。

#### 建立表单

我们进入搜索表单。我们将首先创建较小的屏幕尺寸表单。

![airbnb-form-1](https://tva1.sinaimg.cn/large/006y8mN6ly1g79e4gduybj30v80asq3h.jpg)

Bootstrap 有一个非常不错的表单系统，https://getbootstrap.net/docs/components/forms/。请看 https://getbootstrap.net/docs/components/forms/#form-row 中的第二个示例。

结构非常简单。第一行是一个文本输入，第二行包含两个日期输入，第三行是一个选择，最后一行是一个按钮。

我们将`form-control-lg` 添加到每个输入元素，以略微增加其大小。

```html
<div id="searchForm">
  <div class="container-fluid">
    <form class="py-4">
      <div class="form-group">
        <label for="where"
          ><small><b>WHERE</b></small></label
        >
        <input
          type="text"
          class="form-control form-control-lg rounded"
          id="where"
          placeholder="Anywhere"
        />
      </div>
      <div class="form-row">
        <div class="form-group col-6">
          <label for="checkin"
            ><small><b>CHECK IN</b></small></label
          >
          <input
            type="date"
            class="form-control form-control-lg rounded-left"
            id="checkin"
            placeholder="mm/dd/yyyy"
          />
        </div>
        <div class="form-group col-6">
          <label for="checkout"
            ><small><b>CHECK OUT</b></small></label
          >
          <input
            type="date"
            class="form-control form-control-lg rounded-right"
            id="checkout"
            placeholder="mm/dd/yyyy"
          />
        </div>
      </div>
      <div class="form-group">
        <label for="inputAddress"
          ><small><b>GUESTS</b></small></label
        >
        <select class="form-control form-control-lg rounded" id="guests">
          <option>1 guest</option>
          <option>2 guest</option>
        </select>
      </div>
      <div class="d-flex flex-column">
        <button type="submit" class="btn btn-danger px-4 py-2 mt-2">
          Search
        </button>
      </div>
    </form>
  </div>
</div>
```

将其粘贴到 hero 内容之后，保存并刷新。你应该看到这样的东西。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2svzwbvj30v70hkk15.jpg)

鉴于它目前只是 Bootstrap 自带的样式，还不错的看。

我们对 input 元素的字体样式中添加一些 CSS，使其看起来更像原始字体。我们还需要删除默认的边框半径。

```css
#searchForm .form-control {
  font-size: 15px;
  font-weight: 300;
  border-radius: 0;
}
```

还有一件事，第二行中的两个日期输入目前被一个微小的间隙隔开。我们应该删除它。

Bootstrap 有一个`no-gutters` 类，可以添加到`row` 元素中以删除列之间的 gutters。https://getbootstrap.net/docs/layout/grid/#no-gutters。让我们将它添加到`form-row` 元素，并将`form-row` 更改为 `row` 。

同时，将`border-left-0` 添加到第二个日期 input 元素以删除其左边框。

```html
<div class="row no-gutters">
  <div class="form-group col-6">
    <label for="checkin"
      ><small><b>CHECK IN</b></small></label
    >
    <input
      type="date"
      class="form-control form-control-lg rounded-left"
      id="checkin"
      placeholder="mm/dd/yyyy"
    />
  </div>
  <div class="form-group col-6">
    <label for="checkout"
      ><small><b>CHECK OUT</b></small></label
    >
    <input
      type="date"
      class="form-control form-control-lg rounded-right border-left-0"
      id="checkout"
      placeholder="mm/dd/yyyy"
    />
  </div>
</div>
```

此外，按钮的垂直内边距应略大，颜色应为较浅的红色。

```css
#searchForm .btn-danger {
  padding-top: 12px;
  padding-bottom: 12px;
  background: #ff5a5f;
  border-color: #ff5a5f;
}
```

![aibnb-form-3](https://tva1.sinaimg.cn/large/006y8mN6ly1g79ejihcgij30b20jdgq9.jpg)

看起来不错！

#### **超大屏幕搜索表**

现在，我们需要添加一些 CSS，以便表单在超大屏幕上显示在 hero 容器内。

这是我们需要做的:

1. 在`xl` 断点处将 hero 元素的高度增加到`100vh` 。并给它一个最小的高度，这样即使屏幕高度很短，背景也会比表格高。
2. 隐藏`xl` 断点上的标题元素。
3. 将 searchForm 的位置设置为`absolute`并将其定位在导航栏下方并留出一定的空隙。确保其宽度设置为`100%`。
4. 将标题元素添加到表单中，仅显示在`xl`上。
5. 给 searchForm 中的`container-fluid`元素`xl` 断点处设置一个最大宽度值。
6. 给表单一个水平的 padding、一个白色的背景、圆角、最大宽度和一些框阴影。
7. 将搜索按钮向右对齐。

在 hero 元素的`xl`断点处将高度增加到`100vh` 。并给它一个最小的高度，这样即使屏幕高度很短，背景也会比表格高

```css
@media (min-width: 1200px) {
  #hero {
    height: 100vh;
    min-height: 650px;
  }
}
```

隐藏`xl`断点上的标题元素。

```html
<h2 class="mb-0 pb-3 pb-sm-4 text-white d-xl-none">
  Book unique homes and experiences.
</h2>
```

将 searchForm 的位置设置为 absolute，并将其定位在导航栏下方并留出一定的空隙，确保其宽度设置为 100%。

```css
@media (min-width: 1200px) {
  #searchForm {
    position: absolute;
    top: 120px;
    width: 100%;
  }
}
```

将标题元素添加到表单中，仅显示在 xl 上。

```html
<form class="py-4">
  <h2 class="d-none d-xl-block">Book unique homes and experiences.</h2>
</form>
```

给 searchForm 中的 container-fluid 元素一个`xl` 断点的最大宽度值。

```css
@media (min-width: 1200px) {
  #searchForm .container-fluid {
    max-width: 1080px;
  }
}
```

给表单更大的内边距、白色背景、圆角、最大宽度和一些框阴影。

```html
<form class="py-4 rounded bg-white"></form>
```

```css
@media (min-width: 1200px) {
  #searchForm form {
    padding: 32px;
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.12);
    max-width: 441px;
  }
}
```

将搜索按钮对齐到右侧。

```html
<div class="d-flex flex-column align-items-xl-end"></div>
```

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2t6yvgoj30zi0j9h4r.jpg)

看起来很棒！

#### 小细节

我们错过了一些细节。

1. 在右下角应该有一个小链接说"Over 300 unique homes in Oregon"。

   ![little-details-1](https://tva1.sinaimg.cn/large/006y8mN6ly1g79f9zqrnaj307o01ymxl.jpg)

2. `xl` 导航栏上的站点链接在悬停时应具有底部边框。

   ![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2teczjvj30f802raat.jpg)

我们将首先处理网站链接。如果你深入挖掘原始站点上的站点链接，你将看到它分为两层。每个链接周围都有一个`button`元素，左右两边有`8px` 内边距。然后有一个包含文本的`div`元素，它还有一个`8px`的水平内边距。底部边框仅应用于`div`元素。我们将复制这种结构。

```html
<div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
  <a class="navbar-brand py-0 pr-0 pl-2 text-white" href="#">Airbnb</a>
  <div class="navbar-nav ml-auto">
    <a class="nav-item nav-link py-0 px-2 text-white" href="#"
      ><div class="px-2">Become a host</div></a
    >
    <a class="nav-item nav-link py-0 px-2 text-white" href="#"
      ><div class="px-2">Earn credit</div></a
    >
    <a class="nav-item nav-link py-0 px-2 text-white" href="#"
      ><div class="px-2">Help</div></a
    >
    <a class="nav-item nav-link py-0 px-2 text-white" href="#"
      ><div class="px-2">Sign up</div></a
    >
    <a class="nav-item nav-link py-0 px-2 text-white" href="#"
      ><div class="px-2">Log in</div></a
    >
  </div>
</div>

```

```css
@media (min-width: 1200px) {
  #xlNavbar .nav-link div:hover {
    border-bottom: 2px solid #fff;
  }
}
```

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2tjw9dqj30zh02xdhw.jpg)

在右下角的小消息链接上。它只是一个位于 hero 容器右下角的锚链接。它应该只出现在`xl` 断点上，absolute 定位，且应该右对齐。

链接应相对于 hero 元素定位。

```html
<div id="hero" class="position-relative">
  <div class="container-fluid">
    <h2 class="mb-0 pb-3 pb-sm-4 text-white d-xl-none">
      Book unique homes and experiences.
    </h2>
  </div>
  <div class="d-none d-xl-block text-right position-absolute p-4" id="message">
    <a href="#" class="text-white"
      ><small class="font-weight-light"
        >Over 300<br />unique homes in Oregon</small
      ></a
    >
  </div>
</div>
```

```css
#message {
  bottom: 0;
  right: 0;
}
```

保存并刷新。右下角的消息链接看起来还不错，但导航栏消失了。由于我们将 hero 元素的位置值设置为`relative` ，因此在层叠顺序中它现在在导航栏的上方。

我们需要在导航栏中添加一个正`z-index` 值，以便它显示在 hero 元素的上方。<mark>将一个</mark>**id** 添加到``元素并给它一个`z-index: 1`; 。

```html
<nav
  class="navbar navbar-expand-xl py-0 position-absolute w-100"
  id="navbar"
></nav>
```

```css
#navbar {
  z-index: 1;
}
```



![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2trmq3jj30zi0k2dzw.jpg)

#### 小结

很棒，第 2 部分已经完成。你可以在下面看到完整的源代码。或者访问 [HTML CSS: AirBnb Clone Part 2](https://codepen.io/HackerStart/pen/MWgZRpg) 在线查看。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />

    <!-- Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"
    />

    <link rel="stylesheet" type="text/css" href="./style.css" />

    <title>Airbnb</title>
  </head>
  <body>
    <nav
      class="navbar navbar-expand-xl py-0 position-absolute w-100"
      id="navbar"
    >
      <!-- nav for xl screens -->

      <div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
        <a class="navbar-brand py-0 pr-0 pl-2 text-white" href="#">Airbnb</a>
        <div class="navbar-nav ml-auto">
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Become a host</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Earn credit</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Help</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Sign up</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Log in</div></a
          >
        </div>
      </div>

      <!-- button and collapsed menu -->

      <a
        class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0 position-relative collapsed"
        role="button"
        data-toggle="collapse"
        href="#navbarMenu"
        id="navbarMenuToggler"
        >Airbnb</a
      >

      <div
        class="collapse navbar-collapse px-4 pb-4 font-weight-light bg-white position-absolute"
        id="navbarMenu"
      >
        <a class="nav-item nav-link" href="#">Home</a>
        <hr />
        <a class="nav-item nav-link" href="#">Invite friends</a>
        <a class="nav-item nav-link" href="#">Refer hosts</a>
        <a class="nav-item nav-link" href="#">Airbnb for work</a>
        <hr />
        <a class="nav-item nav-link" href="#"
          >Host a home<br /><small
            >Earn up to <b>$12,319 HKD a month</b></small
          ></a
        >
        <a class="nav-item nav-link" href="#">Host an experience</a>
        <a class="nav-item nav-link" href="#">Sign up</a>
        <a class="nav-item nav-link" href="#">Log in</a>
        <hr />
        <a class="nav-item nav-link" href="#">Help</a>
      </div>
    </nav>

    <!-- Hero content -->
    <div id="hero" class="position-relative">
      <div class="container-fluid">
        <h2 class="mb-0 pb-3 pb-sm-4 text-white d-xl-none">
          Book unique homes and experiences.
        </h2>
      </div>
      <div
        class="d-none d-xl-block text-right position-absolute p-4"
        id="message"
      >
        <a href="#" class="text-white"
          ><small class="font-weight-light"
            >Over 300<br />unique homes in Oregon</small
          ></a
        >
      </div>
    </div>

    <!-- Search form -->
    <div id="searchForm">
      <div class="container-fluid">
        <form class="py-4 rounded bg-white">
          <h2 class="d-none d-xl-block">Book unique homes and experiences.</h2>
          <div class="form-group">
            <label for="where"
              ><small><b>WHERE</b></small></label
            >
            <input
              type="text"
              class="form-control form-control-lg rounded"
              id="where"
              placeholder="Anywhere"
            />
          </div>
          <div class="row no-gutters">
            <div class="form-group col-6">
              <label for="checkin"
                ><small><b>CHECK IN</b></small></label
              >
              <input
                type="date"
                class="form-control form-control-lg rounded-left"
                id="checkin"
                placeholder="mm/dd/yyyy"
              />
            </div>
            <div class="form-group col-6">
              <label for="checkout"
                ><small><b>CHECK OUT</b></small></label
              >
              <input
                type="date"
                class="form-control form-control-lg rounded-right border-left-0"
                id="checkout"
                placeholder="mm/dd/yyyy"
              />
            </div>
          </div>
          <div class="form-group">
            <label for="inputAddress"
              ><small><b>GUESTS</b></small></label
            >
            <select class="form-control form-control-lg rounded" id="guests">
              <option>1 guest</option>
              <option>2 guest</option>
            </select>
          </div>
          <div class="d-flex flex-column align-items-xl-end">
            <button type="submit" class="btn btn-danger px-4 mt-2">
              Search
            </button>
          </div>
        </form>
      </div>
    </div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script
      src="https://code.jquery.com/jquery-3.3.1.slim.min.js"
      integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
      integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
      integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy"
      crossorigin="anonymous"
    ></script>
  </body>
</html>

```

```css
/* ----------- Container ----------- */

.container-fluid,
.container {
  padding-left: 24px;
  padding-right: 24px;
}

/* ----------- Navigation ----------- */

@media (min-width: 1200px) {
  #navbarMenu {
    display: none !important;
  }

  #xlNavbar .nav-link div:hover {
    border-bottom: 2px solid #fff;
  }
}

#navbar {
  z-index: 1;
}

#xlNavbar .navbar-brand,
#navbarMenuToggler,
#xlNavbar .nav-link {
  line-height: 80px;
}

#xlNavbar .nav-link {
  font-size: 14px;
}

#navbarMenuToggler {
  color: rgb(255, 90, 95);
  transition: color 0.25s;
  z-index: 1;
}

#navbarMenuToggler.collapsed {
  color: #fff;
}

#navbarMenu .nav-link {
  color: #333;
}

#navbarMenu {
  top: 0;
  left: 0;
  right: 0;
  padding-top: 88px;
}

#navbarMenu .nav-link {
  padding: 12px 0;
}

/* ----------- Hero ----------- */

#hero {
  background-image: url(./images/luca-bravo-unsplash.jpg);
  background-size: cover;
  background-position: center bottom;
}

#hero h2 {
  padding-top: 168px;
}

#message {
  bottom: 0;
  right: 0;
}

@media (min-width: 1200px) {
  #hero {
    height: 100vh;
    min-height: 650px;
  }
}

/* ----------- Search form ----------- */

#searchForm .form-control {
  font-size: 15px;
  font-weight: 300;
  border-radius: 0;
}

#searchForm .btn-danger {
  padding-top: 12px;
  padding-bottom: 12px;
  background: #ff5a5f;
  border-color: #ff5a5f;
}

@media (min-width: 1200px) {
  #searchForm {
    position: absolute;
    top: 120px;
    width: 100%;
  }
  #searchForm .container-fluid {
    max-width: 1080px;
  }
  #searchForm form {
    padding: 32px;
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.12);
    max-width: 441px;
  }
}
```



# Airbnb 克隆第 3 部分

好的，继续前进。我们将要克隆第一个评论部分。首先，我们应该看看不同断点的布局。

`xl`屏幕，该行显示三个项目，每个项目占据空间的三分之一。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2xobmdmj30zh0fsqd2.jpg)

`md`屏幕，该行显示两个项目，第三个项目隐藏起来并通过单击平移右键显示。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo32olrdoj30tg0idk42.jpg)

`sm` 及以下屏幕，该行显示一个项目，另外两个项目可以滚动到视图中。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo32r29xkj30kc0ktjzx.jpg)

### 标题和副标题

我们将首先处理比较简单的部分，让我们创建一个新的`container-fluid` div 来包含这部分。然后为第一部分添加另一个 div。添加标题和副标题。

```
<div class="container-fluid">
  <!-- First Section -->
  <div class="headings">
    <h4>What guests are saying about homes in United States</h4>
    <p>
      &#11088; United States homes were rated <b>4.8 out of 5 stars</b> with
      <b>25,500,000+ reviews</b>
    </p>
  </div>
</div>
```

你注意到发光的星星表情符号（emoji character）吗？你可以直接将表情符号复制并粘贴到 HTML 文件中。或者去这个网站可以查找官方的 unicode 表情符号 https://emojipedia.org/。

这部分目前看起来像这样。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo32z55opj30zi04cgpl.jpg)

还记得我们之前在`xl` 断点上为`container-fluid` 类设置了最大宽度值吗？它仅为`#searchForm` 元素设置。现在，我们需要为所有`container-fluid` 设置此项。因此，删除先前 searchForm 的 CSS 规则，然后将其规则添加到所有容器中

```
/* ----------- Container ----------- */
@media (min-width: 1200px) {
  .container-fluid {
    max-width: 1080px;
  }
}

/* ----------- Search form ----------- */
@media (min-width: 1200px) {
  #searchForm {
    position: absolute;
    top: 120px;
    width: 100%;
  }
  /* remove below rule */
  /*#searchForm .container-fluid {
    max-width: 1080px;
  }*/
  #searchForm form {
    padding: 32px;
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.12);
    max-width: 441px;
  }
}
```

在第一部分`` 元素中添加一些顶部内边距，也增加`` 元素的底部外边距。

```
<!-- First Section -->
<div class="pt-3 pt-lg-4 pt-xl-5 headings">
  <h4 class="mb-3">What guests are saying about homes in United States</h4>
</div>
```

查看断点`md` 的布局。请注意，副标题的前半部分消失了。我们可以通过将该部分封装在`` 元素中并将其隐藏以实现较小的断点来实现。

```
<p>
  &#11088;
  <span class="d-none d-md-inline">United States homes were rated </span
  ><b>4.8 out of 5 stars</b> with <b>25,500,000+ reviews</b>
</p>
```

最后，对于断点`md`及以下，标题和副标题的字体大小显着减小。我们将添加一些带有媒体查询的 CSS 来实现这一目标。

```
/* ----------- Content ----------- */

@media (max-width: 767px) {
  .headings h4 {
    font-size: 18px;
  }
  .headings p {
    font-size: 13px;
  }
}
```

### 一行三项

我们需要在三个不同的断点处创建具有不同布局的三项结构。

- `xs` 到`md`时，每个项目占据整行。
- `md` 处，每个项目占用半个行。
- `xl`处，每个项目占据行的三分之一。

```
<div class="row pt-2 scrollableRow">
  <div class="col-12 col-md-6 col-xl-4">
    <div class="review">
      <div class="image mb-3">
        <img
          class="img-fluid w-100 rounded"
          src="https://via.placeholder.com/333x222"
        />
      </div>
      <div class="rating mb-2">
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
      </div>
      <p class="description">
        <small>
          We had a wonderful time staying in Murray & Kay's trailer. The
          location was beautiful and the trailer was adorable. We loved watching
          the sunset and the stars. We also had a great run in the morning on
          the bike path. We enjoyed going to the nearby country club for a
        </small>
      </p>
      <div class="user d-flex flex-row">
        <i class="far fa-user-circle mr-3"></i>
        <div>
          <p class="name mb-0"><b>Shelley</b></p>
          <p class="location mb-0"><small>United States</small></p>
        </div>
      </div>
    </div>
  </div>
  <div class="col-12 col-md-6 col-xl-4">
    <div class="review">
      <div class="image mb-3">
        <img
          class="img-fluid w-100 rounded"
          src="https://via.placeholder.com/333x222"
        />
      </div>
      <div class="rating mb-2">
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
      </div>
      <p class="description">
        <small>
          Judy was very welcoming upon our arrival. We didn't get to meet Tom.
          Judy gave us a little tour of the Silver Cloud and made some excellent
          restaurant recommendations. The entire property is absolutely
          charming! The Silver Cloud is a great, cozy space for two people.
        </small>
      </p>
      <div class="user d-flex flex-row">
        <i class="far fa-user-circle mr-3"></i>
        <div>
          <p class="name mb-0"><b>Alyssa</b></p>
          <p class="location mb-0"><small>United States</small></p>
        </div>
      </div>
    </div>
  </div>
  <div class="col-12 col-md-6 col-xl-4">
    <div class="review">
      <div class="image mb-3">
        <img
          class="img-fluid w-100 rounded"
          src="https://via.placeholder.com/333x222"
        />
      </div>
      <div class="rating mb-2">
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
        <i class="fas fa-star"></i>
      </div>
      <p class="description">
        <small>
          We had a fantastic stay at Doug and Chris' studio! It was a great
          location and they provided us with the best route to Disneyland. They
          were easy to communicate with and were helpful during our stay. We
          definitely want to stay again and it is a great alternative to staying
          at a hotel near Disneyland.
        </small>
      </p>
      <div class="user d-flex flex-row">
        <i class="far fa-user-circle mr-3"></i>
        <div>
          <p class="name mb-0"><b>Sarah</b></p>
          <p class="location mb-0"><small>United States</small></p>
        </div>
      </div>
    </div>
  </div>
</div>
```

我们用了名为[FontAwesome](https://fontawesome.com/)的图标资源，将其添加到`` 元素中 Bootstrap 链接的后面。

```
<!-- Fontawesome -->
<script
  src="https://kit.fontawesome.com/96ba351cc0.js"
  crossorigin="anonymous"
></script>
```

FontAwesome 是一个图标库，提供了不错的免费图标。在https://fontawesome.com/icons?d=gallery&m=free上搜索你需要的图标。

链接 CSS 资源后，就可以使用 FontAwesome 中的任何免费图标。要使用图标，只需将其相应的代码粘贴到 HTML 中即可。单击图标页面后即可找到此代码。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo3rs3uurj30zg0qqagw.jpg)

```
<!-- using the star icon -->
<i class="fas fa-star"></i>
```

我们使用的另一个资源是 [https://placeholder.com](https://placeholder.com/) 的占位图片。这项服务可生成所需维度的灰色占位图片。你可以通过更改 URL 末尾的值来获取维度。

- " https://via.placeholder.com/350x150 "适用于`350px` x `150px`
- " https://via.placeholder.com/333x222 "适用于`333px` x `222px`

由于没有额外的自定义 CSS，我们的内容目前看起来像这样。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo3rxb2jnj30zf0gwaid.jpg)

看起来还不错。

### 让项目溢出和滚动

最大的问题在于`md` 及以下，这些项目目前是垂直层叠的。但是原始站点会将项目溢出到右侧并让用户水平滚动。

这种效果实际上很容易做到。我们只需要向`scrollableRow` 类添加一个 CSS 属性，并将`flex-nowrap` 添加到`row` 元素中。

```
<div class="row flex-nowrap pt-2 scrollableRow"></div>
```

`flex-nowrap` 在`row`元素上设置`flex-wrap: nowrap;` 。这意味着不适合一行的 flex 项目不会被推送到新行。相反，它们将向右延伸。

```
.scrollableRow {
  overflow-x: scroll;
}
```

`overflow` 是一个 CSS 属性，用于确定我们如何处理溢出项。你可以将其设置为`visible`, `hidden`, `scroll`, 或 `auto`。

- `visible` ：溢出项目不会被截断，它会在父元素之外呈现。
- `hidden`：溢出项被切断，没有溢出项呈现在父项之外。
- `scroll`：溢出项目被切断，但用户可以使用滚动将项目滚动到视图中。不管是否有溢出项目，浏览器会显示滚动条。
- `auto` ：溢出项目被切断，用户可以使用滚动将项目滚动到视图中。根据浏览器的不同，当没有溢出项时，滚动条可能会有也可能不会有。

你可以使用`overflow` 来设置`x`和`y` 方向的值。或者你可以使用`overflow-x` 或 `overflow-y` 设置一个方向。`x` 表示水平，`y` 表示垂直。

**注意：**我们没有实现轮播效果，因为它涉及 JavaScript。

### 自定义网格间距尺寸

我们遇到的另一个问题是，每个项目之间的网格间距太大，这意味着用户看不到`xl` 断点下方右侧的更多内容。

我们需要做的是在行和列中添加一些自定义的左右内边距。

首先，我们使用`row`元素上的`no-gutters` 类删除所有默认的网格间距设置。

```
<div class="row flex-nowrap pt-2 scrollableRow no-gutters"></div>
```

然后，我们将一些自定义内边距和外边距值添加到`scrollableRow` 和列。

```
.scrollableRow {
  overflow-x: scroll;
  margin-left: -24px;
  margin-right: -24px;
  padding-left: 18px;
  padding-right: 18px;
}

.scrollableRow > [class*="col-"] {
  padding-left: 6px;
  padding-right: 6px;
}
```

**注意** `[class*=col-]`是 CSS 属性选择器。特别是，这使我们可以选择一个类元素，该元素在 class 属性中以`col-` 开头。`.scrollableRow > [class*=col-]` 本质上会选择`.scrollableRow` 类中所有带有`col-`直接子类中的元素。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo3s26vdrj30b20du0ur.jpg)

好多了。但是，如果滚动到最后一个项目，你将看到右侧内边距比第一个项目的左侧内边距小得多。这是浏览器的错误，其中带`overflow: scroll`元素在溢出扩展后，其内边距被忽略。在这种情况下，当我们滚动到第三项时，`scrollableRow` 元素的右内边距将被忽略。但是左侧内边距出现在第一项上。

W3C 仍在决定如何解决此问题，你可以在 https://github.com/w3c/csswg-drafts/issues/129 上看到正在讨论中。

可以采取一些措施来改善这一状况。通过在最后一个项目后面的断点`lg` 及以下添加恰好距离的内边距元素。

```
<!-- Filler -->
<div class="d-xl-none filler"></div>
.scrollableRow .filler {
  min-width: 18px;
}
```

这确实有点麻烦。除非绝对必要，否则我建议坚持使用默认的 Bootstrap gutter。

### 将说明限制为最多三行

原始站点中的描述最多三行。适用于所有浏览器的简单方法是设置最大高度值，该值恰好是三行文本的高度。然后将`overflow`值设置为`hidden` 。

为了控制每条线的高度，我们将使用`line-height` 。基于此，我们可以将段落元素的`max-height` 值设置为稍大于`line-height` 值的三倍。

```
.review .description {
  line-height: 18px;
  max-height: 60px;
  overflow: hidden;
}
```

执行此操作的更高级的方法是在句子的末尾添加省略号“ ...”，这是使用一种称为`line-clamp`的方法。

```
.review .description {
  line-height: 18px;
  max-height: 60px;
  overflow: hidden;
  /* using line clamp */
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  text-overflow: ellipses;
}
```

`line-clamp` 是一种属性，允许我们限制特定元素可以显示的最大行数。它需要与`display: -webkite-box;` 和`-webkit-box-orient: vertical;` 一起使用 。`text-overflow: ellipses;`是一个 CSS 规则，在最后添加"..."用。

由于`line-clamp`仍处于草稿模式，并且并非所有浏览器都支持，因此我们将`max-height`方法作为退而求其次的方法。另请注意，在将来的 CSS 版本中，可能会更改这些属性名称。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo3s7abvkj30uh02xtbo.jpg)

### CSS 修饰

我们只需要一点点修饰就可以让物品看起来很棒。首先，让我们将星形图标设置为浅灰色。

```
<div class="rating mb-2 text-black-50">
  <i class="fas fa-star"></i>
  <i class="fas fa-star"></i>
  <i class="fas fa-star"></i>
  <i class="fas fa-star"></i>
  <i class="fas fa-star"></i>
</div>
```

接下来，在描述中添加一点右边内边距，使其不会填充项目的整个宽度。

```
<p class="description pr-4"></p>
```

将用户图标的字体大小增加到`48px` 。

```
.review .user i {
  font-size: 48px;
}
```

最后，减少`font-weight`的`name`到`500` ，和减少`location`的`line-height`的值为 18 像素。

```
.review .user .name b {
  font-weight: 500;
}

.review .user .location {
  line-height: 18px;
}
```

#### **使用免费照片作为项目图像**

我们使用[unsplash.com](http://unsplash.com/)中更好的东西代替占位图像。我找到了以下三个

- https://unsplash.com/photos/TcgASSD5G04
- https://unsplash.com/photos/3wylDrjxH-E
- https://unsplash.com/photos/XbwHrt87mQ0

下载它们并使用https://www.reduceimages.com/调整大小以将宽度减小到小于`800px` 。

之后，将所有调整大小后的图像放入项目的“ images”文件夹中。然后，你可以更改每个图像元素的 src 链接。

```
<img class="img-fluid w-100 rounded" src="./images/blake-wisz-unsplash.jpg" />

<img
  class="img-fluid w-100 rounded"
  src="./images/patrick-perkins-unsplash.jpg"
/>

<img class="img-fluid w-100 rounded" src="./images/brian-babb-unsplash.jpg" />
```

保存并刷新，你将看到此信息。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo3sdzho6j30uj0cegwz.jpg)

第一图像和第三图像具有相同的纵横比（图像的宽度与高度的比率），因此它们看起来具有相同的高度。而第二张图片略高。

解决此问题的简单方法是手动将实际图像文件裁剪为正确的宽高比，即（3：2）。但是我们不会那样做。我们喜欢用困难的方式做事，所以你可以学习更多。

我们将使用一种称为“宽高比盒子”（[aspect ratio box](https://css-tricks.com/aspect-ratio-boxes/)）的东西来创建尺寸正确的元素，然后将漂亮的图像作为背景应用于该 box。

#### 宽高比盒子

要了解长宽比框是如何工作的，我们首先需要知道元素垂直内边距上的百分比值将基于元素的宽度值。因此，如果元素的宽度值为`100px` ，则`padding-top`值`100%`将为`100px` 。如果此元素没有边框或内容，则唯一的高度值将来自顶部内边距。这意味着该元素实质上是一个正方形盒子。因为我们有一个`100px` x `100px`的元素。

现在，如果我们将`padding-top` 设置为`66.666666666%`，则意味着宽高比将接近 3：2（2/3 = 0.66666666 ..）。盒子尺寸是`100px` x `66.666666px` 。这就是我们创建宽高比盒子的方法。

从项目中删除所有图像元素，并将 url 作为内联 CSS `background-image` 属性添加到`` 元素。

```
<div
  class="aspectRatioBox mb-3 rounded"
  style="background-image: url('./images/blake-wisz-unsplash.jpg')"
></div>

<div
  class="aspectRatioBox mb-3 rounded"
  style="background-image: url('./images/patrick-perkins-unsplash.jpg')"
></div>

<div
  class="aspectRatioBox mb-3 rounded"
  style="background-image: url('./images/brian-babb-unsplash.jpg')"
></div>
```

CSS 提供了`calc()`函数，该函数可用于计算数学公式的值。我们可以使用它来准确定义正确的高宽比，而不用输入接近的估计值。有关`calc()`的更多信息，请查看此 MDN 文档https://developer.mozilla.org/en-US/docs/Web/CSS/calc。

```
.aspectRatioBox {
  padding-top: calc(2 / 3 * 100%); /* aspect ratio 3:2 */
  background-size: cover;
  background-position: center;
}
```

#### **画龙点睛**

添加一个

------

元素，我们差不多就完成了第 3 部分。



```
<hr class="mt-4 mt-xl-5" />
```

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo3sjqknej30zh0gjk40.jpg)

你可以在下面看到完整的源代码。访问[HTML CSS: AirBnb Clone Part 3](https://codepen.io/HackerStart/pen/NWKeZJz)查看线上演示。

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />

    <!-- Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"
    />

    <!-- Fontawesome -->
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
      crossorigin="anonymous"
    />

    <link rel="stylesheet" type="text/css" href="./style.css" />

    <title>Airbnb</title>
  </head>
  <body>
    <nav
      class="navbar navbar-expand-xl py-0 position-absolute w-100"
      id="navbar"
    >
      <!-- nav for xl screens -->

      <div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
        <a class="navbar-brand py-0 pr-0 pl-2 text-white" href="#">Airbnb</a>
        <div class="navbar-nav ml-auto">
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Become a host</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Earn credit</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Help</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Sign up</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Log in</div></a
          >
        </div>
      </div>

      <!-- button and collapsed menu -->

      <a
        class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0 position-relative collapsed"
        role="button"
        data-toggle="collapse"
        href="#navbarMenu"
        id="navbarMenuToggler"
        >Airbnb</a
      >

      <div
        class="collapse navbar-collapse px-4 pb-4 font-weight-light bg-white position-absolute"
        id="navbarMenu"
      >
        <a class="nav-item nav-link" href="#">Home</a>
        <hr />
        <a class="nav-item nav-link" href="#">Invite friends</a>
        <a class="nav-item nav-link" href="#">Refer hosts</a>
        <a class="nav-item nav-link" href="#">Airbnb for work</a>
        <hr />
        <a class="nav-item nav-link" href="#"
          >Host a home<br /><small
            >Earn up to <b>$12,319 HKD a month</b></small
          ></a
        >
        <a class="nav-item nav-link" href="#">Host an experience</a>
        <a class="nav-item nav-link" href="#">Sign up</a>
        <a class="nav-item nav-link" href="#">Log in</a>
        <hr />
        <a class="nav-item nav-link" href="#">Help</a>
      </div>
    </nav>

    <!-- Hero content -->
    <div id="hero" class="position-relative">
      <div class="container-fluid">
        <h2 class="mb-0 pb-3 pb-sm-4 text-white d-xl-none">
          Book unique homes and experiences.
        </h2>
      </div>
      <div
        class="d-none d-xl-block text-right position-absolute p-4"
        id="message"
      >
        <a href="#" class="text-white"
          ><small class="font-weight-light"
            >Over 300<br />unique homes in Oregon</small
          ></a
        >
      </div>
    </div>

    <!-- Search form -->
    <div id="searchForm">
      <div class="container-fluid">
        <form class="py-4 rounded bg-white">
          <h2 class="d-none d-xl-block">Book unique homes and experiences.</h2>
          <div class="form-group">
            <label for="where"
              ><small><b>WHERE</b></small></label
            >
            <input
              type="text"
              class="form-control form-control-lg rounded"
              id="where"
              placeholder="Anywhere"
            />
          </div>
          <div class="row no-gutters">
            <div class="form-group col-6">
              <label for="checkin"
                ><small><b>CHECK IN</b></small></label
              >
              <input
                type="date"
                class="form-control form-control-lg rounded-left rounded-left"
                id="checkin"
                placeholder="mm/dd/yyyy"
              />
            </div>
            <div class="form-group col-6">
              <label for="checkout"
                ><small><b>CHECK OUT</b></small></label
              >
              <input
                type="date"
                class="form-control form-control-lg rounded-right border-left-0"
                id="checkout"
                placeholder="mm/dd/yyyy"
              />
            </div>
          </div>
          <div class="form-group">
            <label for="inputAddress"
              ><small><b>GUESTS</b></small></label
            >
            <select class="form-control form-control-lg rounded" id="guests">
              <option>1 guest</option>
              <option>2 guest</option>
            </select>
          </div>
          <div class="d-flex flex-column align-items-xl-end">
            <button type="submit" class="btn btn-danger px-4 mt-2">
              Search
            </button>
          </div>
        </form>
      </div>
    </div>

    <div class="container-fluid">
      <!-- First Section -->
      <div class="pt-3 pt-lg-4 pt-xl-5 headings">
        <h4 class="mb-3">
          What guests are saying about homes in United States
        </h4>
        <p>
          &#11088;
          <span class="d-none d-md-inline">United States homes were rated </span
          ><b>4.8 out of 5 stars</b> with <b>25,500,000+ reviews</b>
        </p>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div
              class="aspectRatioBox mb-3 rounded"
              style="background-image: url('./images/blake-wisz-634300-unsplash.jpg')"
            ></div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4">
              <small>
                We had a wonderful time staying in Murray & Kay's trailer. The
                location was beautiful and the trailer was adorable. We loved
                watching the sunset and the stars. We also had a great run in
                the morning on the bike path. We enjoyed going to the nearby
                country club for a wine tasting and to Malibu Cafe for dinner.
                We would definitely come back.
              </small>
            </p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Shelley</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div
              class="aspectRatioBox mb-3 rounded"
              style="background-image: url('./images/patrick-perkins-340019-unsplash.jpg')"
            ></div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4">
              <small>
                Judy was very welcoming upon our arrival. We didn't get to meet
                Tom. Judy gave us a little tour of the Silver Cloud and made
                some excellent restaurant recommendations. The entire property
                is absolutely charming! The Silver Cloud is a great, cozy space
                for two people.
              </small>
            </p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Alyssa</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div
              class="aspectRatioBox mb-3 rounded"
              style="background-image: url('./images/brian-babb-256298-unsplash.jpg')"
            ></div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4">
              <small>
                We had a fantastic stay at Doug and Chris' studio! It was a
                great location and they provided us with the best route to
                Disneyland. They were easy to communicate with and were helpful
                during our stay. We definitely want to stay again and it is a
                great alternative to staying at a hotel near Disneyland.
              </small>
            </p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Sarah</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler"></div>
      </div>

      <hr class="mt-4 mt-xl-5" />
    </div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script
      src="https://code.jquery.com/jquery-3.3.1.slim.min.js"
      integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
      integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
      integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
/* ----------- Container ----------- */
@media (min-width: 1200px) {
  .container-fluid {
    max-width: 1080px;
  }
}

.container-fluid,
.container {
  padding-left: 24px;
  padding-right: 24px;
}

/* ----------- Navigation ----------- */

@media (min-width: 1200px) {
  #navbarMenu {
    display: none !important;
  }

  #xlNavbar .nav-link div:hover {
    border-bottom: 2px solid #fff;
  }
}

#navbar {
  z-index: 1;
}

#xlNavbar .navbar-brand,
#navbarMenuToggler,
#xlNavbar .nav-link {
  line-height: 80px;
}

#xlNavbar .nav-link {
  font-size: 14px;
}

#navbarMenuToggler {
  color: rgb(255, 90, 95);
  transition: color 0.25s;
  z-index: 1;
}

#navbarMenuToggler.collapsed {
  color: #fff;
}

#navbarMenu .nav-link {
  color: #333;
}

#navbarMenu {
  top: 0;
  left: 0;
  right: 0;
  padding-top: 88px;
}

#navbarMenu .nav-link {
  padding: 12px 0;
}

/* ----------- Hero ----------- */

#hero {
  background-image: url(./images/luca-bravo-121931-unsplash.jpg);
  background-size: cover;
  background-position: center bottom;
}

#hero h2 {
  padding-top: 168px;
}

#message {
  bottom: 0;
  right: 0;
}

@media (min-width: 1200px) {
  #hero {
    height: 100vh;
    min-height: 650px;
  }
}

/* ----------- Search form ----------- */

#searchForm .form-control {
  font-size: 15px;
  font-weight: 300;
  border-radius: 0;
}

#searchForm .btn-danger {
  padding-top: 12px;
  padding-bottom: 12px;
  background: #ff5a5f;
  border-color: #ff5a5f;
}

@media (min-width: 1200px) {
  #searchForm {
    position: absolute;
    top: 120px;
    width: 100%;
  }
  #searchForm form {
    padding: 32px;
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.12);
    max-width: 441px;
  }
}

/* ----------- Content ----------- */

@media (max-width: 767px) {
  .headings h4 {
    font-size: 18px;
  }
  .headings p {
    font-size: 13px;
  }
}

.scrollableRow {
  overflow-x: scroll;
  margin-left: -24px;
  margin-right: -24px;
  padding-left: 18px;
  padding-right: 18px;
}

.scrollableRow > [class*="col-"] {
  padding-left: 6px;
  padding-right: 6px;
}

.scrollableRow .filler {
  min-width: 18px;
}

.aspectRatioBox {
  padding-top: calc(2 / 3 * 100%);
  background-size: cover;
  background-position: center;
}

.review .description {
  line-height: 18px;
  max-height: 60px;
  overflow: hidden;
  /* using line clamp */
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  text-overflow: ellipses;
}

.review .user i {
  font-size: 48px;
}

.review .user .name b {
  font-weight: 500;
}

.review .user .location {
  line-height: 18px;
}
```

# Airbnb 克隆第 4 部分

登录页面展示产品或业务的价值主张是很常见的。即使对于一个众所周知的 Airbnb 企业来说，向客户宣传他们所做的事情也很重要。让我们来看看不同断点的原始布局。

在 `md` 及以上，每个占据连续三分之一。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2y0jtvdj30zh06jmyd.jpg)

在 `xs` 和 `md` 之间，每个占据一行的大约 70%, 该行设置为溢出滚动。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2y4ghf5j30hk05kmxt.jpg)

这与上部分的结构几乎相同，我们可以把结构复制过来 。

在`` 元素后添加以下内容。

```
<!-- Value Props -->

<div class="row flex-nowrap pt-2 pt-md-3 scrollableRow no-gutters">
  <div class="col-8 col-md-4">
    <div class="valueProp">
      <div class="icon mb-3">
        <i class="far fa-heart"></i>
      </div>
      <p class="title mb-1">24/7 customer support</p>
      <p class="description pr-4">
        <small>
          Day or night, we’re here for you. Talk to our support team from
          anywhere in the world, any hour of day.
        </small>
      </p>
    </div>
  </div>
  <div class="col-8 col-md-4">
    <div class="valueProp">
      <div class="icon mb-3">
        <i class="fas fa-home"></i>
      </div>
      <p class="title mb-1">Global hospitality standards</p>
      <p class="description pr-4">
        <small>
          Guests review their hosts after each stay. All hosts must maintain a
          minimum rating and our hospitality standards to be on Airbnb.
        </small>
      </p>
    </div>
  </div>
  <div class="col-8 col-md-4">
    <div class="valueProp">
      <div class="icon mb-3">
        <i class="far fa-user"></i>
      </div>
      <p class="title mb-1">5-star hosts</p>
      <p class="description pr-4">
        <small>
          From fresh-pressed sheets to tips on where to get the best brunch, our
          hosts are full of local hospitality.
        </small>
      </p>
    </div>
  </div>

  <!-- Filler -->
  <div class="d-xl-none filler"></div>
</div>

<hr class="mt-2 mt-md-3 mb-0" />
```

我们重用上部分设置的`scrollableRow` 类。没有写出额外的自定义 CSS，我们的价值道具就像这样。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2yaet8qj30xm067ju6.jpg)

### 自定义 CSS

只需要一点自定义 CSS。

```
/* ------------ Value Props ------------ */

.valueProp .icon {
  font-size: 40px;
  line-height: 40px;
  color: rgb(65, 198, 188);
}

.valueProp .title {
  font-weight: 500;
}
```

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2yel053j30v006gdim.jpg)

完成！

### Homes in United States

好的，继续前进。

这一部分的布局几乎与上部分相同，后者显示了不同住宅的评论列表。主要区别在于`xl` ，显示了四个项目，每个项目占据了行的四分之一。

在`xl`处，该行显示四个项目，每个项目占据空间的四分之一。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2yjscn9j30xm0bgn5o.jpg)

在`md`处，该行显示两个项目，第三个项目隐藏起来并通过单击平移右键显示。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2yoodsqj30o10e6gsw.jpg)

在`sm` 及以下，该行显示一个项目，另外两个项目可以滚动到视图中。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2ytsjayj30jm0h3q9e.jpg)

由于结构几乎相同，我只是复制了评论的布局。主要变化是`col-xl-4` 变为`col-xl-3` 。

宽高比盒子保持不变。描述和评级有一些自定义 CSS，顺序不同，但没什么特别的。

我使用了来自[unsplash.com](http://unsplash.com/)四张照片

- https://unsplash.com/photos/bbw55-xjeJo
- https://unsplash.com/photos/kdwahpWYfQo
- https://unsplash.com/photos/ojEK3p9cDg4
- https://unsplash.com/photos/K1iqi58F4Qw

这是代码，在`` 元素后添加以下内容。

```
<!-- Home Listings -->
<div class="pt-4 pt-lg-5 headings">
  <h4 class="mb-3">Homes in United States</h4>
</div>

<div class="row flex-nowrap pt-2 scrollableRow no-gutters">
  <div class="col-12 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/tyler-nix-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>camper/rv · malibu</small>
      </p>
      <p class="title mb-0">Malibu Dream Airstream</p>
      <p class="pricing mb-0">
        <small>$600 per night · Free cancellation </small>
      </p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span
          ><span class="numberOfRatings">351</span> ·
          <span class="tag">Superhost</span></span
        >
      </div>
    </div>
  </div>
  <div class="col-12 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/neonbrand-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>entire house · joshua tree</small>
      </p>
      <p class="title mb-0">The Joshua Tree House</p>
      <p class="pricing mb-0">
        <small>$285 per night · Free cancellation </small>
      </p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span
          ><span class="numberOfRatings">348</span> ·
          <span class="tag">Superhost</span></span
        >
      </div>
    </div>
  </div>
  <div class="col-12 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/jeremy-bishop-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>dome house · aptos</small>
      </p>
      <p class="title mb-0">Mushroom Dome Cabin: #1 on airbnb in the world</p>
      <p class="pricing mb-0">
        <small>$130 per night · Free cancellation </small>
      </p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span
          ><span class="numberOfRatings">1205</span> ·
          <span class="tag">Superhost</span></span
        >
      </div>
    </div>
  </div>
  <div class="col-12 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/travis-grossen-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>entire house · cazadero</small>
      </p>
      <p class="title mb-0">Cozy A-Frame Cabin in the Redwoods</p>
      <p class="pricing mb-0">
        <small>$175 per night · Free cancellation </small>
      </p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span
          ><span class="numberOfRatings">382</span> ·
          <span class="tag">Superhost</span></span
        >
      </div>
    </div>
  </div>

  <!-- Filler -->
  <div class="d-xl-none filler"></div>
</div>
/* ------------ Listings ------------ */

.listing .location {
  line-height: 18px;
}

.listing .location small {
  font-weight: 700;
  font-size: 12px;
}

.listing .title {
  font-weight: 600;
  margin-top: 1px;
  color: #484848;
}

.listing .pricing {
  line-height: 18px;
  margin-top: 2px;
}

.listing .pricing small {
  font-weight: 300;
}

.listing .info {
  font-size: 12px;
  font-weight: 500;
  margin-top: 3px;
}

.listing .info .rating {
  font-size: 8.5px;
  letter-spacing: -1px;
  margin-right: 3px;
}
```

### 查看更多链接

在列表的底部，有一个指向列表页面的链接。它只在`md` 及以上显示。

```
<div class="mt-3 d-none d-md-block">
  <a href="#" class="listingsLink">Show all (22,000+) &gt;</a>
</div>

.listingsLink { color: #008489; font-size: 17px; }
```

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2z2y6gij30zh0bq137.jpg)

### 最高评分体验

体验部分与列表部分几乎相同。但是，在`sm` 及以下，每个项目占据行宽度的约 70%。

在`xl`处，该行显示四个项目，每个项目占据宽度的四分之一。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2z4obh0j30zg0aqah7.jpg)

在`md`处，该行显示两个项目，第三个项目隐藏起来并通过单击平移右键显示。我们不会实现这种轮播效果。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2zaqqjjj30v40fcwqo.jpg)

在`sm` 及以下，每个项目占据宽度的约 70%。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo2zhvd4wj30jn0ctwm4.jpg)

这是 HTML 代码和使用的图像。

- https://unsplash.com/photos/gPRvTP0sZ2M
- https://unsplash.com/photos/9j9O0J3cfKo
- https://unsplash.com/photos/m2iqRdVGprU
- https://unsplash.com/photos/22qZVcUgD_U

请记住在使用之前减小图像的大小，可以使用https://www.reduceimages.com/或在你的计算机上使用本地工具。

```
<div class="pt-4 pt-lg-5 headings">
  <h4 class="mb-3">Top-rated experiences</h4>
</div>

<div class="row flex-nowrap pt-2 scrollableRow no-gutters">
  <div class="col-8 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/malcolm-lightbody-698733-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>workshop · seattle</small>
      </p>
      <p class="title mb-0">Forge a knife from a horseshoe</p>
      <p class="pricing mb-0"><small>$95 per person</small></p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span><span class="numberOfRatings">210</span></span>
      </div>
    </div>
  </div>
  <div class="col-8 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/greta-scholderle-moller-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>animal encounter · seattle</small>
      </p>
      <p class="title mb-0">Horse Riding</p>
      <p class="pricing mb-0"><small>$175 per person</small></p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span><span class="numberOfRatings">1147</span></span>
      </div>
    </div>
  </div>
  <div class="col-8 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/phad-pichetbovornkul-unsplash.jpg')"
      ></div>
      <p class="mb-0 text-uppercase location">
        <small>day trip · san diego</small>
      </p>
      <p class="title mb-0">Day Trip Across the Border</p>
      <p class="pricing mb-0"><small>$75 per person</small></p>
      <div class="info d-flex align-items-center">
        <span class="rating text-black-50">
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
          <i class="fas fa-star"></i>
        </span>
        <span><span class="numberOfRatings">93</span></span>
      </div>
    </div>
  </div>
  <div class="col-8 col-md-6 col-xl-3">
    <div class="listing">
      <div
        class="aspectRatioBox mb-2 rounded"
        style="background-image: url('./images/matt-zhou-unsplash.jpg')"
      ></div>
    </div>
  </div>

  <!-- Filler -->
  <div class="d-xl-none filler"></div>
</div>
```

CSS 在主页列表和体验列表之间共享。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo309qy5lj30zg09aqb4.jpg)

### 彩色叠加与居中文本

最后一个实际上不是列表，而是显示所有提供体验的链接。这是两个人在桨板上的图片，顶部带有绿色覆盖图，带有居中文字。

你可以使用图片编辑器（如 photoshop 或 Illustrator）创建图片。但我们也可以用 CSS 来做。这是如何做出来的呢？

通常使用绝对定位创建叠加。我们将使用宽高比盒子作为相对基数，并添加一个子元素，该子元素将占用宽高比盒子的整个宽度和高度。

要在中心对齐文本，我们可以使用 flex 属性。

```
<div
  class="aspectRatioBox mb-2 rounded position-relative"
  style="background-image: url('./images/matt-zhou-unsplash.jpg')"
>
  <div
    class="position-absolute w-100 h-100 d-flex flex-column justify-content-center align-items-center overlay"
  >
    <span class="text-white">Show all experiences &gt;</span>
  </div>
</div>
```

你需要将叠加层的顶部位置设置为`0` ，使其位于父元素的正上方，也就是高宽比盒子的上方。

```
.overlay {
  top: 0;
}
```

剩下要做的唯一事情是添加一些透明度的绿色蓝色背景。

```
.overlay {
  top: 0;
  background-color: rgba(0, 255, 255, 0.3);
}
```

搞定！

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo30fk4gpj30vi094gtv.jpg)

### 号召性用语按钮

在主要内容之后添加号召性用语组件是一种常见的用户体验设计。Airbnb 选择带按钮的简单标题，要求用户输入他/她的旅行日期。

我们可以使用与前面所有部分相同的标题元素。

```
<div class="mt-3 py-4 py-lg-5 headings callToAction">
  <h4 class="mb-0 mb-md-1">When are you traveling?</h4>
  <p class="font-weight-light">
    Add dates for updated pricing and availability.
  </p>
  <button class="btn btn-success px-4">Add dates</button>
</div>
```

按钮和副标题的 CSS

```
/* ----------- Call to action ----------- */

@media (max-width: 767px) {
  .callToAction.headings p {
    font-size: 1rem;
  }
}

.callToAction button {
  background-color: #008489;
  padding-top: 12px;
  padding-bottom: 12px;
}
```

最后，让我们在`container-fluid`类的结束`` 元素之后添加一个`` 元素。这将创建一个横跨屏幕整个宽度的水平规则。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo30kwtt2j30zi0g9wnu.jpg)

### 第 4 部分结束

第 4 部分已经完成，只剩下页脚要做了。

你可以在下面看到完整的源代码。

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1, shrink-to-fit=no"
    />

    <!-- Bootstrap CSS -->
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"
    />

    <!-- Fontawesome -->
    <script
      src="https://kit.fontawesome.com/96ba351cc0.js"
      crossorigin="anonymous"
    ></script>

    <link rel="stylesheet" type="text/css" href="./style.css" />

    <title>Airbnb</title>
  </head>
  <body>
    <nav
      class="navbar navbar-expand-xl py-0 position-absolute w-100"
      id="navbar"
    >
      <!-- nav for xl screens -->

      <div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
        <a class="navbar-brand py-0 pr-0 pl-2 text-white" href="#">Airbnb</a>
        <div class="navbar-nav ml-auto">
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Become a host</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Earn credit</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Help</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Sign up</div></a
          >
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"
            ><div class="px-2">Log in</div></a
          >
        </div>
      </div>

      <!-- button and collapsed menu -->

      <a
        class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0 position-relative collapsed"
        role="button"
        data-toggle="collapse"
        href="#navbarMenu"
        id="navbarMenuToggler"
        >Airbnb</a
      >

      <div
        class="collapse navbar-collapse px-4 pb-4 font-weight-light bg-white position-absolute"
        id="navbarMenu"
      >
        <a class="nav-item nav-link" href="#">Home</a>
        <hr />
        <a class="nav-item nav-link" href="#">Invite friends</a>
        <a class="nav-item nav-link" href="#">Refer hosts</a>
        <a class="nav-item nav-link" href="#">Airbnb for work</a>
        <hr />
        <a class="nav-item nav-link" href="#"
          >Host a home<br /><small
            >Earn up to <b>$12,319 HKD a month</b></small
          ></a
        >
        <a class="nav-item nav-link" href="#">Host an experience</a>
        <a class="nav-item nav-link" href="#">Sign up</a>
        <a class="nav-item nav-link" href="#">Log in</a>
        <hr />
        <a class="nav-item nav-link" href="#">Help</a>
      </div>
    </nav>

    <!-- Hero content -->
    <div id="hero" class="position-relative">
      <div class="container-fluid">
        <h2 class="mb-0 pb-3 pb-sm-4 text-white d-xl-none">
          Book unique homes and experiences.
        </h2>
      </div>
      <div
        class="d-none d-xl-block text-right position-absolute p-4"
        id="message"
      >
        <a href="#" class="text-white"
          ><small class="font-weight-light"
            >Over 300<br />unique homes in Oregon</small
          ></a
        >
      </div>
    </div>

    <!-- Search form -->
    <div id="searchForm">
      <div class="container-fluid">
        <form class="py-4 rounded bg-white">
          <h2 class="d-none d-xl-block">Book unique homes and experiences.</h2>
          <div class="form-group">
            <label for="where"
              ><small><b>WHERE</b></small></label
            >
            <input
              type="text"
              class="form-control form-control-lg rounded"
              id="where"
              placeholder="Anywhere"
            />
          </div>
          <div class="row no-gutters">
            <div class="form-group col-6">
              <label for="checkin"
                ><small><b>CHECK IN</b></small></label
              >
              <input
                type="date"
                class="form-control form-control-lg rounded-left rounded-left"
                id="checkin"
                placeholder="mm/dd/yyyy"
              />
            </div>
            <div class="form-group col-6">
              <label for="checkout"
                ><small><b>CHECK OUT</b></small></label
              >
              <input
                type="date"
                class="form-control form-control-lg rounded-right border-left-0"
                id="checkout"
                placeholder="mm/dd/yyyy"
              />
            </div>
          </div>
          <div class="form-group">
            <label for="inputAddress"
              ><small><b>GUESTS</b></small></label
            >
            <select class="form-control form-control-lg rounded" id="guests">
              <option>1 guest</option>
              <option>2 guest</option>
            </select>
          </div>
          <div class="d-flex flex-column align-items-xl-end">
            <button type="submit" class="btn btn-danger px-4 mt-2">
              Search
            </button>
          </div>
        </form>
      </div>
    </div>

    <div class="container-fluid">
      <!-- First Section -->
      <div class="pt-3 pt-lg-4 pt-xl-5 headings">
        <h4 class="mb-3">
          What guests are saying about homes in United States
        </h4>
        <p>
          &#11088;
          <span class="d-none d-md-inline">United States homes were rated </span
          ><b>4.8 out of 5 stars</b> with <b>25,500,000+ reviews</b>
        </p>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div
              class="aspectRatioBox mb-3 rounded"
              style="background-image: url('./images/blake-wisz-634300-unsplash.jpg')"
            ></div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4">
              <small>
                We had a wonderful time staying in Murray & Kay's trailer. The
                location was beautiful and the trailer was adorable. We loved
                watching the sunset and the stars. We also had a great run in
                the morning on the bike path. We enjoyed going to the nearby
                country club for a wine tasting and to Malibu Cafe for dinner.
                We would definitely come back.
              </small>
            </p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Shelley</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div
              class="aspectRatioBox mb-3 rounded"
              style="background-image: url('./images/patrick-perkins-unsplash.jpg')"
            ></div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4">
              <small>
                Judy was very welcoming upon our arrival. We didn't get to meet
                Tom. Judy gave us a little tour of the Silver Cloud and made
                some excellent restaurant recommendations. The entire property
                is absolutely charming! The Silver Cloud is a great, cozy space
                for two people.
              </small>
            </p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Alyssa</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div
              class="aspectRatioBox mb-3 rounded"
              style="background-image: url('./images/brian-babb-unsplash.jpg')"
            ></div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4">
              <small>
                We had a fantastic stay at Doug and Chris' studio! It was a
                great location and they provided us with the best route to
                Disneyland. They were easy to communicate with and were helpful
                during our stay. We definitely want to stay again and it is a
                great alternative to staying at a hotel near Disneyland.
              </small>
            </p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Sarah</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler"></div>
      </div>

      <hr class="mt-4 mt-xl-5" />

      <!-- Value Props -->

      <div class="row flex-nowrap pt-2 pt-md-3 scrollableRow no-gutters">
        <div class="col-8 col-md-4">
          <div class="valueProp">
            <div class="icon mb-3">
              <i class="far fa-heart"></i>
            </div>
            <p class="title mb-1">24/7 customer support</p>
            <p class="description pr-4">
              <small>
                Day or night, we’re here for you. Talk to our support team from
                anywhere in the world, any hour of day.
              </small>
            </p>
          </div>
        </div>
        <div class="col-8 col-md-4">
          <div class="valueProp">
            <div class="icon mb-3">
              <i class="fas fa-home"></i>
            </div>
            <p class="title mb-1">Global hospitality standards</p>
            <p class="description pr-4">
              <small>
                Guests review their hosts after each stay. All hosts must
                maintain a minimum rating and our hospitality standards to be on
                Airbnb.
              </small>
            </p>
          </div>
        </div>
        <div class="col-8 col-md-4">
          <div class="valueProp">
            <div class="icon mb-3">
              <i class="far fa-user"></i>
            </div>
            <p class="title mb-1">5-star hosts</p>
            <p class="description pr-4">
              <small>
                From fresh-pressed sheets to tips on where to get the best
                brunch, our hosts are full of local hospitality.
              </small>
            </p>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler"></div>
      </div>

      <hr class="mt-2 mt-md-3 mb-0" />

      <!-- Home Listings -->
      <div class="pt-4 pt-lg-5 headings">
        <h4 class="mb-3">Homes in United States</h4>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/tyler-nix-685424-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>camper/rv · malibu</small>
            </p>
            <p class="title mb-0">Malibu Dream Airstream</p>
            <p class="pricing mb-0">
              <small>$600 per night · Free cancellation </small>
            </p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span
                ><span class="numberOfRatings">351</span> ·
                <span class="tag">Superhost</span></span
              >
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/neonbrand-263851-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>entire house · joshua tree</small>
            </p>
            <p class="title mb-0">The Joshua Tree House</p>
            <p class="pricing mb-0">
              <small>$285 per night · Free cancellation </small>
            </p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span
                ><span class="numberOfRatings">348</span> ·
                <span class="tag">Superhost</span></span
              >
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/jeremy-bishop-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>dome house · aptos</small>
            </p>
            <p class="title mb-0">
              Mushroom Dome Cabin: #1 on airbnb in the world
            </p>
            <p class="pricing mb-0">
              <small>$130 per night · Free cancellation </small>
            </p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span
                ><span class="numberOfRatings">1205</span> ·
                <span class="tag">Superhost</span></span
              >
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/travis-grossen-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>entire house · cazadero</small>
            </p>
            <p class="title mb-0">Cozy A-Frame Cabin in the Redwoods</p>
            <p class="pricing mb-0">
              <small>$175 per night · Free cancellation </small>
            </p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span
                ><span class="numberOfRatings">382</span> ·
                <span class="tag">Superhost</span></span
              >
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler"></div>
      </div>

      <div class="mt-3 d-none d-md-block">
        <a href="#" class="listingsLink">Show all (22,000+) &gt;</a>
      </div>

      <div class="pt-4 pt-lg-5 headings">
        <h4 class="mb-3">Top-rated experiences</h4>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/malcolm-lightbody-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>workshop · seattle</small>
            </p>
            <p class="title mb-0">Forge a knife from a horseshoe</p>
            <p class="pricing mb-0"><small>$95 per person</small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">210</span></span>
            </div>
          </div>
        </div>
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/greta-scholderle-moller-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>animal encounter · seattle</small>
            </p>
            <p class="title mb-0">Horse Riding</p>
            <p class="pricing mb-0"><small>$175 per person</small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">1147</span></span>
            </div>
          </div>
        </div>
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded"
              style="background-image: url('./images/phad-pichetbovornkul-unsplash.jpg')"
            ></div>
            <p class="mb-0 text-uppercase location">
              <small>day trip · san diego</small>
            </p>
            <p class="title mb-0">Day Trip Across the Border</p>
            <p class="pricing mb-0"><small>$75 per person</small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">93</span></span>
            </div>
          </div>
        </div>
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div
              class="aspectRatioBox mb-2 rounded position-relative"
              style="background-image: url('./images/matt-zhou-unsplash.jpg')"
            >
              <div
                class="position-absolute w-100 h-100 d-flex flex-column justify-content-center align-items-center overlay"
              >
                <span class="text-white">Show all experiences &gt;</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler"></div>
      </div>

      <div class="mt-3 py-4 py-lg-5 headings callToAction">
        <h4 class="mb-0 mb-md-1">When are you traveling?</h4>
        <p class="font-weight-light">
          Add dates for updated pricing and availability.
        </p>
        <button class="btn btn-success px-4">Add dates</button>
      </div>
    </div>

    <hr />

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script
      src="https://code.jquery.com/jquery-3.3.1.slim.min.js"
      integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
      integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
      integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
/* ----------- Container ----------- */
@media (min-width: 1200px) {
  .container-fluid {
    max-width: 1080px;
  }
}

.container-fluid,
.container {
  padding-left: 24px;
  padding-right: 24px;
}

/* ----------- Navigation ----------- */

@media (min-width: 1200px) {
  #navbarMenu {
    display: none !important;
  }

  #xlNavbar .nav-link div:hover {
    border-bottom: 2px solid #fff;
  }
}

#navbar {
  z-index: 1;
}

#xlNavbar .navbar-brand,
#navbarMenuToggler,
#xlNavbar .nav-link {
  line-height: 80px;
}

#xlNavbar .nav-link {
  font-size: 14px;
}

#navbarMenuToggler {
  color: rgb(255, 90, 95);
  transition: color 0.25s;
  z-index: 1;
}

#navbarMenuToggler.collapsed {
  color: #fff;
}

#navbarMenu .nav-link {
  color: #333;
}

#navbarMenu {
  top: 0;
  left: 0;
  right: 0;
  padding-top: 88px;
}

#navbarMenu .nav-link {
  padding: 12px 0;
}

/* ----------- Hero ----------- */

#hero {
  background-image: url(./images/luca-bravo-unsplash.jpg);
  background-size: cover;
  background-position: center bottom;
}

#hero h2 {
  padding-top: 168px;
}

#message {
  bottom: 0;
  right: 0;
}

@media (min-width: 1200px) {
  #hero {
    height: 100vh;
    min-height: 650px;
  }
}

/* ----------- Search form ----------- */

#searchForm .form-control {
  font-size: 15px;
  font-weight: 300;
  border-radius: 0;
}

#searchForm .btn-danger {
  padding-top: 12px;
  padding-bottom: 12px;
  background: #ff5a5f;
  border-color: #ff5a5f;
}

@media (min-width: 1200px) {
  #searchForm {
    position: absolute;
    top: 120px;
    width: 100%;
  }
  #searchForm form {
    padding: 32px;
    box-shadow: 0 16px 40px rgba(0, 0, 0, 0.12);
    max-width: 441px;
  }
}

/* ----------- Content ----------- */

@media (max-width: 767px) {
  .headings h4 {
    font-size: 18px;
  }
  .headings p {
    font-size: 13px;
  }
}

.scrollableRow {
  overflow-x: scroll;
  margin-left: -24px;
  margin-right: -24px;
  padding-left: 18px;
  padding-right: 18px;
}

.scrollableRow > [class*="col-"] {
  padding-left: 6px;
  padding-right: 6px;
}

.scrollableRow .filler {
  min-width: 18px;
}

.aspectRatioBox {
  padding-top: calc(2 / 3 * 100%);
  background-size: cover;
  background-position: center;
}

.description {
  line-height: 18px;
}

/* ----------- Reviews ----------- */

.review .description {
  max-height: 60px;
  overflow: hidden;
  /* using line clamp */
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  text-overflow: ellipsis;
}

.review .user i {
  font-size: 48px;
}

.review .user .name b {
  font-weight: 500;
}

.review .user .location {
  line-height: 18px;
}

/* ------------ Value Props ------------ */

.valueProp .icon {
  font-size: 40px;
  line-height: 40px;
  color: rgb(65, 198, 188);
}

.valueProp .title {
  font-weight: 500;
}

/* ------------ Listings ------------ */

.listing .location {
  line-height: 18px;
}

.listing .location small {
  font-weight: 700;
  font-size: 12px;
}

.listing .title {
  font-weight: 600;
  margin-top: 1px;
  color: #484848;
}

.listing .pricing {
  line-height: 18px;
  margin-top: 2px;
}

.listing .pricing small {
  font-weight: 300;
}

.listing .info {
  font-size: 12px;
  font-weight: 500;
  margin-top: 3px;
}

.listing .info .rating {
  font-size: 8.5px;
  letter-spacing: -1px;
  margin-right: 3px;
}

.listingsLink {
  color: #008489;
  font-size: 17px;
}

.overlay {
  top: 0;
  background-color: rgba(0, 255, 255, 0.3);
}

/* ----------- Call to action ----------- */

@media (max-width: 767px) {
  .callToAction.headings p {
    font-size: 1rem;
  }
}

.callToAction button {
  background-color: #008489;
  padding-top: 12px;
  padding-bottom: 12px;
}
```

# Airbnb 克隆第 5 部分

我们即将结束克隆实验，我们只剩下页脚了。与往常一样，我们首先检查原始布局。

在 `md` 及以上，我们有一个由四列组成的页脚导航。然后是一个页脚栏，包含版权，语言和货币选择。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo31e2amjj30zh0brjsi.jpg)

在 `xs` 和 `md` 之间，列链接消失了。我们只留下了页脚栏。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo31ialczj30km03hdfq.jpg)

### 网站链接

站点链接和页脚栏都包含在容器中。所以我们应该从通常的`container-fluid`设置开始。

```
<footer class="container-fluid">
  <!-- Footer -->
  <div class="row pt-5 d-none d-md-flex footerNav">
    <div class="col-3">
      <h5 class="mb-3">Airbnb</h5>
      <ul class="list-unstyled mb-1">
        <li><a href="#" class="text-secondary">Careers</a></li>
        <li><a href="#" class="text-secondary">Press</a></li>
        <li><a href="#" class="text-secondary">Policies</a></li>
        <li><a href="#" class="text-secondary">Help</a></li>
        <li><a href="#" class="text-secondary">Diversity & Belonging</a></li>
      </ul>
    </div>
    <div class="col-3">
      <h5 class="mb-3">Discover</h5>
      <ul class="list-unstyled mb-1">
        <li><a href="#" class="text-secondary">Trust & Safety</a></li>
        <li><a href="#" class="text-secondary">Travel Credit</a></li>
        <li><a href="#" class="text-secondary">Gift Cards</a></li>
        <li><a href="#" class="text-secondary">Airbnb Citizen</a></li>
        <li><a href="#" class="text-secondary">Business Travel</a></li>
        <li><a href="#" class="text-secondary">Guidebooks</a></li>
        <li><a href="#" class="text-secondary">Airbnbmag</a></li>
        <li><a href="#" class="text-secondary">Events<span class="ml-1 badge badge-secondary font-weight-light p-1">New</span></a></li>
      </ul>
    </div>
    <div class="col-3">
      <h5 class="mb-3">Hosting</h5>
      <ul class="list-unstyled mb-1">
        <li><a href="#" class="text-secondary">Why Host</a></li>
        <li><a href="#" class="text-secondary">Hospitality</a></li>
        <li><a href="#" class="text-secondary">Responsible Hosting</a></li>
        <li><a href="#" class="text-secondary">Community Center</a></li>
        <li><a href="#" class="text-secondary">Host an Experience<span class="ml-1 badge badge-secondary font-weight-light p-1">New</span></a></li>
        <li><a href="#" class="text-secondary">Open Homes<span class="ml-1 badge badge-secondary font-weight-light p-1">New</span></a></li>
      </ul>
    </div>
    <div class="col-3">
      <h5 class="mb-3 social">
        <i class="text-secondary mr-3 fab fa-facebook-f"></i>
        <i class="text-secondary mr-3 fab fa-twitter"></i>
        <i class="text-secondary fab fa-instagram"></i>
      </h5>
      <ul class="list-unstyled mb-1">
        <li><a href="#" class="text-secondary">Terms</a></li>
        <li><a href="#" class="text-secondary">Privacy</a></li>
        <li><a href="#" class="text-secondary">Site Map</a></li>
      </ul>
    </div>
  </div>

  <hr class="d-none d-md-block" />

  <div class="row justify-content-between align-items-center mb-4 mb-md-5 mt-5 mt-md-0 footerBar">
    <div class="col-auto">
      <small class="text-secondary">© Airbnb, Inc.</small>
    </div>
    <div class="col-auto">
      <button class="btn btn-link px-1 text-dark select">
        <small>English <span class="pl-1 angle d-inline-block">&gt;</span></small>
      </button>
      <button class="btn btn-link px-1 text-dark select">
        <small>USD <span class="pl-1 angle d-inline-block">&gt;</span></small>
      </button>
    </div>
  </div>
</footer>
```

站点链接由包含四个列元素的行元素组成，每列占用宽度的四分之一，所以我们选择`col-3` 。由于网站链接行消失在`md` 以下，因此将`d-none d-md-flex`添加到`row`元素。

这次我们使用无序列表作为网站链接。你可以将`list-unstyled` 添加到`` 元素中，以摆脱默认的Bootstrap列表样式。

对于“ New”徽章，我们使用的是Bootstrap的徽章类，你可以在https://getbootstrap.net/docs/components/badge/查看文档，这是一个非常便利的Bootstrap组件。

社交媒体图标来自FontAwesome，它们提供了很多品牌图标。

站点链接和页脚栏之间的`` 也需要`d-none d-md-block`，这样它会随着缩小屏幕而消失。

页脚栏也使用行和列，但是使用flex属性对齐。这是一个很好的场景，我们将使用`col-auto` 用于仅占用其内容宽度的列。

没有任何自定义CSS，我们的页脚当前如下所示。

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo31o3fr0j30zh0blmzy.jpg)

### 设置字体大小

剩下要做的就是调整一些字体大小并旋转两个按钮的尖括号，使它们朝下。

首先，字体大小。

```
/* ----------- Footer ----------- */

.footerNav h5, .footerNav a {
  font-size: 14px;
}

.footerNav h5 {
  line-height: 18px;
}

.footerNav .social {
  font-size: 18px;
  height: 18px;
}

.footerBar small {
  font-size: 14px;
}
```

### 旋转角支架

要旋转尖括号，我们将使用CSS转换。请注意，我们将`d-inline-block` 类添加到尖括号中，因为变换不适用于嵌入式元素。

```
.footerBar .select .angle {
  transform: rotate(90deg);
}
```

搞定!

![img](https://tva1.sinaimg.cn/large/0082zybpgy1gbo31t9ndqj30zh0azq5b.jpg)

### 我们学到了什么？

如我所述，此演练的关键目的是演示使用诸如Bootstrap 4之类的框架快速搭建一个网页。我们学会了利用Bootstrap的网格及其灵活性。我们还使用了许多Bootstrap组件，并利用了一些Web资源来创建克隆。我在下面的列出了此次演练的重要主题，因此你可以回过头再进行重点研究。

**注意：**我们应从本演练中学到最重要一点是：精美的图像和良好的间距是精美网站的关键。

##### 第1部分：

- 通过屏幕断点分解网站布局。
- 先对最上面的组件开始进行操作。
- 使用Bootstrap的导航栏和折叠菜单。
- 充分利用Bootstrap类和组件进行工作，将自定义的CSS降至最低。

##### 第2部分：

- 使用Bootstrap的文本颜色便捷类来更改文本颜色。
- 使用绝对定位从页面流中删除导航栏，因此它位于hero元素的顶部。
- 展开菜单时，使用绝对定位来放置折叠菜单。
- 使用过渡添加效果。
- Bootstrap的表单组件很好用。
- 可以在行元素上使用`no-gutters`，以摆脱Bootstrap列之间的默认网格间距。
- 使用`vh` 可使元素占据可见区域的整个高度。
- [unsplash.com](http://unsplash.com/) 有许多免费的高质量图片。

##### 第3部分：

- 你可以直接在HTML文件中使用表情符号字符。
- 利用Bootstrap网格结构快速布局。
- FontAwesome有很多免费图标。
- [placeholder.com](http://placeholder.com/)生成任何大小和颜色的动态占位图像。
- 将`overflow`设置为滚动将允许用户可以将溢出项目滚动到视图中来。
- 如何使用Bootstrap时定义自定义gutter尺寸。
- 添加补充元素（filler element)以笨拙地修补浏览器溢出内边距问题。
- 使用`-webkit-line-clamp` 在多行中封闭段落。
- 使用高宽比盒子可以创建相同长宽比的图像框。

##### 第4部分：

- 如何用文本创建彩色叠加层。
- 共享清单的CSS类可减少编写的自定义CSS的数量。

##### 第5部分：

- Bootstrap 徽章很好用。
- 使用transform旋转元素。

我希望你从这次演练中学到很多东西，并且我对你将来可以创造的东西寄予很高的期望。

你可以在下面查看完整的源代码。

```
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

    <!-- Fontawesome -->
    <script src="https://kit.fontawesome.com/96ba351cc0.js" crossorigin="anonymous"></script>

    <link rel="stylesheet" type="text/css" href="./style.css">

    <title>Airbnb</title>
  </head>
  <body>
    <nav class="navbar navbar-expand-xl py-0 position-absolute w-100" id="navbar">
      <!-- nav for xl screens -->

      <div class="d-none d-xl-flex flex-grow-1" id="xlNavbar">
        <a class="navbar-brand py-0 pr-0 pl-2 text-white" href="#">Airbnb</a>
        <div class="navbar-nav ml-auto">
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"><div class="px-2">Become a host</div></a>
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"><div class="px-2">Earn credit</div></a>
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"><div class="px-2">Help</div></a>
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"><div class="px-2">Sign up</div></a>
          <a class="nav-item nav-link py-0 px-2 text-white" href="#"><div class="px-2">Log in</div></a>
        </div>
      </div>

      <!-- button and collapsed menu -->

      <a class="navbar-toggler navbar-brand py-0 pr-0 pl-2 border-0 position-relative collapsed" role="button" data-toggle="collapse" href="#navbarMenu" id="navbarMenuToggler">Airbnb</a>

      <div class="collapse navbar-collapse px-4 pb-4 font-weight-light bg-white position-absolute" id="navbarMenu">
        <a class="nav-item nav-link" href="#">Home</a>
        <hr/>
        <a class="nav-item nav-link" href="#">Invite friends</a>
        <a class="nav-item nav-link" href="#">Refer hosts</a>
        <a class="nav-item nav-link" href="#">Airbnb for work</a>
        <hr/>
        <a class="nav-item nav-link" href="#">Host a home<br/><small>Earn up to <b>$12,319 HKD a month</b></small></a>
        <a class="nav-item nav-link" href="#">Host an experience</a>
        <a class="nav-item nav-link" href="#">Sign up</a>
        <a class="nav-item nav-link" href="#">Log in</a>
        <hr/>
        <a class="nav-item nav-link" href="#">Help</a>
      </div>
    </nav>

    <!-- Hero content -->
    <div id="hero" class="position-relative">
      <div class="container-fluid">
        <h2 class="mb-0 pb-3 pb-sm-4 text-white d-xl-none">Book unique homes and experiences.</h2>
      </div>
      <div class="d-none d-xl-block text-right position-absolute p-4" id="message">
        <a href="#" class="text-white"><small class="font-weight-light">Over 300<br/>unique homes in Oregon</small></a>
      </div>
    </div>

    <!-- Search form -->
    <div id="searchForm">
      <div class="container-fluid">
        <form class="py-4 rounded bg-white">
          <h2 class="d-none d-xl-block">Book unique homes and experiences.</h2>
          <div class="form-group">
            <label for="where"><small><b>WHERE</b></small></label>
            <input type="text" class="form-control form-control-lg rounded" id="where" placeholder="Anywhere">
          </div>
          <div class="row no-gutters">
            <div class="form-group col-6">
              <label for="checkin"><small><b>CHECK IN</b></small></label>
              <input type="date" class="form-control form-control-lg rounded-left rounded-left" id="checkin" placeholder="mm/dd/yyyy">
            </div>
            <div class="form-group col-6">
              <label for="checkout"><small><b>CHECK OUT</b></small></label>
              <input type="date" class="form-control form-control-lg rounded-right border-left-0" id="checkout" placeholder="mm/dd/yyyy">
            </div>
          </div>
          <div class="form-group">
            <label for="inputAddress"><small><b>GUESTS</b></small></label>
            <select class="form-control form-control-lg rounded" id="guests">
              <option>1 guest</option>
              <option>2 guest</option>
            </select>
          </div>
          <div class="d-flex flex-column align-items-xl-end">
            <button type="submit" class="btn btn-danger px-4 mt-2">Search</button>
          </div>
        </form>
      </div>
    </div>

    <div class="container-fluid">
      <!-- First Section -->
      <div class="pt-3 pt-lg-4 pt-xl-5 headings">
        <h4 class="mb-3">What guests are saying about homes in United States</h4>
        <p>&#11088; <span class="d-none d-md-inline">United States homes were rated </span><b>4.8 out of 5 stars</b> with <b>25,500,000+ reviews</b></p>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div class="aspectRatioBox mb-3 rounded" style="background-image: url('./images/blake-wisz-unsplash.jpg')">
            </div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4"><small>
              We had a wonderful time staying in Murray & Kay's trailer. The location was beautiful and the trailer was adorable. We loved watching the sunset and the stars. We also had a great run in the morning on the bike path. We enjoyed going to the nearby country club for a wine tasting and to Malibu Cafe for dinner. We would definitely come back.
            </small></p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Shelley</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div class="aspectRatioBox mb-3 rounded" style="background-image: url('./images/patrick-perkins-unsplash.jpg')">
            </div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4"><small>
              Judy was very welcoming upon our arrival. We didn't get to meet Tom. Judy gave us a little tour of the Silver Cloud and made some excellent restaurant recommendations. The entire property is absolutely charming! The Silver Cloud is a great, cozy space for two people.
            </small></p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Alyssa</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-4">
          <div class="review">
            <div class="aspectRatioBox mb-3 rounded" style="background-image: url('./images/brian-babb-unsplash.jpg')">
            </div>
            <div class="rating mb-2 text-black-50">
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
              <i class="fas fa-star"></i>
            </div>
            <p class="description pr-4"><small>
              We had a fantastic stay at Doug and Chris' studio! It was a great location and they provided us with the best route to Disneyland. They were easy to communicate with and were helpful during our stay. We definitely want to stay again and it is a great alternative to staying at a hotel near Disneyland.
            </small></p>
            <div class="user d-flex flex-row">
              <i class="far fa-user-circle mr-3"></i>
              <div>
                <p class="name mb-0"><b>Sarah</b></p>
                <p class="location mb-0"><small>United States</small></p>
              </div>
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler">
        </div>
      </div>

      <hr class="mt-4 mt-xl-5" />

      <!-- Value Props -->

      <div class="row flex-nowrap pt-2 pt-md-3 scrollableRow no-gutters">
        <div class="col-8 col-md-4">
          <div class="valueProp">
            <div class="icon mb-3">
              <i class="far fa-heart"></i>
            </div>
            <p class="title mb-1">24/7 customer support</p>
            <p class="description pr-4"><small>
              Day or night, we’re here for you. Talk to our support team from anywhere in the world, any hour of day.
            </small></p>
          </div>
        </div>
        <div class="col-8 col-md-4">
          <div class="valueProp">
            <div class="icon mb-3">
              <i class="fas fa-home"></i>
            </div>
            <p class="title mb-1">Global hospitality standards</p>
            <p class="description pr-4"><small>
              Guests review their hosts after each stay. All hosts must maintain a minimum rating and our hospitality standards to be on Airbnb.
            </small></p>
          </div>
        </div>
        <div class="col-8 col-md-4">
          <div class="valueProp">
            <div class="icon mb-3">
              <i class="far fa-user"></i>
            </div>
            <p class="title mb-1">5-star hosts</p>
            <p class="description pr-4"><small>
              From fresh-pressed sheets to tips on where to get the best brunch, our hosts are full of local hospitality.
            </small></p>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler">
        </div>
      </div>

      <hr class="mt-2 mt-md-3 mb-0" />

      <!-- Home Listings -->
      <div class="pt-4 pt-lg-5 headings">
        <h4 class="mb-3">Homes in United States</h4>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/tyler-nix-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>camper/rv · malibu</small></p>
            <p class="title mb-0">Malibu Dream Airstream</p>
            <p class="pricing mb-0"><small>$600 per night · Free cancellation
            </small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">351</span> · <span class="tag">Superhost</span></span>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/neonbrand-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>entire house · joshua tree</small></p>
            <p class="title mb-0">The Joshua Tree House</p>
            <p class="pricing mb-0"><small>$285 per night · Free cancellation
            </small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">348</span> · <span class="tag">Superhost</span></span>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/jeremy-bishop-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>dome house · aptos</small></p>
            <p class="title mb-0">Mushroom Dome Cabin: #1 on airbnb in the world</p>
            <p class="pricing mb-0"><small>$130 per night · Free cancellation
            </small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">1205</span> · <span class="tag">Superhost</span></span>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/travis-grossen-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>entire house · cazadero</small></p>
            <p class="title mb-0">Cozy A-Frame Cabin in the Redwoods</p>
            <p class="pricing mb-0"><small>$175 per night · Free cancellation
            </small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">382</span> · <span class="tag">Superhost</span></span>
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler">
        </div>
      </div>

      <div class="mt-3 d-none d-md-block">
        <a href="#" class="listingsLink">Show all (22,000+) &gt;</a>
      </div>

      <div class="pt-4 pt-lg-5 headings">
        <h4 class="mb-3">Top-rated experiences</h4>
      </div>

      <div class="row flex-nowrap pt-2 scrollableRow no-gutters">
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/malcolm-lightbody-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>workshop · seattle</small></p>
            <p class="title mb-0">Forge a knife from a horseshoe</p>
            <p class="pricing mb-0"><small>$95 per person</small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">210</span></span>
            </div>
          </div>
        </div>
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/greta-scholderle-moller-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>animal encounter · seattle</small></p>
            <p class="title mb-0">Horse Riding</p>
            <p class="pricing mb-0"><small>$175 per person</small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">1147</span></span>
            </div>
          </div>
        </div>
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded" style="background-image: url('./images/phad-pichetbovornkul-unsplash.jpg')">
            </div>
            <p class="mb-0 text-uppercase location"><small>day trip · san diego</small></p>
            <p class="title mb-0">Day Trip Across the Border</p>
            <p class="pricing mb-0"><small>$75 per person</small></p>
            <div class="info d-flex align-items-center">
              <span class="rating text-black-50">
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
                <i class="fas fa-star"></i>
              </span>
              <span><span class="numberOfRatings">93</span></span>
            </div>
          </div>
        </div>
        <div class="col-8 col-md-6 col-xl-3">
          <div class="listing">
            <div class="aspectRatioBox mb-2 rounded position-relative" style="background-image: url('./images/matt-zhou-unsplash.jpg')">
              <div class="position-absolute w-100 h-100 d-flex flex-column justify-content-center align-items-center overlay">
                <span class="text-white">Show all experiences &gt;</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Filler -->
        <div class="d-xl-none filler">
        </div>
      </div>

      <div class="mt-3 py-4 py-lg-5 headings callToAction">
        <h4 class="mb-0 mb-md-1">When are you traveling?</h4>
        <p class="font-weight-light">Add dates for updated pricing and availability.</p>
        <button class="btn btn-success px-4">Add dates</button>
      </div>

    </div>

    <hr />


    <footer class="container-fluid">
      <!-- Footer -->
      <div class="row pt-5 d-none d-md-flex footerNav">
        <div class="col-3">
          <h5 class="mb-3">Airbnb</h5>
          <ul class="list-unstyled mb-1">
            <li><a href="#" class="text-secondary">Careers</a></li>
            <li><a href="#" class="text-secondary">Press</a></li>
            <li><a href="#" class="text-secondary">Policies</a></li>
            <li><a href="#" class="text-secondary">Help</a></li>
            <li><a href="#" class="text-secondary">Diversity & Belonging</a></li>
          </ul>
        </div>
        <div class="col-3">
          <h5 class="mb-3">Discover</h5>
          <ul class="list-unstyled mb-1">
            <li><a href="#" class="text-secondary">Trust & Safety</a></li>
            <li><a href="#" class="text-secondary">Travel Credit</a></li>
            <li><a href="#" class="text-secondary">Gift Cards</a></li>
            <li><a href="#" class="text-secondary">Airbnb Citizen</a></li>
            <li><a href="#" class="text-secondary">Business Travel</a></li>
            <li><a href="#" class="text-secondary">Guidebooks</a></li>
            <li><a href="#" class="text-secondary">Airbnbmag</a></li>
            <li><a href="#" class="text-secondary">Events<span class="ml-1 badge badge-secondary font-weight-light p-1">New</span></a></li>
          </ul>
        </div>
        <div class="col-3">
          <h5 class="mb-3">Hosting</h5>
          <ul class="list-unstyled mb-1">
            <li><a href="#" class="text-secondary">Why Host</a></li>
            <li><a href="#" class="text-secondary">Hospitality</a></li>
            <li><a href="#" class="text-secondary">Responsible Hosting</a></li>
            <li><a href="#" class="text-secondary">Community Center</a></li>
            <li><a href="#" class="text-secondary">Host an Experience<span class="ml-1 badge badge-secondary font-weight-light p-1">New</span></a></li>
            <li><a href="#" class="text-secondary">Open Homes<span class="ml-1 badge badge-secondary font-weight-light p-1">New</span></a></li>
          </ul>
        </div>
        <div class="col-3">
          <h5 class="mb-3 social">
            <i class="text-secondary mr-3 fab fa-facebook-f"></i>
            <i class="text-secondary mr-3 fab fa-twitter"></i>
            <i class="text-secondary fab fa-instagram"></i>
          </h5>
          <ul class="list-unstyled mb-1">
            <li><a href="#" class="text-secondary">Terms</a></li>
            <li><a href="#" class="text-secondary">Privacy</a></li>
            <li><a href="#" class="text-secondary">Site Map</a></li>
          </ul>
        </div>
      </div>

      <hr class="d-none d-md-block" />

      <div class="row justify-content-between align-items-center mb-4 mb-md-5 mt-5 mt-md-0 footerBar">
        <div class="col-auto">
          <small class="text-secondary">© Airbnb, Inc.</small>
        </div>
        <div class="col-auto">
          <button class="btn btn-link px-1 text-dark select">
            <small>English <span class="pl-1 angle d-inline-block">&gt;</span></small>
          </button>
          <button class="btn btn-link px-1 text-dark select">
            <small>USD <span class="pl-1 angle d-inline-block">&gt;</span></small>
          </button>
        </div>
      </div>
    </footer>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
  </body>
</html>
/* ----------- Container ----------- */
@media (min-width: 1200px) {
  .container-fluid {
    max-width: 1080px;
  }
}

.container-fluid, .container {
  padding-left: 24px;
  padding-right: 24px;
}

/* ----------- Navigation ----------- */

@media (min-width: 1200px) {
  #navbarMenu {
    display: none !important;
  }

  #xlNavbar .nav-link div:hover {
    border-bottom: 2px solid #fff;
  }
}

#navbar {
  z-index: 1;
}

#xlNavbar .navbar-brand, #navbarMenuToggler, #xlNavbar .nav-link {
  line-height: 80px;
}

#xlNavbar .nav-link {
  font-size: 14px;
}

#navbarMenuToggler {
  color: rgb(255, 90, 95);
  transition: color 0.25s;
  z-index: 1;
}

#navbarMenuToggler.collapsed {
  color: #fff;
}

#navbarMenu .nav-link {
  color: #333;
}

#navbarMenu {
  top: 0;
  left: 0;
  right: 0;
  padding-top: 88px;
}

#navbarMenu .nav-link {
  padding: 12px 0;
}

/* ----------- Hero ----------- */

#hero {
  background-image: url(./images/luca-bravo-121931-unsplash.jpg);
  background-size: cover;
  background-position: center bottom;
}

#hero h2 {
  padding-top: 168px;
}

#message {
  bottom: 0;
  right: 0;
}

@media (min-width: 1200px) {
  #hero {
    height: 100vh;
    min-height: 650px;
  }
}

/* ----------- Search form ----------- */

#searchForm .form-control {
  font-size: 15px;
  font-weight: 300;
  border-radius: 0;
}

#searchForm .btn-danger {
  padding-top: 12px;
  padding-bottom: 12px;
  background: #FF5A5F;
  border-color: #FF5A5F;
}

@media (min-width: 1200px) {
  #searchForm {
    position: absolute;
    top: 120px;
    width: 100%;
  }
  #searchForm form {
    padding: 32px;
    box-shadow: 0 16px 40px rgba(0,0,0,0.12);
    max-width: 441px;
  }
}

/* ----------- Content ----------- */

@media (max-width: 767px) {
  .headings h4 {
    font-size: 18px;
  }
  .headings p {
    font-size: 13px;
  }
}

.scrollableRow {
  overflow-x: scroll;
  margin-left: -24px;
  margin-right: -24px;
  padding-left: 18px;
  padding-right: 18px;
}

.scrollableRow > [class*=col-] {
  padding-left: 6px;
  padding-right: 6px;
}

.scrollableRow .filler {
  min-width: 18px;
}

.aspectRatioBox {
  padding-top: calc(2 / 3 * 100%);
  background-size: cover;
  background-position: center;
}

.description {
  line-height: 18px;
}

/* ----------- Reviews ----------- */

.review .description {
  max-height: 60px;
  overflow: hidden;
  /* using line clamp */
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  text-overflow: ellipsis;
}

.review .user i {
  font-size: 48px;
}

.review .user .name b {
  font-weight: 500;
}

.review .user .location {
  line-height: 18px;
}

/* ------------ Value Props ------------ */

.valueProp .icon {
  font-size: 40px;
  line-height: 40px;
  color: rgb(65, 198, 188);
}

.valueProp .title {
  font-weight: 500;
}

/* ------------ Listings ------------ */

.listing .location {
  line-height: 18px;
}

.listing .location small {
  font-weight: 700;
  font-size: 12px;
}

.listing .title {
  font-weight: 600;
  margin-top: 1px;
  color: #484848;
}

.listing .pricing {
  line-height: 18px;
  margin-top: 2px;
}

.listing .pricing small {
  font-weight: 300;
}

.listing .info {
  font-size: 12px;
  font-weight: 500;
  margin-top: 3px;
}

.listing .info .rating {
  font-size: 8.5px;
  letter-spacing: -1px;
  margin-right: 3px;
}

.listingsLink {
  color: #008489;
  font-size: 17px;
}

.overlay {
  top: 0;
  background-color: rgba(0, 255, 255, 0.3);
}

/* ----------- Call to action ----------- */

@media (max-width: 767px) {
  .callToAction.headings p {
    font-size: 1rem;
  }
}

.callToAction button {
  background-color: #008489;
  padding-top: 12px;
  padding-bottom: 12px;
}

/* ----------- Footer ----------- */

.footerNav h5, .footerNav a {
  font-size: 14px;
}

.footerNav h5 {
  line-height: 18px;
}

.footerNav .social {
  font-size: 18px;
  height: 18px;
}

.footerBar small {
  font-size: 14px;
}

.footerBar .select .angle {
  transform: rotate(90deg);
}
```

# 相关笔记





