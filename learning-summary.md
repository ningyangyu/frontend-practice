这是一个可以记录每天学习结果的文件
第十三课，学习justufy-content：center和align-items：center的区别
区别其实在前几节课就说过了，justify-content:center是设置主轴方向上的排列，而align-items：conter是设置交叉轴方向上的排列，由于我们使用flex-direction：row将主轴设置为水平，虽然默认就是水平，所以效果会显示原本分在两端的两元素凑在了一起
第十四课 Flexbox技能卡片布局
首先我们在技能区h2和表格table之间加入
<div class="skill-list">
  <div class="skill-card">Git</div>
  <div class="skill-card">HTML</div>
  <div class="skill-card">CSS</div>
</div>
在这里<div>是卡片容器，表示建立一个容器用来管理三个技能卡片
<div>本身知识一个没有默认含义的区块标签，是否像卡片，由CSS决定
我们创建了list和item，现在来设置他们的属性，在CSS里先输入
.skill-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
这是用来设置list属性，可以知道首先将list里的元素纳入Flexbox里，设置为允许换行，项目横向间距设为20px
如果宽度不够，比如在手机上打开网页，就会有
flex-wrap：wrap；允许换行

.skill-card {
  flex: 1;
  min-width: 150px;
  padding: 20px;
  border: 1px solid #999;
  background-color: white;
  text-align: center;
}
首先flex：1；让三个卡片均分剩余宽度
min-width：150px；每个项目至少150px
padding：20px；元素边框内部与内容之间的距离为20px；
border：1px soild #999；宽度为1px的某颜色的实线
background-color: white;背景色设为白色
text-align: center;控制元素内部文字的横向对其方式为居中，这里的align与Flexbox的align-items无关



