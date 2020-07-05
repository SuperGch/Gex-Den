# Mapbox使用文档


# MapBox的使用文档

- `lng` *[必需]* (**第一个**位置参数):

    地图初始中心点的经度, 以度为单位.

- `lat` *[必须]*（**第二个**参数位置）: 

    地图初始中心点的纬度, 以度为单位.

- `zoom` *[可选]*（**第三个**位置参数）:

    地图的初始缩放级别, 默认值是 `10`.

- `marked` *[可选]* (**第四个**位置参数): 

    是否在地图的初始中心点添加图钉, 默认值是 `true`.

- `light-style` *[可选]* (**第五个**位置参数):

    浅色主题的地图样式, 默认值是`config.toml`中配置的值.

- `dark-style` *[可选]*（**第六个**位置参数）:

    深色主题的地图样式，默认值是`config.toml`中配置的值.

- `navigation` *[可选]*:

    是否添加 `NavigationControl`, 默认值是`config.toml`中配置的值.

- `geolocate` *[可选]*:

    是否添加`GeolocateControl`, 默认值是`config.toml`中配置的值.

- `scale` *[可选]*: 

    是否添加`ScaleControl`, 默认值是`config.toml`中配置的值.

- `fullscreen` *[可选]*: 

    是否添加` FullscreenControl`, 默认值是`config.toml`中配置的值.

- `width` *[可选]*: 

    地图的宽度, 默认值是 `100%`.

- `height` *[可选]*: 

    地图的高度, 默认值是 `20rem`.

```markdown
{{</* mapbox 111.003 35.022 12 */>}}
或者
{{</* mapbox lng=111.003 lat=35.022 zoom=12 */>}}
```

{{< mapbox 111.003 35.022 12 >}}
或者
{{< mapbox lng=111.003 lat=35.022 zoom=12 marked=false >}}


可以通过如下方式自定义地图样式：

```markdown
{{</* mapbox 121.554 31.292 10 false "mapbox://styles/mapbox/streets-zh-v1" */>}}
或者
{{</* mapbox lng=121.554 lat=31.292 zoom=10 marked=false light-style="mapbox://styles/mapbox/streets-zh-v1" */>}}
```

{{< mapbox lng=121.554 lat=31.292 zoom=15 light-style="mapbox://styles/mapbox/streets-zh-v1" >}}
