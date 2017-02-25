---
title: "Compilerwarnung (Stufe 1) C4297 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4297"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4297"
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4297
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Funktion“: Die Funktion löst eine unerwartete Ausnahme aus  
  
 Eine Funktionsdeklaration enthält einen \(möglicherweise impliziten\) `noexcept`\-Bezeichner, einen leeren `throw`\-Ausnahmebezeichner oder ein [\_\_declspec\(nothrow\)](../../cpp/nothrow-cpp.md)\-Attribut, und die Definition enthält eine oder mehrere [throw](../../cpp/try-throw-and-catch-statements-cpp.md)\-Anweisungen.  Um C4297 zu beheben, versuchen Sie nicht, Ausnahmen in Funktionen auszulösen, die als `__declspec(nothrow)`, `noexcept(true)` oder `throw()` deklariert sind.  Alternativ können Sie die `noexcept`\-, `throw()`\- oder `__declspec(nothrow)`\-Spezifikation entfernen.  
  
 Standardmäßig generiert der Compiler implizite `noexcept(true)`\-Bezeichner für benutzerdefinierte Destruktoren und Deallocator\-Funktionen und vom Compiler generierte spezielle Memberfunktionen.  Dies entspricht dem ISO\-Standard C\+\+11.  Um die Generierung impliziter Noexcept\-Bezeichner zu verhindern und für den Compiler das nicht standardmäßige Verhalten von Visual Studio 2013 wiederherzustellen, verwenden Sie die **\/Zc:implicitNoexcept\-**\-Compileroption.  Weitere Informationen finden Sie unter [\/Zc:implicitNoexcept \(implizite Ausnahmespezifizierer\)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).  
  
 Weitere Informationen zu Ausnahmespezifikationen finden Sie unter [Ausnahmespezifikationen \(throw\)](../../cpp/exception-specifications-throw-cpp.md).  Informationen zum Ändern des Verhaltens für die Behandlung von Ausnahmen zur Kompilierungszeit finden Sie auch unter [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md)  
  
 Diese Warnung wird auch für \_\_declspec\([dllexport](../../cpp/dllexport-dllimport.md)\)\-Funktionen generiert, die als extern „C“ gekennzeichnet sind, auch wenn es sich um C\+\+\-Funktionen handelt.  
  
 Im folgenden Beispiel wird C4297 generiert:  
  
```  
// C4297.cpp  
// compile with: /W1 /LD  
void __declspec(nothrow) f1()   // declared nothrow  
// try the following line instead  
// void f1()  
{  
   throw 1;   // C4297  
}  
```