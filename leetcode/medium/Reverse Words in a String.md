# Reverse Words in a String

## 📋 題目資訊

- **題目名稱: Reverse Words in a String**
- **題目連結**: [Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/description/?envType=study-plan-v2&envId=leetcode-75)
- **難度**: medium
- **解題日期**: 2024-06-27
- **解題時間**: 15 分鐘
- **程式語言**: JavaScript

## 🎯 題目描述

## 💡 解題思路

1. **第一步**: split字串成陣列 並filter掉空白的字元(’’)
2. **第二步**: two pointer反轉陣列
3. **第三步**: Array.join()轉換回字串並填空白

## ⏱️ 複雜度分析

- O(n)

## 💻 程式碼實現

### 解法：Math.max()+for loop

```jsx
/**
 * @param {string} s
 * @return {string}
 */
var reverseWords = function(s) {
    let arr=s.split(' ');
    arr=arr.filter(item=>item!='');
    let i=0;
    let j=arr.length-1;
    while(i<j){
        if(arr[i]!='' && arr[j]!=''){
            let temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
            i++;
            j--;
        }else if(arr[i]!=''){
            j--
        }else{
            i++
            j--
        }
    }
    return arr.join(' ');
};
```

## 📚 學習心得

- **學到的新概念**:這次很棒 語法基本上都記得記得怎麼寫
- **使用語法**: String.split()、 Array.filter()、Array.join()
- **使用演算法: Two Pointer**

## 📖 參考資料

## 🏷️ 標籤

- Array
- two pointer