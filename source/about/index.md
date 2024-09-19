# 关于我

!!:broken_heart:只是一个普普通通的大二小白罢了。自己随手写点博客，就当梳理学过的知识点了。!!{.bulr}

# 我的Github贡献图表

![Github记录](https://ghchart.rshah.org/StarlingLin)

# 我的文章统计图表

:::info
由于pjax加载问题，可能看不到统计图表，请刷新页面重试。
:::

{% raw %}
<script src="https://cdn.jsdelivr.net/npm/echarts@5.2.2/dist/echarts.min.js"></script>
<script>
function switchPostChart () {
  // 这里为了统一颜色选取的是 “明暗模式” 下的两种字体颜色，也可以自己定义
  let color = document.documentElement.getAttribute('data-theme') === null ? '#fff' : '#000'

  if (document.getElementById('posts-calendar')) {
    let postsCalendarNew = postsCalendarOption
    postsCalendarNew.textStyle.color = color
    postsCalendarNew.title.textStyle.color = color
    postsCalendarNew.visualMap.textStyle.color = color
    postsCalendarNew.calendar.itemStyle.color = color
    postsCalendarNew.calendar.yearLabel.color = color
    postsCalendarNew.calendar.monthLabel.color = color
    postsCalendarNew.calendar.dayLabel.color = color
    postsCalendar.setOption(postsCalendarNew)
  }
  if (document.getElementById('posts-chart')) {
    let postsOptionNew = postsOption
    postsOptionNew.textStyle.color = color
    postsOptionNew.title.textStyle.color = color
    postsOptionNew.xAxis.axisLine.lineStyle.color = color
    postsOptionNew.yAxis.axisLine.lineStyle.color = color
    postsChart.setOption(postsOptionNew)
  }
  if (document.getElementById('tags-chart')) {
    let tagsOptionNew = tagsOption
    tagsOptionNew.textStyle.color = color
    tagsOptionNew.title.textStyle.color = color
    tagsOptionNew.xAxis.axisLine.lineStyle.color = color
    tagsOptionNew.yAxis.axisLine.lineStyle.color = color
    tagsChart.setOption(tagsOptionNew)
  }
  if (document.getElementById('categories-chart')) {
    let categoriesOptionNew = categoriesOption
    categoriesOptionNew.textStyle.color = color
    categoriesOptionNew.title.textStyle.color = color
    categoriesOptionNew.legend.textStyle.color = color
    categoriesChart.setOption(categoriesOptionNew)
  }
}

document.getElementsByClassName("theme")[0].addEventListener("click", function () { setTimeout(switchPostChart, 100) })
</script>
<!-- 文章发布日历 -->
<div id="posts-calendar" style="border-radius: 8px; height: 300px; padding: 10px;"></div>
<!-- 文章发布时间统计图 -->
<div id="posts-chart" style="border-radius: 8px; height: 300px; padding: 10px;"></div>
<!-- 文章标签统计图 -->
<div id="tags-chart" data-length="10" style="border-radius: 8px; height: 300px; padding: 10px;"></div>
<!-- 文章分类统计图 -->
<div id="categories-chart"  style="border-radius: 8px; height: 300px; padding: 10px;"></div>
{% endraw %}