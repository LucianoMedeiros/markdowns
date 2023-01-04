# Projeto
> Instalação
```bash 
pnpm create vite
```

# Ant Design
> Instalação
```bash 
pnpm add antd react-icons moment
pnpm add -D @types/antd
```
# Redux
> Instalação
```bash 
pnpm add @reduxjs/toolkit react-redux axios
pnpm add -D @types/react-redux
```
> Configuração

**src/store/store-config.ts**

```js 

import { Action, configureStore, ThunkAction } from '@reduxjs/toolkit'
import { useSelector } from 'react-redux'
import { TypedUseSelectorHook, useDispatch } from 'react-redux'
// import { userReducer } from './user/user-reducer'

const store = configureStore({
  reducer: {
    // user: userReducer,
  },
  middleware: (getDefaultMiddleware) => getDefaultMiddleware({ serializableCheck: false }),
})

export type RootState = ReturnType<typeof store.getState>
export type AppDispatch = typeof store.dispatch
export type Appthunk = ThunkAction<void, RootState, null, Action<string>>

export const useAppDispatch: () => AppDispatch = useDispatch
export const useAppSelector: TypedUseSelectorHook<RootState> = useSelector

export default store
```

**src/store/user/user-reducer.ts**
```js 
import { createSlice } from '@reduxjs/toolkit'
import { userInitialState } from './user-initialstate'

const slice = createSlice({
  name: '',
  initialState: userInitialState,
  reducers: {
    setIsPending: (state, { payload }) => {
      state.isPending = payload
    },
  },
})

export const UserActions = slice.actions

export const userReducer = slice.reducer
```

**src/store/user/user-initialstate.ts**
```js 
export const userInitialState = {
  isPending: false,
  all: [],
  current: {
    name: '',
    email: '',
  }
}
```
