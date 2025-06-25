## [Kids With the Greatest Number of Candies](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/)

## 📋 題目資訊

- **題目連結**: https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/
- **難度**: Easy
- **解題日期**: 2024-06-25
- **解題時間**: 10 分鐘
- **程式語言**: JavaScript

## 🎯 題目描述

## 💡 解題思路

1. **第一步**: 使用Math.max 獲取最大糖果樹 變數名稱為max
2. **第二步**: 遍歷陣列，對於每個數字計算 = candy+extraCandies 若計算結果大於最大糖果數，則result陣列push true value，否則push false value
3. **第三步**: return results

## ⏱️ 複雜度分析

* O(n)+O(n)

## 💻 程式碼實現

### 解法：Math.max()+for loop

```javascript
/**
 * @param {number[]} candies
 * @param {number} extraCandies
 * @return {boolean[]}
 */
var kidsWithCandies = function(candies, extraCandies) {
    let max=Math.max(...candies);
    let results=[];
    for(idx in candies){
        if(candies[idx]+extraCandies>=max)
            results.push(true);
        else
            results.push(false);
    }
    return results;
};
```

## 📚 學習心得

- **學到的新概念**:整體解題思路並不複雜，主要是套件函數語法的不熟悉，這點可以多加記憶
- **使用語法**: Math.max() Array.push(Collection c)

## 📖 參考資料

- [JavaScript Math.max](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)

## 🏷️ 標籤

- Array

---

*解題時間: 10 分鐘*
