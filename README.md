# octopus-merge
## これはなに？
gitで、3つ以上のbranchを同時にmergeしたらどうなるかを試したリポジトリです。

merge commitは [151557d](https://github.com/haruelico/octopus-merge/commit/151557d) です。

## つくりかた
```shell
$ mkdir octopus-merge
$ cd octopus-merge
$ git init
$ git commit --allow-empty -m "Initial commit"

# feature1
$ git checkout -b feature1
$ echo feature1 > feature1.txt
$ git add feature1.txt
$ git commit -m "Create feature1.txt"
$ git checkout master

# feature2
$ git checkout -b feature2
$ echo feature2 > feature2.txt
$ git add feature2.txt
$ git commit -m "Create feature2.txt"
$ git checkout master

# feature3
$ git checkout -b feature3
$ echo feature3 > feature3.txt
$ git add feature3.txt
$ git commit -m "Create feature3.txt"
$ git checkout master

# merge
$ git merge --no-ff --strategy=octopus feature1 feature2 feature3
```

## 参考URL
[Git - merge-strategies Documentation](https://git-scm.com/docs/merge-strategies#Documentation/merge-strategies.txt-octopus)