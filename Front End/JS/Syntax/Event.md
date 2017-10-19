# 事件

The difference between 'return false;' and 'e.preventDefault();'

cabcelable属性表示事件是否可取消，只有此属性为true时，事件对象的preventDefault方法才会起到阻止事件默认行为的作用。

```js
function stopEvent(event){
    var e = (event) ? event : window.event;
    if (e.stopPropagation) {
        e.stopPropagation();
        e.preventDefault();
    }
    else {
        e.cancelBubble = true;
        e.returnValue = false;
    }
}
```

## event.preventDefault()

该方法将通知 Web 浏览器不要执行与事件关联的默认动作（如果存在这样的动作）。

例如，如果 type 属性是 "submit"，在事件传播的任意阶段可以调用任意的事件句柄，通过调用该方法，可以阻止提交表单。

注意，如果 Event 对象的 cancelable 属性是 fasle，那么就没有默认动作，或者不能阻止默认动作。无论哪种情况，调用该方法都没有作用。

## event.stopPropagation()

该方法将停止事件的传播，阻止它被分派到其他 Document 节点。在事件传播的任何阶段都可以调用它。

注意:虽然该方法不能阻止同一个 Document 节点上的其他事件句柄被调用，但是它可以阻止把事件分派到其他节点。

event是DOM的事件方法，所以不是单独使用，比如指定DOM