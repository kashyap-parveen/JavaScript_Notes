# JavaScript_Notes
```javascript
## redux-toolkit
##### createSlice
```javascript
import {createSlice,nanoid} from '@reduxjs/toolkit'

const initialState = {
    todos:[{id:1,text:"Hello World",toggle:false}]
}

export const todoSlice = createSlice({
    name:"todo",
    initialState,
    reducers:{
        addTodo:(state,action)=>{
            const todo = {
                id:nanoid(),
                text:action.payload,
                toggle:false
            }
            state.todos.push(todo)
        },
        deleteTodo:(state,action)=>{
            state.todos = state.todos.filter((todo)=> todo.id !== action.payload)
        }
    }
})

export const {addTodo,deleteTodo} =todoSlice.actions

export default todoSlice.reducer

```
### store
##### configure
```javascript
import {configureStore} from '@reduxjs/toolkit'
import todoReducer  from '../../TodoSlice/TodoSlice'

export const Store = configureStore({
    reducer:todoReducer,
})

```
## cmd for make files & folders
```javascript
npx mkdirp controllers db middlewares models routes utils
npx touch app.js index.js constants.js

```
