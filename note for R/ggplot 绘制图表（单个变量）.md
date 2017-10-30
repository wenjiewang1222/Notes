##ggplot（单个变量）

**library(ggplot2)**  
加载ggplot2  
**qplot(x = age, data = pf)**  
创建数据来自“pf”，以“age”为x轴的直方图。  
**facet_wrap(~variable)**  
为每个类别的变量级别创建直方图,传递一个变量  
**facet_grid(vertical~horizontal)**  
传递两个及多个变量  
**qplot(x = age, data = pf, xlim = c(0, 110))**   
**=qplot(x = age, data = pf) +**  
      **scale_x_continuous(limits = c(0, 110))**  
限制X轴起点和终点的矢量  
**qplot(x = age, data = pf, binwidth = 1) +**  
**scale_x_continuous(limits = c(0, 110), breaks = seq(0, 110, 5)**  
调整组宽和组距  
**qplot(x = age, data = subset(pf, !is.na(gender)), binwidth = 1) +**  
**scale_x_continuous(limits = c(0, 110), breaks = seq(0, 110, 5) +**  
**facet_wrap(~gender)**  
以忽略性别为NA的子集创建以性别划分的年龄直方图  
**table(pf$gender)**  
**by(pf$friend_count, pf$gender，summary)**  
创建性别的子集列表，按性别划分计算朋友数量的所有计数统计  
**qplot(x = age, data = pf,**  
**xlab = "the age of people using facebook",**  
**ylab = "Number of users in sample,**  
**color = I('black'), fill = I('#F79420'))**  
修改x轴标签和y轴标签，修改颜色  
###转换数据  
**log10(pf$friend_count)**  
**sqrt(pf$friend_count)**  
有些时候数据是过度离散的，可以通过取对数或者平方根等将数据转换，使其可能变成正太分布。  
或者非常接近正太分布。  
###创建频率多边形  
**qplot(x = age, data = subset(pf, !is.na(gender)), binwidth = 1，geom = 'freqpoly', color = gender) +**  
**scale_x_continuous(limits = c(0, 110), breaks = seq(0, 110, 5) +**  
###创建箱线图  
**qplot(x = gender, y = friend_count, data = subset(pf, !is.na(gender)), geom = 'boxplot') +**  
**coor_cartesian(ylim = c(0,250))**  
限制y轴的范围，但并不改变统计计数的值  
###符合逻辑  
mobile_check_in <- NA  #将表格中为NA的值赋值给mobile_check_in  
pf$mobile_check_in <- ifelse(pf$mobile_likes > 0, 1, 0)
如果pf$mobile_likes > 0则 pf$mobile_check_in = 1，反之等于0
pf$mobile_check_in <- factor(pf$mobile_check_in)
将因子变量转换成因素变量