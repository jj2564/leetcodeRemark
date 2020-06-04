# leetcodeRemark
記錄一下覺得需要複習的leetcode題目

- [144][M] Binary Tree Preorder Traversal
跟94類似，優先順序為 `中 > 左 > 右` 
所以想法要稍微改變
在訪問子節點的同時就直接將value加入結果
檢查發現左右都無子的時候將該點移出堆疊
先前照指前面的想法一直在迴圈內加所以會重複加入

- [94][M] Binary Tree Inorder Traversal
這一題是要求從一個二元樹轉成Inorder Traversal
可以用recusive, 這採用迴圈來解
思考方式：
優先順序為 `左 > 中 > 右` 所以判斷上會變成
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
