# leetcodeRemark
記錄一下覺得需要複習的leetcode題目

- [279][M] Perfect Squares
第一眼看到完全沒想法，基本上應該是可以用暴力法去拆解，先對送入的函數找到最接近的平方根。
然後用逐一嘗試的方法解決，但是用想的就覺得效率很差

查詢了一下，這題是考到一個觀念`四平方合定理`，完全沒聽過...
今天先跳過...

- [78][M] Subsets
這一題是要找出陣列的所有的子集合，想法可以直接一點
就是逐步的把每個組合加進去就好，在裡面的迴圈先加入現在的數字，然後再疊加之前已經存在的陣列，透過這個邏輯就能在雙層回圈內完成。
```swift
for num in nums {
    for arr in result {
        var newArr = [num]
        newArr.append(contentsOf: arr)
        result.append(newArr)
    }
}
```

- [230][M] Kth Smallest Element in a BST
首先這題是BST，二元樹
所以根據樹的特性，左邊節點一定小於父節點，右邊則反之。
所以目前只要進行訪問樹
要找到第K個大的樹就要進行Inorder的訪問方式只要找到地K個位置直接回傳即可

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
