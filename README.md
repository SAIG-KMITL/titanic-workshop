# Titanic Workshop

![alt bit.ly/SAIG-TITANIC](https://saig-kmitl.github.io/titanic-workshop/saig-titanic-qr.jpg)

## คำสั่ง
* จงคัดลอง code ต่อไปนี้ ไปเติมใน Colab เพื่อให้เป็นกระบวนการสร้างโมเดลการทำนายการรอดของผู้โดยสารไททานิค
* Link ของ Colab ที่  https://colab.research.google.com/drive/1cYVrWHJhP44V30w7ftj20i2UqOdlppkJ

## ตัวเลือก


```
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(max_depth=2)
model.fit(X_train,y_train)
```


```
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X,y, test_size=0.2)
```



```
y = df['Survived']
```


```
y_pred = model.predict(X_test)
```


```
X = df[['Sex', 'Age']].copy()
```


```
from sklearn.metrics import accuracy_score

acc = accuracy_score(y_test, y_pred)
print('Accuracy = ', acc)
```



```
df.dropna(inplace=True)
```



```
X['Sex'] = X['Sex'].map({'male':1, 'female':0})
```

---
## อ้างอิง
* ข้อมูลจาก https://www.kaggle.com/datasets/yasserh/titanic-dataset
