# leetcodeRemark
記錄一下覺得需要複習的leetcode題目

- [94][M] Binary Tree Inorder Traversal
這一題是要求從一個二元樹轉成Inorder Traversal
思考方式：
優先順序為 `左 > 父 > 右` 所以判斷上會變成
```
if 左空 {
    移除現在點
    將值放入結果
} else {
    把現在點加入堆疊
    清除現在點的左邊
}
if 右不為空 {
    把現在點加入堆疊
    清除現在點的右邊
}
```

- [279][M] Perfect Squares
