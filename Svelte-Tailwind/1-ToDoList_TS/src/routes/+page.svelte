<script lang="ts">

    type ToDoItem = {
        text: String;
        id: Number;
    }
    
    
    let text = '';
    
    let toDoItems: ToDoItem[] = [];
    
    function add(){
    
    console.log(text)
            //    text: toDoItem.text,
            //     html :`<div class="border-black border-b-[1px] flex ">
            //     <div class="flex items-center">
            //         <h1 class="text-3xl pl-3">✓</h1><li class="pl-3"></li>
            //     </div>
            //     <div class="flex flex-1 justify-end">
            //         <button class="bg-gray-300">
            //             <img class="w-[70px] h-[70px] border border-x-neutral-500 bg-neutral-200 active:bg-neutral-300" src="/images/crayon.png" alt="ee">
            //         </button>
            //         <button class="px-[30px] py-[20px] border-neutral-500 bg-gray-200 active:bg-gray-300">x</button>
            //     </div>
            // </div>`
        
            toDoItems = toDoItems
    
            toDoItems.push({id : toDoItems.length, text : text})
        }
        
    function deleteTodo(id: number){
        toDoItems.splice(id,1)
        toDoItems = toDoItems
    }
        
    </script>
    
        <div class="w-[600px] border-neutral-900 border h-[500px] m-auto">
    
            <div class="border-neutral-900 border-b h-[100x] mx-auto my-auto">
                    <div  class=" flex my-[25px] w-[320px] m-auto">
                        <input bind:value={text} type="text" placeholder="text..." class="w-60 h-10 text-xl m-auto">
                        <button on:click={add} class="border border-neutral-400 bg-gray-200 px-5 py-2.5 active:bg-gray-300">Add</button>
                    </div>
            </div>
          
    {#each toDoItems as todo,i}
            <div class="border-black border-b-[1px] flex ">
                <div class="flex items-center">
                    <h1 class="text-3xl pl-3">✓</h1><li class="pl-3">{todo.text}</li>
                </div>
                <div class="flex flex-1 justify-end">
                    <button class="bg-gray-300">
                        <img class="w-[70px] h-[70px] border border-x-neutral-500 bg-neutral-200 active:bg-neutral-300" src="/images/crayon.png" alt="pencil">
                    </button>
                    <button on:click={()=> deleteTodo(i)} class="px-[30px] py-[20px] border-neutral-500 bg-gray-200 active:bg-gray-300">x</button>
                </div>
            </div>
    {/each}
        </div>
        
    <style>
         *{
           list-style: none;
        }
    </style>