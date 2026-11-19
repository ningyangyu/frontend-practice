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

第十五课 媒体查询
媒体查询能根据屏幕宽度切换CSS
基本格式为
@media (max-width: 600px) {
  /* 屏幕宽度不超过 600px 时生效 */
}
在窄屏幕下，让页眉由横向排列改为纵向排列
@media (max-width: 600px) {
  header {
    flex-direction: column;
  }

  .skill-item {
    flex-basis: 100%;
  }
}
当屏幕宽度小于600px时，页眉改成纵向排列，技能卡片各占满一行，达到的效果很形象，在手机上打开和电脑上打开很明显，虽然好像在用媒体查询之前就是这样

第十六课 box-sizing: border-box
在普通的盒模型
box-sizing：content-box；
元素宽度只包含内容，不包含padding和border
假设main {
  width: 100%;
  padding: 20px;
  border: 2px solid blue;
}
实际总宽度时100%内容宽度+左右padding各20px+左右border各2px
容器占满屏幕后，再额外增加padding和border就可能超出课件区域造成页面横向溢出
使用border-box
* {
  box-sizing: border-box;
}
width包含内容、padding和border，总宽度仍是100%
加在*上表示对页面所有元素起效，使用统一的宽度计算方式
在视觉上不会产生明显的变化，实际上网页会变得略微紧凑，因为padding、border和可用宽度都被合并到盒子内部，不会再额外让页面总宽度明显增大
