# Heap

### 힙

```javascript
class MaxHeap {
    constructor(){
        this.heap = []
    }
    
    swap(i ,j){
        [this.heap[i], this.heap[j]] = [this.heap[j], this.heap[i]]
    }
    
    push(value){
        this.heap.push(value)
        let cur = this.heap.length - 1
        
        while(cur > 0){
            let parent = parseInt((cur-1) / 2)
            if(this.heap[parent] < this.heap[cur]){
                this.swap(parent, cur)
                cur = parent
            } else {
                break
            }
        }
    }
    
    pop(){
        if(this.heap.length === 0) return null
        if(this.heap.length === 1) return this.heap.pop()
        
        let max = this.heap[0]
        this.heap[0] = this.heap.pop()
        this.heapify(0)
        
        return max
    }
    
    heapify(index){
        let large = index
        let left = index * 2 + 1
        let right = index * 2 + 2
        
        if(left < this.heap.length && this.heap[small] < this.heap[left]){
            large = left
        }
        
        if(right < this.heap.length && this.heap[small] < this.heap[right]){
            large = right
        }
        
        if(large !== index){
            this.swap(large, index)
            this.heapify(large)
        }
    }
}
```



### 최소 힙

```javascript
class MinHeap {
    constructor(){
        this.heap = []
    }
    
    swap(i ,j){
        [this.heap[i], this.heap[j]] = [this.heap[j], this.heap[i]]
    }
    
    push(value){
        this.heap.push(value)
        let cur = this.heap.length - 1
        
        while(cur > 0){
            let parent = parseInt((cur-1) / 2)
            if(this.heap[parent] > this.heap[cur]){
                this.swap(parent, cur)
                cur = parent
            } else {
                break
            }
        }
    }
    
    pop(){
        if(this.heap.length === 0) return null
        if(this.heap.length === 1) return this.heap.pop()
        
        let min = this.heap[0]
        this.heap[0] = this.heap.pop()
        this.heapify(0)
        
        return min
    }
    
    heapify(index){
        let small = index
        let left = index * 2 + 1
        let right = index * 2 + 2
        
        if(left < this.heap.length && this.heap[small] > this.heap[left]){
            small = left
        }
        
        if(right < this.heap.length && this.heap[small] > this.heap[right]){
            small = right
        }
        
        if(small !== index){
            this.swap(small, index)
            this.heapify(small)
        }
    }
}
```
