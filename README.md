### Описание по использованию контекста на чистом React

---

### About

Я попытаюсь кратко рассказать тебе базу, чтобы ты понял как работать с контекстом в React проекте.

---

### Documentation

1. Используй `createContext` чтобы создать глобальную переменную в файле ___Context.ts___;
   ```
   export const myContext = React.createContext<string | undefined>(undefined)

   
2. Потом в родительском компонетне Parent.tsx:
   + оберни дочерние элементы своим ***"провайдером контекста"*** (глоб. переменаая и через точку ___Provider___)
   + и наконец помести в `value` глобальную переменную

     
   ```
      <myContext.Provider value={contextValue}>
        <Child />
      </myContext.Provider>
    ```
   
     
     
3. И теперь просто используй глобальную переменную в ___Child.tsx___:
   ```
   import { useContext } from 'react'
   import { myContext } from '../Context/Context'
    
   export function Child(){
     const context = useContext(myContext)
      
      return<>
        <h1>{context}</h1>
        <p>just test</p>
      </>
    }
---
