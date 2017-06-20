---
title: Alfred-iTerm2
date: 2016-12-16 11:36:27
tags:
  - mac
  - Alfred
  - iTerm2
---
# Alfred 中将iTerm2 设置成默认的terminal
* 打开`Alfred Preferences`  - `Features` - `Terminal / Shell`
* 更改`Application`为`Customer`
* 替换成以下代码:

```shell
on alfred_script(q)
tell application "System Events"
    tell application "iTerm2"
        create window with default profile
        delay 0.5
        tell current session of current window
            write text q
        end tell
    end tell
end tell

end alfred_script
```

👌

[参考]('https://github.com/tridays/alfred-iterm2')
