## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/dcbenwu/doc/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block
# oom killer理解和日志分析:知识储备
Link[Link](https://www.jianshu.com/p/ba1cdf92a602) 
# Linux 下进程消失的原因分析
## 命令参考
dmesg | egrep -i -B100 'killed process'

## 或:
egrep -i 'killed process' /var/log/messages
egrep -i -r 'killed process' /var/log

## 或:
journalctl -xb | egrep -i 'killed process'
--------------------- 
# 一个查询决策的方法
[root@cnsh2ucats978 cats]# cat oomscore.sh
#!/bin/bash
for proc in $(find /proc -maxdepth 1 -regex '/proc/[0-9]+'); do
    printf "%2d %5d %s\n" \
        "$(cat $proc/oom_score)" \
        "$(basename $proc)" \
        "$(cat $proc/cmdline | tr '\0' ' ' | head -c 50)"
done 2>/dev/null | sort -nr | head -n 10

### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dcbenwu/doc/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
