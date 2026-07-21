# 柚子社 (Yuzusoft) 经典作品攻略流程图

以下为你整理了《千恋＊万花》、《魔女的夜宴》、《RIDDLE JOKER》以及《天神乱漫》的简要核心路线分支流程图。
这可以帮助你直观地了解各个游戏的女主角进入条件及好感度分支。

````carousel
## 🌸 千恋＊万花 (Senren * Banka)
> [!NOTE]
> 推荐攻略顺序：蕾娜 → 小春 → 芦花 → 芳乃 → 丛雨 → 茉子
> 注意：小春和芦花线通常需要在二周目及以后才能进入。

```mermaid
graph TD
    Start[游戏开始 共通线] --> Options1{关键好感度选项}
    
    Options1 -->|偏向 芳乃/蕾娜| Branch1(钓鱼相关选项)
    Options1 -->|偏向 茉子| Branch2(挖野菜相关选项)
    Options1 -->|偏向 丛雨| Branch3(单独行动)
    
    Branch1 --> CheckYoshino{芳乃好感度满?}
    CheckYoshino -->|Yes| RouteYoshino[朝武芳乃 线]
    CheckYoshino -->|No| CheckRena{蕾娜好感度满?}
    CheckRena -->|Yes| RouteRena[蕾娜 线]
    
    Branch2 --> CheckMako{茉子好感度满?}
    CheckMako -->|Yes| RouteMako[常陆茉子 线]
    
    Branch3 --> CheckMurasame{丛雨好感度满?}
    CheckMurasame -->|Yes| RouteMurasame[丛雨 线]
    
    CheckRena -->|No| CheckKoharu{二周目 & 小春好感满?}
    CheckKoharu -->|Yes| RouteKoharu[小春 线]
    
    CheckMako -->|No| CheckRoka{二周目 & 芦花好感满?}
    CheckRoka -->|Yes| RouteRoka[马庭芦花 线]
    
    CheckMurasame -->|No| BadEnd[表哥线 / 单身线]
    CheckKoharu -->|No| BadEnd
    CheckRoka -->|No| BadEnd
```

<!-- slide -->
## 🌙 魔女的夜宴 (Sanoba Witch)
> [!TIP]
> 推荐首先攻略绫地宁宁。隐藏角色【假屋和奏】需在完成任意一周目后解锁。

```mermaid
graph TD
    Start[游戏开始 共通线] --> Ch2[第二章 分支点]
    
    Ch2 -->|2-2 拜托绫地| BranchNene(宁宁 / 䌷 分支)
    Ch2 -->|2-2 就这样和因幡继续下去| BranchMeguru(巡 / 憧子 分支)
    
    BranchNene -->|倾向宁宁, 关心宁宁| RouteNene[绫地宁宁 线]
    BranchNene -->|放弃学习, 偏离感情线| RouteTsumugi[椎叶䌷 线]
    
    BranchMeguru -->|配合因幡演练, 互动增多| RouteMeguru[因幡巡 线]
    BranchMeguru -->|倾向憧子学姐| RouteTouko[户隐憧子 线]
    
    RouteNene -.通关任一角色后.-> UnlockWakana{解锁和奏线}
    UnlockWakana -->|二周目避开主角团好感| RouteWakana[假屋和奏 线 - 隐藏]
    
    RouteNene --> TrueEnd[宁宁 TRUE END - 重启与追加剧情]
```

<!-- slide -->
## 🃏 RIDDLE JOKER
> [!NOTE]
> 推荐攻略顺序：二条院羽月 → 壬生千咲 → 式部茉优 → 在原七海 → 三司绫濑。千咲线需二周目解锁。

```mermaid
graph TD
    Start[游戏开始 共通线] --> Lab{研究室选项}
    
    Lab -->|继续实验| BranchUpper(绫濑/茉优/羽月 分支)
    Lab -->|向七海搭话| BranchNanami(七海 分支)
    
    BranchUpper --> Swimsuit{泳装事件倾向}
    Swimsuit -->|想看二条院的泳装| RouteHazuki[二条院羽月 线]
    Swimsuit -->|去研究室找茉优学姐| RouteMayu[式部茉优 线]
    Swimsuit -->|倾向绫濑| RouteAyase[三司绫濑 线]
    
    BranchNanami -->|好好夸她两句, 想看泳装| RouteNanami[在原七海 线]
    
    RouteNanami -.通关任一线路后.-> UnlockChisaki{二周目千咲解锁}
    UnlockChisaki -->|多选择关心千咲的日常选项| RouteChisaki[壬生千咲 线]
    
    BranchUpper -->|好感度均不足| BadEnd[单身线 Normal End]
    BranchNanami -->|好感度均不足| BadEnd
```

<!-- slide -->
## ⛩️ 天神乱漫 (Tenshin Ranman)
> [!TIP]
> 推荐攻略顺序：まひろ → 紫 → 佐久夜 → ルリ → 佐奈 → 葵。全通关后解锁隐藏快乐结局。

```mermaid
graph TD
    Start[共通线] --> RouteSelect{好感度与地点选择}
    
    RouteSelect -->|主要陪伴前辈| RouteMahiro[常盘まひろ 线]
    RouteSelect -->|倾向同班同学| RouteYukari[乌羽紫 线]
    RouteSelect -->|倾向神社与神明| RouteSakuya[卯花之佐久夜姫 线]
    RouteSelect -->|倾向狐耳娘| RouteRuri[龙胆ルリ 线]
    RouteSelect -->|倾向妹妹| RouteSana[千岁佐奈 线]
    RouteSelect -->|倾向青梅竹马| RouteAoi[山吹葵 线]
    
    RouteMahiro -.完成所有个人线.-> TrueEnd[快楽エンド / 特殊结局]
    RouteYukari -.-> TrueEnd
    RouteSakuya -.-> TrueEnd
    RouteRuri -.-> TrueEnd
    RouteSana -.-> TrueEnd
    RouteAoi -.-> TrueEnd
    
    RouteSelect -->|好感度分散未达标| BadEnd[普通日常线 / 退回主界面]
```
````
