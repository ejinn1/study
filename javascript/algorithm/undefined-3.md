# 연결리스트

### 단일 연결 리스트

```javascript
class Node{
    constructor(val){
        this.val = val
        this.next = null
    }
}

class SiglyList{
    constructor(){
        this.length = 0
        this.head = null
        this.tail = null
    }
    push(val){
        let newNode = new Node(val)
        if(this.head === null){
            this.head = newNode
            this.tail = newNode
        } else {
            this.tail.next = newNode
            this.tail = newNode
        }

        this.length++
    }
    pop(){
        if(!this.head) return undefined
        let pre = this.head
        let del = pre
        while(del.next){
            pre = del
            del = del.next
        }
        pre.next = null
        this.tail = pre
        this.length--
        if(this.length === 0){
            this.head = null
            this.tail = null
        }
        return del
    }

    shift(){
        if(!this.head) return undefined
        let cur = this.head
        this.head = cur.next
        this.length--
        if(this.length === 0){
            this.tail = null
        }
        return cur
    }

    unshift(val){
        let newNode = new Node(val)
        if(!this.head){
            this.head = newNode
            this.tail = newNode
        } else {
            newNode.next = this.head
            this.head = newNode
        }
        this.length++
    }

    get(idx){
        if(idx < 0 || !this.head) return null
        let i = 0
        let cur = this.head
        while(i < idx){
            cur = cur.next
            i++
        }
        return cur
    }

    set(idx, val){
        let foundNode = this.get(idx)
        if(foundNode){
            foundNode.val = val
            return true
        }
        return false
    }

    insert(idx, val){
        if(idx < 0 || idx > this.length) return false
        if(idx === 0){
            this.unshift(val)
            return true
        }
        if (idx === this.length){
            this.push(val)
            return true
        }
        let newNode = new Node(val)
        let pre = this.get(idx - 1)
        newNode.next = pre.next
        pre.next = newNode
        this.length++
        return true
    }

    remove(idx){
        if(idx < 0 || idx > this.length) return undefined
        if(idx === 0) return this.shift()
        if(idx === this.length - 1) return this.pop()
        let pre = this.get(idx - 1)
        let del = pre.next
        pre.next = del.next
        this.length--
        return del
    }

    reverse(){
        
    }
}

let list = new SiglyList()
```











### 이중 연결 리스트
