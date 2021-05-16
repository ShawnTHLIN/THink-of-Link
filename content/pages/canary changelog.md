---
title: Canary Changelog
---

* [[Apr 30th, 2021]]
Canary Version 0.0.1
Desktop app download link:
https://github.com/logseq/logseq/releases/tag/0.0.1

Logseq Canary is for early adopters and developers to test new features and APIs without affecting the stable working environment. It will be installed as a separate app besides the stable one.
    * This is the first canary release, introducing the big refactoring of Logseq. The rationale behind the refactoring is detailed here [[The Refactoring Of Logseq]] . Overall, it makes the code simpler and more robust, fixes some long-standing issues along the way and paves the way for upcoming features.
    * [[Enhancement]]
        * A refactored core that is simpler and more robust.
        * A much better undo/redo experience.
        * Better keyboard navigation:
            * [](https://user-images.githubusercontent.com/45989292/116767907-a44f2080-aa65-11eb-9cc3-e2ed34e4b6aa.gif)
            * We've made most of above shortcuts customizable as well. If you don't like arrow keys, you can change it. Also for navigation keys in auto-completion, search, and more.

To add custom shortcuts, you can add/modify the `:shortcuts` section in config.edn like before, but now you can also add multiple bindings for one shortcut, for example here's my personal vim like bindings:
    :shortcuts
    
    {:editor/new-block "enter"
    
    :editor/new-line "shift+enter"
    
    :editor/insert-link "ctrl+shift+k"
    
    :editor/up ["ctrl+k" "up"]
    
    :editor/down ["ctrl+j" "down"]
    
    :editor/left ["ctrl+h" "left"]
    
    :editor/right ["ctrl+l" "right"]
    
    :editor/open-edit ["i" "enter"]
    
    :editor/backspace ["ctrl+d" "backspace"]
    
    
    :date-picker/complete ["enter"]
    
    :date-picker/prev-day ["ctrl+h" "left"]
    
    :date-picker/next-day ["ctrl+l" "right"]
    
    :date-picker/prev-week ["ctrl+k" "up"]
    
    :date-picker/next-week ["ctrl+j" "down"]
    
    
    :auto-complete/prev ["ctrl+k" "up"]
    
    :auto-complete/next ["ctrl+j" "down"]
    
    :auto-complete/complete ["ctrl+l" "enter"]}
    
The full list of shortcut bindings for canary version is here:
https://github.com/logseq/logseq/blob/feat/outliner-core/src/main/frontend/modules/shortcut/binding.cljc

        * Markdown improvements:
            * The grammar of properties changes as below while staying the same in Org mode:
> title
property-1:: value-1
property-2:: value-2
body
            * Support unordered list as headings
            * Support headings as top-level blocks, with convenient /h1 ~ /h6 commands