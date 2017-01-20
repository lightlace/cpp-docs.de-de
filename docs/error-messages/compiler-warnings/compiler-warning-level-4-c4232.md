---
title: "Compilerwarnung (Stufe 4) C4232"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4232"
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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