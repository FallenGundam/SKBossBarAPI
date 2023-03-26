# SKBossBarAPI
因其他插件的bossbar不太合乎需求所以自己寫了一個，可綁定獨有ID

# 備註:  
 id不可使用中文只可使用英文a-z/0-9  
 當重啟後，所有的bossbar將會被清除  

# API
  * ### effect:  
    * #### 創建一個bossbar  並取得該bossbar物件  
      > create bossbar [object] by id %string% with title %string% with color %string% [with type %string%]  
      ex:  
      `create bossbar object by id "mybar" with title "this title" with color "red" with type "solid"`  
      `set {_mybar} to bossbar object by id "mybar"`

      __可使用function的方式 (推薦)__  
      > BossBar_create(id:string,title:string,color:string,style:string = "SOLID")  
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
      `set bossbar title of {_bar} to "&e這是標題"`  
    * #### 更改bossbar的進度條
      > bossbar [object] progress of %object%  
      > 輸入數字為 0 ~ 100  
      ex:  
      `set bossbar progress of {_bar} to 100`

      
      
      
      
      
      
      
