# Titanic Workshop

![alt bit.ly/SAIG-TITANIC](https://saig-kmitl.github.io/titanic-workshop/saig-titanic-qr.jpg)

## Slides
* https://www.canva.com/design/DAGMnMjQlOM/H51kDyp1pRodPIl-U4qK7Q/edit 

## คำสั่ง
* Copy the following code into Colab to complete the process of building a model to predict the survival of Titanic passengers.
  
  (จงคัดลอง code ต่อไปนี้ ไปเติมใน Colab เพื่อให้เป็นกระบวนการสร้างโมเดลการทำนายการรอดของผู้โดยสารไททานิค)
* Link of Colab:  https://colab.research.google.com/drive/1cYVrWHJhP44V30w7ftj20i2UqOdlppkJ
* If you have time left, try applying the Artificial Neural Network (code below) to achieve higher accuracy than the Decision Tree.
  
  (หากมีเวลาเหลือ ให้ลองปรับใช้ Artifical Neural Network (code ด้านล่าง) เพื่อให้ได้ Accuracy สูงกว่า Decision Tree)

## Options (ตัวเลือก)


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
## Extra task (เพิ่มเติม)
Try adapting this Neural Network code to achieve higher accuracy.

(ลองนำ code ของ Neural Network ตัวนี้ไปปรับใช้ เพื่อให้ได้ค่า Accuracy สูงขึ้น)

```
from sklearn.neural_network import MLPClassifier
model = MLPClassifier(hidden_layer_sizes=(1, 1), activation='relu')
model.fit(X_train,y_train)

y_pred = model.predict(X_test)

from sklearn.metrics import accuracy_score
acc = accuracy_score(y_test, y_pred)
print('Accuracy = ', acc)
```

---
## Ref
* Data from  https://www.kaggle.com/datasets/yasserh/titanic-dataset
