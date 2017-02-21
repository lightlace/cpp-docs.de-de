---
title: "__thiscall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__thiscall"
  - "__thiscall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__thiscall-Schlüsselwort [C++]"
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# __thiscall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Die `__thiscall`\-Aufrufkonvention wird für Memberfunktionen verwendet und ist die Standardaufrufkonvention, die von C\+\+\-Memberfunktionen verwendet wird, die keine variablen Argumente verwenden.  Unter `__thiscall` entleert der Aufgerufene den Stapel, was für `vararg`\-Funktionen nicht möglich ist.  Argumente werden von rechts nach links auf den Stapel geschoben, wobei der `this`\-Zeiger auf der x86\-Architektur über das Register "ECX" übergeben wird, und nicht auf dem Stapel.  
  
 Die Verwendung von `__thiscall` ist in Klassen sinnvoll, deren Memberfunktionen standardmäßig `__clrcall` verwenden.  In diesem Fall können Sie `__thiscall` verwenden, um individuelle Memberfunktionen aus dem systemeigenen Code aufrufbar zu machen.  
  
 Beim Kompilieren mit [\/clr: pure](../build/reference/clr-common-language-runtime-compilation.md) sind alle Funktionen und Funktionszeiger `__clrcall`, sofern nicht anders angegeben.  
  
 In Versionen vor Visual C\+\+ 2005 konnte die thiscall\-Aufrufkonvention nicht explizit in einem Programm angegeben werden, da `thiscall` kein Schlüsselwort war.  
  
 `vararg`\-Memberfunktionen verwenden die `__cdecl`\-Aufrufkonvention.  Alle Funktionsargumente werden auf dem Stapel abgelegt, wobei der `this`\-Zeiger zuletzt auf dem Stapel abgelegt wird.  
  
 Da diese Aufrufkonvention nur für C\+\+ gültig ist, gibt es kein Schema zur C\-Namensergänzung.  
  
 Auf ARM\- und [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Computern wird `__thiscall` vom Compiler akzeptiert und ignoriert.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden.  Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird.  
  
## Beispiel  
  
```  
// thiscall_cc.cpp  
// compile with: /c /clr:oldSyntax  
struct CMyClass {  
   void __thiscall mymethod();  
   void __clrcall mymethod2();  
};  
```  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)