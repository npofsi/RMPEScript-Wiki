# ModPE

ModPE 是 zhuoweizhang 的启动器为 MinecraftPE 添加扩展而使用的的语言，其本质是 Rhino\(JavaScript\) 。本 mod 的灵感由此而发。

并因为其简易的实现方法，对其作出了部分适配，来方便 programers 更方便的编写 mod.

ModPE 分好多功能模块，使用过程式的编写思想，但这并不影响你用 oop 的思想来编写 rmpescript.

## Global.

```java
void clientMessage(String message)
World getLevel()
```

## ModPE.

```java
void showTipMessage(String message)
void log(String log)
String getLanguage()
String getMinecraftVersion()
void leaveGame()
void showTipMessage(String message)
```

## Level.

```java
void setWorld(World world) //设定当前Level类所作用的存档
World getWorld() //获取当前Level类所作用的存档
void explode(double x, double y, double z, double r, boolean isSmoking)
void explode(double x, double y, double z, double r)
void setTile(double x,double y,double z,String id,int data)
int getDifficulty()
```

## Player.

```java
void setPlayer(EntityPlayer player)
EntityPlayer getPlayer()
double getX()
double getY()
double getZ()
float getExp()
World getLevel()
double getPitch()
double getYaw()
EntityPlayer getEntity()
```

