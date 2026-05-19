```mermaid
graph TD
    %% 样式定义
    classDef red fill:#d32f2f,stroke:#b71c1c,stroke-width:2px,color:white;
    classDef black fill:#424242,stroke:#212121,stroke-width:2px,color:white;
    classDef green fill:#388e3c,stroke:#1b5e20,stroke-width:2px,color:white;
    classDef water fill:#1976d2,stroke:#0d47a1,stroke-width:2px,color:white;
    classDef forest fill:#2e7d32,stroke:#1b5e20,stroke-width:2px,color:white,stroke-dasharray: 5 5;

    %% ========== 地形与环境 ==========
    subgraph Legend [图例]
        L_Red("● 红色 - 战役地点") :::red
        L_Black("▲ 黑色 - 匪巢") :::black
        L_Green("■ 绿色 - 村镇") :::green
        L_Water("~~~~ 蓝色 - 河流")
        L_Forest("--- 绿色 - 林海/原始森林")
    end

    %% ========== 主地图结构 ==========
    subgraph North_West ["西北部 - 张广才岭（高海拔密林区）"]
        direction TB
        Weihushan("<b>威虎山 ▲</b><br/>座山雕匪巢<br/>『九群二十七地堡』") :::black
        Jiapigou("<b>夹皮沟 ■</b><br/>小分队驻地<br/>森林铁路终点") :::green
        Forest1("<b>林海 🌲</b><br/>原始密林，冬季雪深数米")
    end

    subgraph South ["南部 - 平原/低山丘陵"]
        Hailin("<b>海林 ■</b><br/>剿匪前哨基地") :::green
        Mudanjiang("<b>牡丹江市 ■</b><br/>军区指挥部") :::green
    end

    subgraph East ["东部 - 老爷岭"]
        Shanjia("<b>杉岚站 ■</b><br/>遭土匪屠杀的村屯") :::green
        Kulunbi("<b>库仑比 ■</b>") :::green
    end

    subgraph River ["河流水系"]
        Mudan_River("牡丹江 ~~~~") :::water
        Hailang_River("海浪河 ~~~~") :::water
    end

    %% ========== 关键地点与暗道 ==========
    Shenhe_Temple("<b>神河庙</b><br/>伪装成庙宇的联络站") :::green
    Wufu_Ridge("五福岭<br/>『怀抱五福，易守难攻』")

    %% 威虎山暗道系统
    subgraph Weihushan_Tunnels ["威虎山暗道系统"]
        Tunnel1("暗道1 → 夹皮沟")
        Tunnel2("暗道2 → 牡丹峰")
        Tunnel3("暗道3 → 套环山")
    end

    %% ========== 交通线 ==========
    RailRoad("森林小铁路 🚂<br/>夹皮沟 ↔ 牡丹江")

    %% ========== 连接关系 ==========
    Weihushan --- Wufu_Ridge
    Weihushan --> Tunnel1 & Tunnel2 & Tunnel3
    Tunnel1 -.-> Jiapigou
    
    Jiapigou --- RailRoad
    RailRoad -.-> Mudanjiang
    
    Jiapigou --- Forest1
    Weihushan --- Forest1
    
    Mudan_River --- Mudanjiang
    Hailang_River --- Hailin
    
    Shenhe_Temple --- RailRoad
    Jiapigou --- Shenhe_Temple
    
    %% 战役事件连线
    Weihushan -.-> |"奇袭匪巢<br/>『百鸡宴』"| L_Red
    Shanjia -.-> |"惨案发生地"| L_Red
```