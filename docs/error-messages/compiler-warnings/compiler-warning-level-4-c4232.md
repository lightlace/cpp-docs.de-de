---
title: "Compilerwarnung (Stufe 4) C4232 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4232"
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: 'Bezeichner': Adresse von dlllimport 'dllimport' ist nicht statisch, Identität wird nicht garantiert  
  
 Bei Verwendung der Microsoft\-Erweiterungen \(\/Ze\) können Sie einen nicht statischen Wert als Adresse einer mit dem **dllimport**\-Modifizierer deklarierten Funktion angeben.  Bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) wird dadurch ein Fehler verursacht.  
  
 Im folgenden Beispiel wird C4232 generiert:  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```