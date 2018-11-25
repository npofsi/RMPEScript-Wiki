# Event

RMPEScript 的事件处理分三类：FMLEvent, MinecraftEvent, ModPEHooks. 而ModPEHooks由前两种 Event 控制，并且尚不完善。

## FMLEvent

FMLEvent 是指作为 ForgeMod 可以接收到的回调。

这种回调可以在 `_RMPE.broadcast.FMLEventHandler` 注册

先定义一个回调:

```javascript
var callback=new _RMPE.broadcast.FMLEventHandler.FMLEventCallback({
    "call":function(event){
        //TODO
    }
})
```

然后就可以注册这个回调（ `init` 处即事件名称,只在 r1.0.0 版本中不需要`.getInstance()`）：

```javascript
_RMPE.broadcast.FMLEventHandler.getInstance().registerCallback("init",callback)
```

之后可以选择性注销这个回调（注意也需要写事件的名称）：

```javascript
_RMPE.broadcast.FMLEventHandler.getInstance().unregisterCallback("init",callback)
```

### FML事件列表：

* init：forge 加载 mod 时触发
* serverStarting：mc 本地服务器启动时触发（相当于启动存档时）

## MinecraftEvent

这类事件是原版游戏运行时发生的事件

类似的，这种回调可以在 `_RMPE.broadcast.ForgeEventHandler` 注册（叫 Forge 是因为注册是用的是 ForgeAPI ）

与上面类似，先定义一个回调:

```javascript
var callback=new _RMPE.broadcast.ForgeEventHandler.EventCallback({
    "call":function(event){
        //TODO
    }
})
```

然后就可以注册这个回调（ `pickupItem` 处即事件名称）：

```javascript
_RMPE.broadcast.ForgeEventHandler.getInstance().registerCallback("pickupItem",callback)
```

之后可以选择性注销这个回调（注意也需要写事件的名称）：

```javascript
_RMPE.broadcast.ForgeEventHandler.getInstance().unregisterCallback("pickupItem",callback)
```

### MinecraftEvent事件列表（这里不需要解释了吧）

* pickupItem
* arrowNocked
* pickupXp
* entityAttacked
* advancement

