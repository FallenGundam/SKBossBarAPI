# SKBossBarAPI
因其他插件的bossbar不太合乎需求所以自己寫了一個，可綁定獨有ID  
![image](https://user-images.githubusercontent.com/54828956/227782421-60c572e3-ae22-492f-b6d8-9df9f7bb8f2c.png)  

# required:
 skript 2.5 ~ lastest  
 skript-reflect

# 備註:  
 id不可使用中文只可使用英文a-z/0-9  
 當重啟後，所有的bossbar將會被清除  

# API
  * ### effect:  
    * #### 創建一個bossbar  並回傳該bossbar物件  
      > BossBar_create(id:string,title:string = "example title",color:string = "red",style:string = "SOLID")  
      > id必填，其他留空會自動使用預設值  
      ex:  
      `set {_bar} to BossBar_create("mybar","&emy title","red","solid")`  
    * #### 刪除bossbar物件
      > delete bossbar [object] %object%  
      ex:  
      `delete bossbar {_bar}`
  * ### conditions:
    * #### 判斷bossbar物件是否存在  
      > BossBar_isExists(id:string) return boolean  
      ex:  
      `if BossBar_isExists("mybar") = true:`  
  * ### expression:
    * #### 透過id取得bossbar物件  
      > bossbar [object] by id %string%  
      ex:  
      `set {_bar} to bossbar by id "mybar"`  
      `delete bossbar by id "mybar"`  
    * #### 取得所有存在的bossbar id  
      > all [of] bossbar [object] [with id]  
      ex:  
      `broadcast "%all bossbar object%"`  
      `delete all bossbar object`  
    * #### 設定bossbar物件中的玩家
      > bossbar [object] players of %object%  
      ex:  
      `set {_players::*} to bossbar players of {_bar}`  
      `add player to bossbar players of {_bar}`  
      `remove player from bossbar players of {_bar}`  
      `delete bossbar players of {_bar}`  
    * #### 更改bossbar的顏色
      > bossbar [object] color of %object%  
      ex:  
      `set bossbar color of {_bar} to "red"`
    * #### 更改bossbar的style
      > bossbar [object] style of %object%  
      > 可使用 SEGMENTED_10, SEGMENTED_12, SEGMENTED_20, SEGMENTED_6, SOLID  
      ex:  
      `set bossbar color of {_bar} to "solid"`  
    * #### 添加bossbar特殊flag
      > bossbar [object] flags of %object%  
      > 可使用 CREATE_FOG, DARKEN_SKY,	PLAY_BOSS_MUSIC  
      ex:  
      `add "CREATE_FOG" to bossbar flags of {_bar}`  
      `remove "CREATE_FOG" from bossbar flags of {_bar}`  
      `set {_flags::*} to bossbar flags of {_bar}`  
    * #### 更改bossbar的title
      > bossbar [object] title of %object%  
      ex:  
      `set {_title} to bossbar title of {_bar}`  
      `set bossbar title of {_bar} to "&e這是標題"`  
    * #### 更改bossbar的進度條
      > bossbar [object] progress of %object%  
      > 回傳數字number(0-100)
      > 輸入數字為 0 ~ 100  
      ex:  
      `set bossbar progress of {_bar} to 100`  
      `add 10 to bossbar progress of {_bar}`  
      `set {_progress} to bossbar progress of {_bar}`
    * #### 玩家是否可見bossbar
      > bossbar [object] %object% can visible  
      > 回傳布林值  
      ex:  
      `if bossbar {_bar} can visible = true`  
      `  set bossbar {_bar} can visible to false`  
  * ### Type:
    * #### 取得 color, flag, style 的所有名稱
      > all %string% type in bossbar [object]  
      > 回傳string列表  
      ex:  
      `set {_color::*} to all "color" type in bossbar`  
      `set {_rainbow} to random element out of {_color::*}:`  
      `set bossbar color of {_bar} to {_rainbow}`  
      
      
      
      
      
      
      
      
