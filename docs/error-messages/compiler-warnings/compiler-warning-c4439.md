---
title: "Compilerwarnung C4439 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4439"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4439"
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung C4439
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Die Funktionsdefinition mit einem verwalteten Typ in der Signatur muss eine \_\_clrcall\-Aufrufkonvention aufweisen  
  
 Der Compiler hat eine Aufrufkonvention implizit mit [\_\_clrcall](../../cpp/clrcall.md) ersetzt.  Um diese Warnung zu vermeiden, entfernen Sie die `__cdecl`\-Aufrufkonvention oder die `__stdcall`\-Aufrufkonvention.  
  
 C4439 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit `#pragma warning` oder **\/wd** deaktivieren. Weitere Informationen finden Sie unter [warning](../../preprocessor/warning.md) oder [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../../build/reference/compiler-option-warning-level.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4439 generiert.  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```