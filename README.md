# 前言

欢迎来到基于SSM的协同过滤书城系统项目！该项目是一个基于Java语言和Spring、Springmvc、Mybatis框架开发的书籍推荐系统。通过协同过滤算法，为用户提供个性化的书籍推荐。以下是项目的详细介绍。

## 内容介绍

基于SSM的协同过滤书城系统旨在为用户提供一个便捷、智能的购书平台。系统主要包括用户模块、书籍模块、推荐模块等。用户可以在系统中浏览、搜索书籍，查看书籍详情，同时，系统会根据用户的阅读历史和喜好，为用户推荐合适的书籍。此外，系统还提供了管理员后台，方便对书籍和用户信息进行管理。

## 技术介绍

- 语言：Java
- 使用框架：Spring、Springmvc、Mybatis
- 前端技术：JS、Vue、css3
- 开发工具：IDEA/Eclipse
- 数据库：MySQL 5.7/8.0
- 数据库管理工具：phpstudy/Navicat
- JDK版本：jdk1.8
- Maven: apache-maven 3.8.1-bin
- 前端环境：Node.Js 12\14\16

## 核心代码

以下是项目中协同过滤算法的一个简单示例：

```java
// 获取用户相似度
public double getUserSimilarity(int userId1, int userId2) {
    // 获取用户评分列表
    List<Rating> ratings1 = ratingService.getUserRatings(userId1);
    List<Rating> ratings2 = ratingService.getUserRatings(userId2);

    // 计算共同评分的书籍数量
    int common = 0;
    for (Rating rating1 : ratings1) {
        for (Rating rating2 : ratings2) {
            if (rating1.getBookId() == rating2.getBookId()) {
                common++;
                break;
            }
        }
    }

    // 如果没有共同评分的书籍，返回0
    if (common == 0) {
        return 0;
    }

    // 计算皮尔逊相关系数
    double sum1 = 0;
    double sum2 = 0;
    double sum1Sq = 0;
    double sum2Sq = 0;
    double pSum = 0;

    for (Rating rating1 : ratings1) {
        for (Rating rating2 : ratings2) {
            if (rating1.getBookId() == rating2.getBookId()) {
                double x = rating1.getRating();
                double y = rating2.getRating();

                sum1 += x;
                sum2 += y;
                sum1Sq += x * x;
                sum2Sq += y * y;
                pSum += x * y;
                break;
            }
        }
    }

    double num = pSum - (sum1 * sum2 / common);
    double den = Math.sqrt((sum1Sq - sum1 * sum1 / common) * (sum2Sq - sum2 * sum2 / common));

    if (den == 0) {
        return 0;
    }

    return num / den;
}
```

## 免费源码获取

```
5000套系统成品在线演示视频，复制到流浪器： 
```
```
https://www.yuque.com/yuqueyonghux32e1j/kxdc9g/ad8oz3bamkxmay0e#Cxun
```
![下载](https://img12.360buyimg.com/ddimg/jfs/t1/339687/11/1349/28408/68ad865fF412d7877/adaa650483a100f2.jpg)

## 项目截图

![封面图片](https://img11.360buyimg.com/ddimg/jfs/t1/348659/4/312/110394/68bbd31aF3a83ecfc/cd7254e0add10d1d.jpg)

![介绍图片](https://img12.360buyimg.com/ddimg/jfs/t1/339918/6/7699/10713/68bbd2f3Faba19b81/2aa75313647ccb7c.jpg)

![介绍图片](https://img12.360buyimg.com/ddimg/jfs/t1/344703/27/282/46981/68bbd2f4F6dd96201/5e52264526ca5a39.jpg)

![介绍图片](https://img13.360buyimg.com/ddimg/jfs/t1/340139/3/7712/42005/68bbd2f8F4960a58d/85abf1c84c41f8ed.jpg)

![介绍图片](https://img14.360buyimg.com/ddimg/jfs/t1/343343/19/328/95331/68bbd2fbFb035b2ae/19967618be6cd6eb.jpg)

![介绍图片](https://img13.360buyimg.com/ddimg/jfs/t1/334815/6/10192/45040/68bbd2fcF314f1881/28f5898708f2c703.jpg)

![介绍图片](https://img13.360buyimg.com/ddimg/jfs/t1/336533/15/7511/26439/68bbd2feF5a44cae6/06ec2f4f3ab598a8.jpg)

![介绍图片](https://img10.360buyimg.com/ddimg/jfs/t1/337873/27/7701/36801/68bbd2feF458e3942/9a748c720933a08c.jpg)

![介绍图片](https://img12.360buyimg.com/ddimg/jfs/t1/333233/27/10229/29449/68bbd2feFbaaee1e4/bd0daf012ee6ae00.jpg)

![介绍图片](https://img14.360buyimg.com/ddimg/jfs/t1/347390/14/315/29750/68bbd2ffF81e1f5ef/dfda95d2a9b07c87.jpg)

