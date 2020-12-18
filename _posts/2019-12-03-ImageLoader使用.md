---
layout:     post
title:      ImageLoader使用
subtitle:   Android开发
date:       2019-12-02
author:     JackyCJ
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Android
    - ImageLoader

---

# ImageLoader使用


```
//初始化
Context context = getContext();
File cacheDir = StorageUtils.getOwnCacheDirectory(getContext(), "imageloader/Cache");
ImageLoaderConfiguration config = new ImageLoaderConfiguration
        .Builder(context)
        .memoryCacheExtraOptions(480,800)
        .threadPoolSize(3)
        .threadPriority(Thread.NORM_PRIORITY - 2)
        .denyCacheImageMultipleSizesInMemory()
        .memoryCache(new UsingFreqLimitedMemoryCache(2*1024*1024))
        .memoryCacheSize(2*1024*1024)
        .discCacheSize(50*1024*1024)
        .discCacheFileNameGenerator(new Md5FileNameGenerator())
        .tasksProcessingOrder(QueueProcessingType.LIFO)
        .discCacheFileCount(100)
        .discCache(new UnlimitedDiskCache(cacheDir))
        .defaultDisplayImageOptions(DisplayImageOptions.createSimple())
        .imageDownloader(new BaseImageDownloader(context, 5*1000, 30*1000))
        .writeDebugLogs()
        .build();

ImageLoader.getInstance().init(config);
//图片来自于网络
String imageUrl = "https://pic4.zhimg.com/80/v2-9e8f6759bb2ad740ef172d438ed8e8f5_hd.jpg";
ImageLoader.getInstance().displayImage(imageUrl, mImageView);
/*ImageLoader.getInstance().displayImage(imageUrl, mImageView, getSimpleOptions(), new SimpleImageLoadingListener(), new ImageLoadingProgressListener() {
    @Override
    public void onProgressUpdate(String imageUri, View view,
                                 int current, int total) {
        double progress = ((double)current/total)*100;
        System.out.println(progress+"%");
        //progressTv.setText("当前进度是：" + progress+"%");
    }
});
//清除缓存
//ImageLoader.getInstance().clearDiskCache();
//ImageLoader.getInstance().clearMemoryCache();
*/
```

# 参考文档
+ [Android-Universal-Image-Loader 图片异步加载类库的使用（超详细配置）](https://blog.csdn.net/vipzjyno1/article/details/23206387)
+ 