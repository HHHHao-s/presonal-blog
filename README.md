<style>
@import url('https://fonts.googleapis.com/css2?family=Crimson+Text:ital,wght@0,400;0,600;0,700;1,400;1,600;1,700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Alegreya:ital,wght@0,400;0,500;0,700;0,800;0,900;1,400;1,500;1,700;1,800;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

:root {
  --head: 'Microsoft Yahei';
  --body: 'Microsoft Yahei', sans-serif;
  --mono: 'Microsoft Yahei';
  font-family: var(--body);
  font-size: 12pt;

  --offwhite: #fcf5e5;
  --green: #e0e5c1;
  --yellow: #c9ad6a;
  --red: #822000;
  --purple: #704cd9;
}

/** Background **/

content, .typora-export-content {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  overflow-y: scroll;
  background-image: url("torillic/torillic-bg.jpg");
  background-size: cover;
  background-position: center;
  z-index: -2;
}
.typora-export-content {
  top: 0;
}
content:after, .typora-export-content:after {
  content: "Background: Dmitry Demidov via Pexels [#3843969]";
  position: fixed;
  bottom: 1cm;
  left: 0;
  width: 6.5cm;
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  z-index: -1;
  font-size: 8pt;
  padding: 2mm 3mm;
  border-radius: 0 2mm 2mm 0;
}

/** Page **/
#write, #typora-source {
  position: relative;
  margin: 4rem auto;
  width: 21cm;
  min-height: 80vh;
  padding: 2cm;
  overflow-y: hidden;
  box-shadow:
    inset 0cm -0cm 0.1cm 0.05cm rgba(0, 0, 0, 0.1),
    1cm 1cm 1cm 1cm rgba(0, 0, 0, 0.5);
  transform-style: preserve-3d;
  background-image: url("https://www.dndbeyond.com/content/1-0-1895-0/skins/waterdeep/images/mon-summary/paper-texture.png");
  background-color: var(--offwhite);
  /* Add columns */
  column-count: 2;
  column-gap: 0.5cm;
  column-width: 8cm;
}
#typora-source {
  font-family: var(--mono) !important;
  column-count: 1 !important;
  column-width: auto !important;
}
#write p, #write h1, #write h2, #write h3, #write h4, #write h5, #write h6, #write div, #write pre {
  width: auto;
}
#write > *:first-child {
  margin-block-start: 0;
}
.ty-on-typewriter-mode #write {
  column-count: 1;
  padding-bottom: 50%;
}

/** Responsivity **/
/* Compress for small windows */
@media only screen and (max-width: 22cm) {
  #write, #typora-source {
    column-count: 1;
    width: calc(100% - 2rem);
    margin: 1rem;
  }
}
/* Hide background credit if there's no width */
@media only screen and (max-width: 37cm) {
  content:after, .typora-export-content:after {
    left: -6.1cm
  }
}

/** Export **/
@media print {
    content, .typora-export-content {
      position: relative;
      background: none;
      overflow-y: visible;
    }
    content:after, .typora-export-content:after {
      display: none;
    }
    #write, #typora-source {
        min-height: 0;
        padding: 0;
        overflow-y: visible;
        box-shadow: none;
        background: none;
    }
}

body {
    font-family: var(--body)
}

/** Headings **/

/* All headings */
h1, h2, h3, h4, h5, h6 {
    
  margin-block-end: 2pt;
  margin-block-start: 1em;
  line-height: 1em;
  break-inside: avoid;
  break-after: avoid;
}

/* Major headings */
h1, h2, h3, h4 {
  font-family: var(--head);
  font-weight: 700;
  font-variant: small-caps;
  color: var(--red);
}

/* Individual headings */
h1 {
  font-size: 28pt;
  column-span: all;
}

h2 {
  font-size: 24pt;
  column-span: all;
}

h3 {
  font-size: 18pt;
  margin-left: 10px;
}

h4 {
  font-size: 14pt;
  border-bottom: 1pt solid var(--yellow);
  border-bottom: 1pt solid var(--yellow);
}
h4 a {
  text-decoration: none;
}

h5 {
  font-size: 12pt;
}


h6 {
  font-size: 10pt;
  font-weight: 400;
  text-decoration: underline;
  text-decoration-color: var(--yellow);
}

hr {
  /* Common to all hr's */
  border-top: 2pt solid transparent;
  border-bottom: 2pt solid transparent;
  border-left-style: solid;
  border-left-color: var(--red);

  /* Top-level hr (aka page delineator) */
  column-span: all;
  border-left-width: 16cm;
  margin-top: 18pt;
  margin-bottom: 36pt;
}

blockquote hr {
  /* Within a blockquote (aka fancy underline) */
  column-span: none;
  border-left-width: 6cm;
  margin-top: 2pt;
  margin-bottom: 2pt;
}

/** Body **/
p {
  margin-block-start: 2pt;
  break-inside: avoid;
}

strong {
  color: var(--red);
}

a {
  color: var(--text-color);
  text-decoration-color: var(--yellow);
}
a:visited {
  text-decoration-color: var(--green);
}
a:hover {
  color: var(--text-color);
  text-decoration-color: var(--purple);
}
h1 a,
h2 a,
h3 a,
h4 a,
strong a {
  color: var(--red);
}

del {
  text-decoration-color: var(--red);
}

mark {
  background-color: var(--green);
}

code, pre {
  background: auto;
  font-family: var(--mono);
}

ol, ul {
  padding-left: 1rem;
}

li::marker {
  font-weight: 700;
  color: var(--red);
}

/** Tables **/
table {
  break-inside: avoid;
}

thead, th {
  font-weight: 700;
}

tbody tr:nth-child(odd) {
  background-color: var(--green);
}

blockquote tbody tr:nth-child(odd), pre blockquote tbody tr:nth-child(odd) {
  background-color: rgba(255, 255, 255, 0.2);
}

td, th {
  padding: 3pt 6pt;
}

/** Blocks **/
pre, pre.md-meta-block {
  background-color: var(--green);
  padding: 6pt;
}

blockquote {
  background-color: var(--green);
  padding: 12pt;
  border-top: 3pt solid var(--red);
  border-bottom: 3pt solid var(--red);
  break-inside: avoid;
}

blockquote blockquote {
  background-color: rgba(255, 255, 255, 0.5);
}

/** Images **/

.md-image {
  z-index: 0;
}

.md-image:before {
  position: absolute;
  top: -1.5cm;
  left: -1.5cm;
  right: -1.5cm;
  bottom: -0.5cm;
  background-image: url("torillic/splash.png");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center top;
  content: " ";
  z-index: -1;
}
.on-focus-mode .md-image:before {
  opacity: 0.2;
}
</style>


# <center style="font-size: 40px">**个人博客**

# **个人博客选题分析**

## **选题背景**

博客是一种个人的网络日记，是一种用来记录个人生活、感悟、思考和经验的网络日记。近年来，随着信息技术的进步，博客也快速发展。为人们提供了一个自由、开放、互动的交流平台。博客不仅可以帮助个人实现自我表达和展示，也可以为企业、政府、媒体等机构提供一个有效的宣传和传播渠道。沟通方式比电子邮件、讨论群组以及BBS和论坛更展现个性，博客系统已经成为广大用户发表文章言论的主要工具。个人博客可以分享自己的想法，为自己的产出引流。




# **问题**
这段文本描述了一个博客网站的功能和系统设计方法。以下是其中可能存在的问题：

1. 游客浏览和评价功能：
   - 没有提到游客可以如何访问网页和浏览内容的方式，例如是否需要注册账号或者可以匿名访问。
   - 在浏览记录和评价添加到数据库中时，没有提及具体的数据结构和字段。
   - 针对评价的排序方式没有具体说明，是按照时间排序还是其他指标。

2. 站主文章管理功能：
   - 对已有内容的修改没有具体说明，是否包括修改文章的标题、内容和其他属性。
   - 关于图片和附件的引用，没有提到如何管理和存储这些文件的信息，以及如何在文章中进行引用。

3. 系统设计方法：
   - 登录界面的设计没有详细说明，包括界面样式、用户验证方式等。
   
   

# **愿景和范围文档**
## **1.业务需求**
### **1.1 背景**
近年来随着信息技术的进步，Blog（音译博客）也快速发展。为人们提供了一个自由、开放、互动的交流平台。博客不仅可以帮助个人实现自我表达和展示，也可以为企业、政府、媒体等机构提供一个有效的宣传和传播渠道。沟通方式比电子邮件、讨论群组以及BBS和论坛更展现个性，博客系统已经成为广大用户发表文章言论的主要工具，同时，博客也为网络营销、个人品牌建设、知识分享等方面提供了有力的支持。
### **1.2 业务机遇**
内容创作：博客本身就是以内容为核心的平台，因此，对于擅长写作的人来说，博客提供了一个很好的机会来展示自己的才华和技能。通过不断更新高质量、有价值的内容，博客可以吸引更多的读者，进而获得更多的关注和流量。

营销推广：博客可以作为一个宣传和推广产品或服务的平台，通过博客上的内容来吸引潜在客户的注意，提高品牌知名度和产品销售。

广告收入：博客也可以通过在内容中嵌入广告或推广合作，获得广告收入。例如，博主可以通过展示谷歌广告或加入广告联盟等方式来获得广告收入。

会员订阅：博主可以通过提供独家内容、优惠福利、专业服务等方式来吸引粉丝成为会员，从而获得稳定的收入。

品牌合作：博主可以通过与品牌进行合作，为品牌提供曝光和宣传，从而获得一定的收益。
### **1.3 业务目标**
提高网站流量：通过优化博客的SEO，定期发布高质量、有价值的内容，积极推广博客，吸引更多的访问者，提高网站流量。

提高用户留存率：通过提供个性化的用户体验，例如定期推送订阅邮件、社交媒体分享等方式，增强用户的参与感和忠诚度，提高用户留存率。

增加粉丝数量：通过各种社交媒体平台和其他渠道宣传博客，积极与读者互动，增加粉丝数量。可以通过提供独家内容、优惠福利等方式吸引更多的用户成为粉丝。

扩大品牌影响力：通过与其他博主、品牌进行合作，参与各种行业活动和社区活动，扩大博客的品牌影响力。

增加收益：通过各种方式如会员订阅、广告收入、品牌合作等，增加博客的收益。可以通过谷歌广告等广告平台、知名电商平台等方式，获取更多的收益。

### **1.4 成功指标**
在发布6个月之后，博客的流量达到每月数千或数万的访问量，且这些访问量是有价值的。

### **1.5 愿景陈述**
博客应具有积极的社会意义和价值，提供一个平台为读者提供有用的信息和知识，或者帮助读者解决实际问题等。也可以成为特定领域的权威博客，或者成为特定群体的首选博客等。博客的受众是博客的目标读者群体，博客的影响范围则是博客所影响的人群和领域。做到全国第一的博客

### **1.6业务风险**
博客的内容可能存在侵权、虚假宣传、违反社会公德等问题，导致法律风险和声誉风险。（概率=0.8；影响=4）

博客的流量可能受到搜索引擎算法变化、社交媒体政策调整等因素的影响，导致流量的急剧下降。（概率=0.4；影响=3）

博客所在的行业和领域可能存在激烈的竞争，其他博客可能通过价格战、品牌宣传等手段抢占市场份额。（概率=0.6；影响=5）

博客所处的政策环境可能发生变化，例如出台新的网络安全法规、版权法规等，导致博客需要承担额外的合规成本和责任。（概率=0.2；影响=2）

### **1.7 业务假设和依赖**
系统为用户们提供了个性化的用户界面，用户可以根据个性需求装扮界面。

服务器可以承受上千人的访问量，并且检测博客是否合规并上传的时间控制在30分钟以内。

## **2.范围和限制**
### **2.1主要特性**
发表，修改，取消或删除和查看已经发表的博客。

审核和删除发表的博客。

为经常访问的博客进行博客订阅，删除和取消。

授权员工管理员可通过企业内网，互联网，智能手机以及平板电脑访问系统。

可查阅博客的订阅数量

![](./src/%E5%8D%9A%E5%AE%A2%E7%B3%BB%E7%BB%9F%E7%9A%84%E5%B1%80%E9%83%A8%E7%89%B9%E6%80%A7%E6%A0%91.png)


## **3.业务上下文**

### **3.1干系人资料**
![](./src/%E5%B9%B2%E7%B3%BB%E4%BA%BA%E8%B5%84%E6%96%99.png)




### **3.2部署考虑**
需要为ios和安卓系统的智能手机和平板开发应用，相应的windows phone和windows 平板电脑在随后的发布中完成开发。需要制作一系列的长度短于5分支的视频，用于培训管理人员如何基于互联网和版本应用的。


# **用例**

**个人博客网站的主要操作者及用例**

|主要操作者|用例|
|---|---|
|游客|1.浏览文章<br>2.评论文章<br>3.下载附件|
|站主|1.登录<br>2.注销<br>3.发表文章<br>4.修改文章<br>5.删除文章<br>6.上传附件<br>7.删除附件|

-----------
## **用例图**

![](./src/用例图.svg)

---------
## **具体用例**

1. **发表文章**

    |用例名称|发表文章|
    |---|---|
    |参与者|站主|
    |前置条件|站主必须登录|
    |后置条件|文章发表成功|
    |主事件流|1.站主点击发表文章按钮<br>2.站主填写文章信息<br>3.系统保存文章信息<br>4.系统提示发表成功<br>|
    |备选事件流|3a.系统检测到文章信息有误<br>3a1.系统提示文章信息有误<br>3a2.系统返回文章填写页面<br>3a3.站主修改文章信息<br>3a4.系统保存文章信息<br>3a5.系统提示发表成功<br>|

2. **上传附件**

    |用例名称|上传附件|
    |---|---|
    |参与者|站主|
    |前置条件|站主必须登录|
    |后置条件|附件上传成功|
    |主事件流|1.站主点击上传附件按钮<br>2.站主选择附件<br>3.系统保存附件信息<br>4.系统提示上传成功<br>|
    |备选事件流|3a.系统检测到附件信息有误<br>3a1.系统提示附件信息有误<br>3a2.系统返回附件填写页面<br>3a3.站主修改附件信息<br>3a4.系统保存附件信息<br>3a5.系统提示上传成功<br>|

3. **发表评论**

    |用例名称|发表评论|
    |---|---|
    |参与者|游客|
    |前置条件|无|
    |后置条件|评论发表成功|
    |主事件流|1.游客点击发表评论按钮<br>2.游客填写评论信息<br>3.系统保存评论信息<br>4.系统提示发表成功<br>|
    |备选事件流|3a.系统检测到评论信息有误<br>3a1.系统提示评论信息有误<br>3a2.系统返回评论填写页面<br>3a3.游客修改评论信息<br>3a4.系统保存评论信息<br>3a5.系统提示发表成功<br>|


4. **发表留言**

    |用例名称|发表留言|
    |---|---|
    |参与者|游客|
    |前置条件|无|
    |后置条件|留言发表成功|
    |主事件流|1.游客点击发表留言按钮<br>2.游客填写留言信息<br>3.系统保存留言信息<br>4.系统提示发表成功<br>|
    |备选事件流|3a.系统检测到留言信息有误<br>3a1.系统提示留言信息有误<br>3a2.系统返回留言填写页面<br>3a3.游客修改留言信息<br>3a4.系统保存留言信息<br>3a5.系统提示发表成功<br>|

5. **登录**

    |用例名称|登录|
    |---|---|
    |参与者|站主|
    |前置条件|无|
    |后置条件|登录成功|
    |主事件流|1.站主点击登录按钮<br>2.站主填写登录信息<br>3.系统保存登录信息<br>4.系统提示登录成功<br>|
    |备选事件流|3a.系统检测到登录信息有误<br>3a1.系统提示登录信息有误<br>3a2.系统返回登录填写页面<br>3a3.站主修改登录信息<br>3a4.系统保存登录信息<br>3a5.系统提示登录成功<br>|

6. **注销**

    |用例名称|注销|
    |---|---|
    |参与者|站主|
    |前置条件|站主必须登录|
    |后置条件|注销成功|
    |主事件流|1.站主点击注销按钮<br>2.系统提示注销成功<br>|

7. **修改文章**

    |用例名称|修改文章|
    |---|---|
    |参与者|站主|
    |前置条件|站主必须登录|
    |后置条件|文章修改成功|
    |主事件流|1.站主点击修改文章按钮<br>2.站主修改文章信息<br>3.系统保存文章信息<br>4.系统提示修改成功<br>|
    |备选事件流|3a.系统检测到文章信息有误<br>3a1.系统提示文章信息有误<br>3a2.系统返回文章填写页面<br>3a3.站主修改文章信息<br>3a4.系统保存文章信息<br>3a5.系统提示修改成功<br>|

8. **删除文章**

    |用例名称|删除文章|
    |---|---|
    |参与者|站主|
    |前置条件|站主必须登录|
    |后置条件|文章删除成功|
    |主事件流|1.站主点击删除文章按钮<br>2.系统提示删除成功<br>|


|用例优先级|用例|
|---|---|
|高|1.发表文章<br>2.登录|
|中|1.上传附件<br>2.发表评论<br>3.发表留言<br>4.注销<br>5.修改文章<br>|
|低|1.删除文章|




------

# **软件需求规范**

## 1. **介绍**
    
### 1.1 **目的**


基于个人博客的特点，本系统实现个人博客的主要功能，包括博客系统的站主登录/退出，博客站主并发表文章、图片等，游客发表评论、分页浏览文章和下载文章附件等。博客系统主要区分了两类用户，分别为博客站主和普通游客。网站登录仅限于博客站主，博客站主可以登陆写下自己的文章与上传附件，登陆即拥有网站管理的权限，未登录时均以游客身份访问。游客主要的功能是分页、分类、分标签阅读博客站主文章和浏览图片，发表评论和留言。

### 1.2 **项目范围**

个人博客将提供一个网站给站主写博客，为游客提供阅读，下载附件，评论的功能
-------------------
## 2. **总述**

### 2.1 **产品视角**

个人博客

### 2.2 **用户类别及特征**

| 用户类别 | 描述 |
|   ---   | ---  |
| 游客 | 查看，转发，评论站主发布的文章 |
| 站主 | 添加，修改，删除文章，维护网站 |

### 2.3 **操作环境**

正常浏览器

### 2.4 **设计与实现约束**

- 使用html，css，js语言做前端，加上bootstrap框架
- 使用java语言做后端
- 使用mysql数据库

### 2.5 **假设与依赖**

- 站主的服务器有充足的容量存储数据
- 站主的服务器运行正常
-------------------
## 3. **系统特性**

### 3.1 **游客浏览，评价**

- 游客浏览会产生浏览记录，可以添加到数据库中

- 游客评价会添加到数据库中，游客可以使用临时名进行评价，并记录评价时间来排序

### 3.2 **站主文章管理，发表、修改、上传**

- 站主使用Markdown格式书写内容，保存在数据库中，网页访问时通过js获取api，并转换成html格式显示

- 可以对已有的内容进行修改

- 文章对图片和附件进行直接的引用，即图片和附件信息不通过数据库存储


### 3.3 **系统设计方法**

- 系统为博客网站站主提供专门的登录界面，不为浏览网站的用户提供登陆界面，亦不包括登陆后的管理界面

- 浏览用户仅有浏览网页、下载指定附件的功能，除评论功能外，不涉及对博客网站系统后台数据库表的修改

- 博客站主需输入密码方可登陆，登陆后可进行各种管理操作。博主的密码通过rsa256算法加密保存在服务器端，加强安全性

-------------------

## 4. **数据需求**

### 4.1 **ER图**

![](./src/er.jpg)

### 4.2 **数据流图**

![](./src/%E6%95%B0%E6%8D%AE%E6%B5%81%E5%9B%BE.jpg)


### 4.3 **数据库表**

*仅针对首次迭代进行数据库建模*

1. **站长信息表**

    |属性名|数据类型|约束条件|注释|
    |---|---|---|---|
    |id|int|主键|站长id|
    |name|varchar(20)|唯一|站长名|
    |password|password||站长密码|
    |email|varchar(30)||站长邮箱|
    |img|图片信息表.id|外键|站长头像|
    |description|varchar(100)||站长描述|
    
    

2. **文章信息表**

    |属性名|数据类型|约束条件|注释|
    |---|---|---|---|
    |id|int|主键|文章id|
    |title|varchar(100)||文章标题|
    |content|longtext||文章内容|
    |time|datetime||文章发表时间|
    |author|varchar(20)||文章作者|
    |type|varchar(10)||文章类型|
    |tag|varchar(20)||文章标签|
    
    
3. **评论信息表**

    |属性名|数据类型|约束条件|注释|
    |---|---|---|---|
    |id|int|主键|评论id|
    |name|varchar(20)||评论者名|
    |content|varchar(100)||评论内容|
    |time|datetime||评论时间|
    |article|文章信息表.id|外键|评论文章|

    
4. **附件信息表**

    |属性名|数据类型|约束条件|注释|
    |---|---|---|---|
    |id|int|主键|附件id|
    |name|varchar(20)||附件名|
    |content|longblob||附件内容|
    |time|datetime||附件上传时间|
        
### 4.4 **数据字典**

|数据元素|描述|组成方式或数据类型|长度|值|
|---|---|---|---|---|
|站长id|站长唯一标识|整数|20||
|站长名|站长唯一标识|字符串|20||
|站长密码|站长登陆密码|字符串|20||
|站长邮箱|站长邮箱|字符串|30||
|站长头像|站长头像|整数|20||
|站长描述|站长描述|字符串|100||
|文章id|文章唯一标识|整数|20||
|文章标题|文章标题|字符串|100||
|文章内容|文章内容|字符串|1000||
|文章发表时间|文章发表时间|时间|20||
|文章作者|文章作者|字符串|20||
|文章类型|文章类型|字符串|10||
|文章标签|文章标签|字符串|20||
|评论id|评论唯一标识|整数|20||
|评论者名|评论者名|字符串|20||
|评论内容|评论内容|字符串|100||
|评论时间|评论时间|时间|20||
|评论文章|评论文章|整数|20||
|附件id|附件唯一标识|整数|20||
|附件名|附件名|字符串|20||
|附件内容|附件内容|二进制|1000||
|附件上传时间|附件上传时间|时间|20||



-------------------
## 5. **外部接口需求**
    
### 5.1 **用户界面**

- 网站首页
- 文章列表页
- 文章详情页
- 图片列表页
- 图片详情页
- 附件列表页
- 附件详情页
- 留言页
- 评论页
- 登陆页
- 注册页
- 管理页

### 5.2 **软件接口**

- 上传附件
- 下载附件
- 上传图片
- 下载图片
- 上传文章
- 修改文章
- 删除文章
- 添加评论
- 删除评论
- 添加留言
- 删除留言
- 登陆
- 注册
- 修改密码
- 修改信息
- 退出

-------------------

## 6. **质量属性**
    
### 6.1 **易用性要求**

- 罗列博客的所有内容，可以按照文章属性排序
- 提供搜索功能

### 6.2. **性能要求**

- 尽可能快的响应

### 6.3 **防护要求**

- 保护站主密码
- 保护数据库
- 保护用户隐私
### 6.4 **安全要求**

- 防止xss攻击
- 防止sql注入
- 防止csrf攻击
- 防止暴力破解
### 6.5 **可用性要求**

- 保证网站的稳定性
- 保证网站的持续性
- 保证程序的可维护性
- 保证程序的可扩展性
- 保证程序的可移植性
### 6.6 **健壮性要求**


- 保证程序的容错性
- 保证程序的可恢复性
- 保证程序的可用性



