# 空间数据类型和模型

> 原文:[https://www . geesforgeks . org/spatial-data-type-and-models/](https://www.geeksforgeeks.org/spatial-data-types-and-models/)

**空间数据**是通过城镇、城市、岛屿等实际生活地点收集的数据。空间数据基本上有三种不同的类型，并被明智地用于商业部门:

1.  **地图数据:**
    地图数据包括地图中对象的不同类型的空间特征，例如——对象的形状和对象在地图中的位置。要素的三种基本类型是点、线和面(或区域)。
    *   **点–**
        点用于表示对象的空间特征，这些对象的位置对应于特定应用比例中的单一二维坐标(x、y 或经度/纬度)。例如:建筑物、蜂窝塔或固定车辆。移动的车辆和其他移动的物体可以用随时间变化的点位置序列来表示。
    *   **线–**
        线表示具有长度的对象，例如道路或河流，其空间特征可以通过连接的线的序列来近似。

*   **多边形–**
    多边形用于表示有边界的对象的特征，如州、湖泊或国家。*   **属性数据:**
    **是地理信息系统 与地图中要素关联的描述性数据。例如，在代表印度一个邦内的国家的地图中(例如:奥迪沙或孟买)。
    属性-人口、最大城市/城镇、平方英里面积等。***   ****Image data :**
    Itincludes camera created data like satellite images and aerial photographs. Objects of interest, such as buildings and roads, can be identified and overlaid on these images. Aerial and satellite images are typical examples of *raster data*.

    **空间信息模型:**
    它分为两类:

    *   **字段:**
        这些模型用于模拟自然界中连续的空间数据，例如地形高程、空气质量指数、温度数据和土壤变化特征。
    *   **Object :**
        Thesemodels have been used for applications such as transportation networks, land parcels, buildings, and other objects that possess both spatial and non-spatial attributes.

        空间应用使用**场**或基于**对象**的模型来建模，这取决于应用的需求和模型的传统选择。示例–高流量分析系统等。**