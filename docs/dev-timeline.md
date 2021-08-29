# Development timeline  
This document records the development timeline.

## Create code base  
Vue3 is used as development framework    

## Add Quasar as UI framework   

Quasar is used as UI framework   

Webfonts: https://icons8.com/line-awesome  

## Class component approach 
Adopt vue class component to author component in typescript class-style syntax. 

https://juejin.cn/post/6860703641037340686  

Other link is here:  
https://medium.com/@takeit_/vue-3-composition-api-with-typescript-class-components-dbe7cc9bb468  
https://github.com/vuejs/vue-class-component/issues/406  

https://class-component.vuejs.org/

## Component drag and drop  
1. 设置拖拽元素的的draggable属性为true，即draggable="true"
2. 添加事件"dragstart"响应函数，执行一些拖拽应用的数据初始化处理
3. 在放置拖拽元素的目标元素中添加事件"drop"和"dragover"的事件响应函数
4. 在"dragover"事件响应函数中需要调用 e.preventDefault() 以允许放置拖拽元素
5. 在"drop"事件响应函数中执行拖拽应用的完成处理  

参考：https://developer.mozilla.org/en-US/docs/Web/API/Document/drag_event  

## State management  
1. Use vuex's createStore to create a state store, for example, define state store in ./store/index.ts  

    ```typescript
    import { createStore } from 'vuex'

    export default createStore({
        state: {
            count: 0
        },
        mutations: {
            increment(state) {
            state.count++;
            }
        },
    })
    ```
2. Import it anywhere you want to use the store  

    ```typescript
    import store from '@/store'

    // modify
    store.commit('increment');

    //access
    store.state.count;
    ```
参考：https://stackoverflow.com/questions/64545382/create-a-global-store-using-vue-3-composition-api  
 