# Cathay Tech Assignments

## 1
Q1. Please follow the principle (‘firstName’ + ‘lastName’ + ‘customerID’) to sort this array and print it out.

```javascript
function sortUserName(user) {

  function compareFunction(a, b) {
    const userA = `${a.firstName}${a.lastName}${a.customerID}`; 
    const userB = `${b.firstName}${b.lastName}${b.customerID}`;
    return userA.localeCompare(userB); 
  }

  return user.sort(compareFunction);
}
```

Q2. Please sort by ‘profession’ to follow the principle. (‘systemAnalytics’ > ‘engineer’ > ‘productOwner’ > ‘freelancer’ > ‘student’’)
**/

```javascript
function sortByType(user) {
  function compareFunction(a, b) {
    const order = {
      'systemAnalytics': 1,
      'engineer': 2,
      'productOwner': 3,
      'freelancer': 4,
      'student': 5
    }
    return order[a.profession] - order[b.profession];
  }
  return user.sort(compareFunction);
}
```

## 2
Explain why does this color not works, and how to fix make it work on 1st list

```
權重問題，藍色蓋不過去綠色。如果是部分item需要藍色的話，可以加li:nth-child or :first-child蓋過去
```

## 3
Please write down a function to console log unique value from this array.

```javascript
function getUniqueNumber (items) {
  return [...new Set(items)];
}
```

## 4
Can you explain about Interface and Enum, and where will you be using, please make some examples.
```
Interface: 定義物件結構
Enum: 定義一系列常數
```

```typescript
enum responseStatusCode {
  error = 500,
  success = 200
}
      
interface ButtonProps {
  text: string;
  onClick: () => void;
}
```

## 5
Can you explain the problem with the following code, and how to fix it.
```
React是批次更新，所以畫面只會re-render一次，要改使用updater function。
```

```jsx
handleAddCount() {
  this.setState(prevState => ({ count: prevState.count + 1 }));
}
```

## 6
Please write the sample code to debounce handleOnChange
```jsx
constructor(props) {
  super(props);
  this.timer = null;
}

handleOnChange = (event) => {
  clearTimeout(this.timer);
  this.timer = setTimeout(() => {
    // make ajax call
  }, 1000);
};
```