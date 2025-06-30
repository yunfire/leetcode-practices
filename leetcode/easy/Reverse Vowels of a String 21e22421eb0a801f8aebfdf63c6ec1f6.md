# Reverse Vowels of a String

## 📋 題目資訊

- **題目名稱: Reverse Vowels of a String**
- **題目連結**: [https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/](https://leetcode.com/problems/reverse-vowels-of-a-string/description/?envType=study-plan-v2&envId=leetcode-75)
- **難度**: Easy
- **解題日期**: 2024-06-26
- **解題時間**: 70 分鐘
- **程式語言**: JavaScript

## 🎯 題目描述

## 💡 解題思路

### 解法1. 索引蒐集+重組

1. 遍歷字串後取得母音索引值後並反轉
2. 再次遍歷字串並對照是否對應到母音索引值
    1. 遇到母音則透過反轉後的索引取值
    2. 沒對應到則正常添加字串
3. 返回字串

## ⏱️ 複雜度分析

- O(n)+O(n)

## 💻 程式碼實現

### 解法：Array.toReversed()+Array.includes()

```jsx
/**
 * @param {string} s
 * @return {string}
 */
var reverseVowels = function(s) {
    let vowelsIdx=[]
    let reversedvowelsIdx=[]
    let vowels=['a','e','i','o','u','A','E','I','O','U'];
    let len=s.length;
    let results="";
    for(var i=0;i<len;i++){
        if(vowels.indexOf(s[i])>=0){
            vowelsIdx.push(i);
        }
    }
    reversedvowelsIdx=vowelsIdx.toReversed()
    for(let i=0;i<len;i++){
        if(vowelsIdx.indexOf(i)>=0){   
            results+=s[reversedvowelsIdx[vowelsIdx.indexOf(i)]]
        }else{
            results+=s[i];
        }
    }
    return results;
};

```

### 解法2. 雙指標法

1. 定義母音字元集 `vowels` 包含母音大小自
2. 雙指標法(Two Pointers)
    1. 使用兩個指標 `i` (從字串頭部)、`j`(從字串尾部)
    2. 目的是同時從兩端尋找母音 
3. 主迴圈
    1. 當i<j時持續執行:
        1. 如果arr[i]是母音且arr[j]也是母音，則交換兩者位置(母音交換)
        2. 如果arr[i]是母音且arr[j]不是母音，則j--(往前找母音)
        3. 其他: 則i++(往後找母音)
4. 組合結果回傳

## ⏱️ 複雜度分析

- O(n)

## 💻 程式碼實現

### 解法：Array.toReversed()+Array.includes()

```jsx
/**
 * @param {string} s
 * @return {string}
 */
var reverseVowels = function(s) {
    let vowelsIdx=[]
    let reversedvowelsIdx=[]
    let vowels=['a','e','i','o','u','A','E','I','O','U'];
    let len=s.length;
    let results="";
    let arr=s.split('');
    let i=0;
    let j=len-1;
    while(i<j){
        if(vowels.includes(arr[i]) && vowels.includes(arr[j])){
            let temp=arr[i]
            arr[i]=arr[j]
            arr[j]=temp
            i++;
            j--;
        }else if(vowels.includes(arr[i])){
            j--
        }else{
            i++
        }
    }
    return arr.join('');
};
```

## 📚 學習心得

- 解法1需要跑兩次迴圈 分別是蒐集索引反轉與重組句子，邏輯值觀不需要交換陣列元素
- 解法2透過雙指標法 可以頭尾同時尋找 時間與空間複雜度皆為O(n)  效率更高 缺電就是需要理解雙指標的運作邏輯 不是那麼直觀
- **使用語法**: `Array.toReversed()`、 `Array.includes(Collection c)`
- **演算法:** `Two Pointer`

## 📖 參考資料

## 🏷️ 標籤

- Array

---

*解題時間: 70 分鐘*