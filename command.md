# Command

以下是使用 rmpe 在 minecraft 中注册命令的方法。

## 回调

用户使用命令后执行（example）：

```javascript
var commandCallback=new _RMPE.command.CommandInstance.Callback({
    "execute":function(server,sender,args){
                //TODO
        Level.explode(sender.posX,sender.posY,sender.posZ,10);
    }
});
```

## 实例

建立一个回调后需要把回调包装成一个命令实例：

```javascript
// 参数: 指令名, 用法, 回调
var commandIns=new _RMPE.command.CommandInstance("boom","/boom",commandCallback);
```

## 注册

建立一个命令实例后需要注册，但只有加载存档后才能注册，所以需要一个事件监听：

```javascript
_RMPE.broadcast.FMLEventHandler.getInstance().registerCallback("serverStarting",new _RMPE.broadcast.FMLEventHandler.FMLEventCallback({
    "call":function(event){
        _RMPE.command.CommandManager.getInstance().register(commandIns);
    }
}));
```

## 例子

[example/CommandBoom.js](https://github.com/npofsi/RMPEScript/blob/master/examples/CommandBoom.js)

