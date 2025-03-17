本项目是提供直接可用的 release 文件：kuroshiro v1.1.2 和 kuroshiro-analyzer-kuromoji v1.1.0

原始项目：https://github.com/hexenq/kuroshiro

示例
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>日文假名标注工具</title>
    <script src="kuroshiro.js"></script>
    <script src="kuroshiro-analyzer-kuromoji.js"></script>
</head>
<body>
<div id="res"></div>
 
<script>
    const res = document.getElementById('res');
    const kuroshiro = new Kuroshiro();
 
    kuroshiro.init(new KuromojiAnalyzer()).then((result) => {
        kuroshiro.convert("教室に学生がいる", {
            mode: 'furigana',
            to: "hiragana"
        }).then((result) => {
            res.innerHTML = result;
        })
    })
</script>
</body>
</html>
```

结果
```
<ruby>教室<rp>(</rp><rt>きょうしつ</rt><rp>)</rp></ruby>に<ruby>学生<rp>(</rp><rt>がくせい</rt><rp>)</rp></ruby>がいる
```
