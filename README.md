gulp-multi-tabs
================

> 替换多个tab


## Install
```
npm install gulp-multi-tabs --save-dev
```

## Example

### a.html
```html
<!DOCTYPE>
<html>
<head>
</head>
<body>
	<header>
		<inline src="b.html" tab=[1:class="selected"] />
	</header>
</body>
</html>
```

### b.html
```html
    <div class="header">
        <div class="header-top">
            <div class="header-nav">
                <ul id="headerNav">
                    <li <!--tab:1-->><a href="/1.html">tab1</a></li>
                    <li <!--tab:2-->><a href="/2.html">tab2</a></li>
                    <li <!--tab:3-->><a href="/3.html">tab3</a></li>
                    <li <!--tab:4-->><a href="/4.html">tab4</a></li>                                  
                    <li <!--tab:5-->><a href="/5.html">tab5</a></li>
                </ul>
            </div>
        </div>
    </div>
```

### dist/a.html
```html
<!DOCTYPE>
<html>
<head>
</head>
<body>
	<header>
	    <div class="header">
		<div class="header-top">
		    <div class="header-nav">
			<ul id="headerNav">
			    <li class="selected"><a href="/1.html">tab1</a></li>
			    <li><a href="/2.html">tab2</a></li>
			    <li><a href="/3.html">tab3</a></li>
			    <li><a href="/4.html">tab4</a></li>                                  
			    <li><a href="/5.html">tab5</a></li>
			</ul>
		    </div>
		</div>
	    </div>
	</header>
</body>
</html>
```

### `gulpfile.js`
```javascript
var gulp = require('gulp');
var inline = require('gulp-multi-tabs');


gulp.src('./src')
	.pipe(replace('%TimeStamp%',new Date().getTime()))
	.pipe(inline('./src/'))
	.pipe(gulp.dest('./dist'));
```