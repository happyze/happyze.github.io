---
layout: post
title: 使用gulp-imagemin压缩图片
description: gulp-imagemin压缩图片还是很方便的,这里建议开发者都能熟练的掌握
category: coding
---

### 使用 imagemin 来压缩图片  

装包    

需要安装三个包，一个是 `gulp` `gulp-imagemin` ，另一个是 `imagemin-pngquant` 。  

```
cnpm i -D  gulp gulp-imagemin imagemin-pngquant
```

gulpfile.js 内容  

```
var gulp = require("gulp")
var imagemin = require('gulp-imagemin');
var pngquant = require('imagemin-pngquant');

gulp.task('imagemin', function(){
  return gulp.src('src/images/*')
    .pipe(imagemin({
      progressive: true,
      svgoPlugins: [{removeViewBox: false}],
      use: [pngquant()]
    }))
    .pipe(gulp.dest('dist/images'));
});
```  

##### 注:  

gulpfile.js 内容其实重点是要搞明白两句  
1. `return gulp.src('src/images/*')` 输入文件的地方也就是src下的images文件里面的某张图片 。 
2. `.pipe(gulp.dest('dist/images'))` 输出的文件的地方dist下的images文件夹里面 。
