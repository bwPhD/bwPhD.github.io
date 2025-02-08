---
layout: page
---

### 个人简介

**汪斌**，东南大学社会学系讲师，硕士生导师。北京大学博士(PhD)。
在老年学顶级期刊 **Journal of Gerontology: Social Science** 及《人口研究》、《人口与发展》等SSCI和CSSCI来源刊物发表**20**余篇论文。论文总下载量**6w+**，总引用**900+次**，H指数14，G指数21。**7次**被《新华文摘》、《高等学校文科学术文摘》、《人大复印报刊资料（人口学）》摘编或全文转载。2024年1篇政策建言被**全国政协**采纳，目前主持国家社会科学基金项目（24CRK006）和江苏省社会科学基金项目（24SHC007）。

---

### 电子邮箱：

wangbinwork@seu.edu.cn

---

### 研究兴趣

- 老年社会学
- 人口社会学
- 数字社会学

---

### 社会兼职

中国老年学和老年医学学会青年委员会理事

---

### 社会服务

人口与发展(C刊) 、社会建设(C扩) 、Plos One（SCI）审稿专家

---

<!-- 加载页面  提取内容 -->
<div id="dynamic-content">
  <p>正在加载内容...</p>
</div>

<script>
  // 需要加载的页面列表（采用绝对 URL）
  const pages = [
    "https://bwphd.github.io/publications/",
    "https://bwphd.github.io/awards/",
    "https://bwphd.github.io/teach/",
    "https://bwphd.github.io/blogs/"
  ];

  async function loadContent() {
    const contentDiv = document.getElementById("dynamic-content");
    let aggregateHTML = ""; // 用于聚合所有页面内容

    // 依次加载各页面（顺序加载，确保内容排列有序）
    for (const page of pages) {
      try {
        const response = await fetch(page);
        // 检查 HTTP 响应状态
        if (!response.ok) {
          throw new Error(`HTTP 错误：${response.status}`);
        }
        const text = await response.text();

        // 创建临时容器提取 <body> 内部的 HTML 内容
        const tempDiv = document.createElement("div");
        tempDiv.innerHTML = text;
        const bodyContent = tempDiv.querySelector("body");

        if (bodyContent) {
          aggregateHTML += bodyContent.innerHTML;
        } else {
          aggregateHTML += `<p>无法加载 ${page}</p>`;
        }
      } catch (error) {
        aggregateHTML += `<p>加载 ${page} 失败</p>`;
      }
    }
    // 一次性更新 DOM，避免多次重绘
    contentDiv.innerHTML = aggregateHTML;
  }

  // 页面加载完成后自动调用加载函数
  window.addEventListener("load", loadContent);
</script>
