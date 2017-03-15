---
title: "Compilerwarnung (Stufe 3) C4290 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4290"
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 3) C4290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Ausnahmespezifikation ignoriert, es sei denn, es wird angezeigt, dass eine Funktion nicht \_\_declspec\(nothrow\) ist  
  
 Eine Funktion wurde mit einer Ausnahmespezifikation deklariert, die von Visual C\+\+ zwar akzeptiert, nicht aber implementiert wird.  Code, der mit nicht berücksichtigten Ausnahmespezifikationen kompiliert wurde, muss für zukünftige Versionen, die Ausnahmespezifikationen unterstützen, möglicherweise neu kompiliert und verknüpft werden.  
  
 Weitere Informationen finden Sie unter [Ausnahmespezifikationen \(throw\)](../../cpp/exception-specifications-throw-cpp.md).  
  
 Sie können diese Warnung vermeiden, indem Sie das Pragma [warning](../../preprocessor/warning.md) verwenden:  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 Im folgenden Codebeispiel wird C4290 generiert:  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```