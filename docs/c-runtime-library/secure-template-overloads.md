---
title: "Sichere Vorlagen&#252;berladungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT"
  - "Sichere Vorlagenüberladungen"
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Sichere Vorlagen&#252;berladungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele CRT\-Funktionen wurden zugunsten der neueren, Sicherheit\-erhöhten Versionen veraltet \(beispielsweise, `strcpy_s` ist die sicherere Ersatz für `strcpy`\).  Die CRT\- stellt Vorlagenüberladungen, um dazu beizutragen, den Übergang zu den sichereren Varianten zu erleichtern.  
  
 Beispielsweise generiert dieser Code eine Warnung, da `strcpy` ist veraltet:  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // warning: deprecated`  
  
 Sie können die Warnung ignorieren.  Definieren Sie das Symbol `_CRT_SECURE_NO_WARNINGS`, um die Warnung zu unterdrücken, oder aktualisieren Sie den Code, um `strcpy_s` zu verwenden:  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, 10, "test"); // security-enhanced _s function`  
  
 Die Vorlagenüberladungen stellen zusätzliche Optionen.  Das Definieren von `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` auf 1 aktiviert Vorlagenüberladungen von Standard\-CRT funktioniert, die die beim Varianten automatisch aufrufen.  Wenn `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 1 ist, dann sind keine Änderungen am Code erforderlich.  Im Hintergrund wird der Aufruf von `strcpy` zu einem Aufruf von `strcpy_s` mit dem Größenargument geändert, das automatisch angegeben wird.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` hat keine Auswirkungen auf die Funktionen, die eine Anzahl verwenden, z `strncpy`.  Um Vorlagenüberladungen für die Anzahlfunktionen zu aktivieren, definieren Sie `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` auf 1.  Vor dies überprüfen Sie jedoch, ob Ihr Code die Anzahl von Zeichen übergibt, nicht die Puffergröße \(ein häufiger Fehler\).  Außerdem Code, der explizit ein NULL\-Zeichen am Ende des Puffers schreibt, nachdem der Funktionsaufruf nicht erforderlich ist, wenn die Variante sichere aufgerufen wird.  Wenn Sie Abschneidenverhalten benötigen, finden Sie unter [\_TRUNCATE](../c-runtime-library/truncate.md).  
  
> [!NOTE]
>  Makro\- `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` erforderlich, dass `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` auch als 1 definiert. wird.  Wenn `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` definiert wurde, während 1 und `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` als 0 definiert ist, wird die Anwendung keine Vorlagenüberladungen aus.  
  
 Das Definieren von `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` auf 1 aktiviert Vorlagenüberladungen der sicheren Varianten \(die Namen, die in "\_s" Beenden\).  In diesem Fall `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1 ist, wird eine kleinere Änderung muss zum ursprünglichen Code durchgeführt werden:  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 Nur der Name der Funktion muss geändert werden \(durch Hinzufügen "von \_s"\); die Vorlagenüberladung kümmert sich um Bereitstellen des Größenarguments.  
  
 Standardmäßig werden `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` und `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` definiert, wie 0 \(Deaktiviert\) und `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` als 1 definiert \(aktiviert\).  
  
 Beachten Sie, dass diese Vorlagenüberladungen nur für statische Arrays arbeiten.  Dynamisch zugeordnete Puffer erfordern zusätzliche Quellcodeänderungen.  Nochmals besuchen der oben aufgeführten Beispiele:  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy(szBuf, "test"); // still deprecated; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
 Und dieses:  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy_s(szBuf, "test"); // doesn't compile; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
## Siehe auch  
 [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)