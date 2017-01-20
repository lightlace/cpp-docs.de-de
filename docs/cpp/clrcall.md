---
title: "__clrcall"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__clrcall"
  - "__clrcall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__clrcall-Schlüsselwort [C++]"
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# __clrcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Gibt an, dass eine Funktion nur aus verwaltetem Code aufgerufen werden kann.  Verwenden Sie `__clrcall` für alle virtuellen Funktionen, die nur aus verwaltetem Code aufgerufen werden.  Allerdings kann diese Aufrufkonvention nicht für Funktionen verwendet werden, die vom systemeigenen Code aufgerufen werden.  
  
 Verwenden Sie `__clrcall`, um die Leistung zu verbessern, wenn aus einer verwalteten Funktion eine virtuelle verwaltete Funktion oder aber aus einer verwalteten Funktion ein verwalteter Funktionszeiger aufgerufen wird.  
  
 Einstiegspunkte sind separate, vom Compiler generierte Funktionen.  Wenn eine Funktion sowohl über die systemeigenen als auch über verwaltete Einstiegspunkte verfügt, ist eine von ihnen die tatsächliche Funktion mit der Funktionsimplementierung.  Die andere Funktion ist eine separate Funktion \(ein Thunk\), welche die tatsächliche Funktion aufruft und die Common Language Runtime PInvoke ausführen lässt.  Wenn Sie eine Funktion als `__clrcall` markieren, geben Sie an, dass die Funktionsimplementierung MSIL sein muss und dass die systemeigene Einstiegspunktfunktion nicht generiert wird.  
  
 Wenn `__clrcall` nicht angegeben ist und die Adresse einer systemeigenen Funktion verwendet wird, verwendet der Compiler den systemeigenen Einstiegspunkt.  `__clrcall` gibt an, dass die Funktion verwaltet wird und keine Notwendigkeit besteht, den Übergang von verwaltet zu systemeigen zu durchlaufen.  In diesem Fall verwendet der Compiler den verwalteten Einstiegspunkt.  
  
 Wenn **\/clr** \(nicht **\/clr:pure** oder **\/clr:safe**\) verwendet und `__clrcall` nicht verwendet wird, wird für die Adresse einer Funktion immer die Adresse des Einstiegspunkts der systemeigenen Funktion zurückgegeben.  Wenn `__clrcall` verwendet wird, wird der Einstiegspunkt der systemeigenen Funktion nicht erstellt. Daher wird die Adresse der verwalteten Funktion und keine Einstiegspunkt\-Thunkfunktion zurückgegeben.  Weitere Informationen finden Sie unter [Doppeltes Thunking](../dotnet/double-thunking-cpp.md).  
  
 [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) bedeutet, dass alle Funktionen und Funktionszeiger `__clrcall` sind und der Compiler nicht erlaubt, dass eine Funktion in der Kompiliereinheit anders als mit `__clrcall` markiert ist.  Wenn **\/clr:pure** verwendet wird, kann `__clrcall` nur für Funktionszeiger und externe Deklarationen angegeben werden.  
  
 Sie können `__clrcall`\-Funktionen von existierendem C\+\+\-Code, der kompiliert wurde, indem **\/clr** verwendet wurde, direkt aufrufen, sofern diese Funktion eine MSIL\-Implementierung aufweist.  `__clrcall`\-Funktionen können nicht direkt von den Funktionen aufgerufen werden, die Inline\-ASM haben und z. B. CPU\-spezifische Systeminterna aufrufen, auch wenn diese Funktionen mit **\/clr** kompiliert werden.  
  
 `__clrcall`\-Funktionszeiger sollen nur in der Anwendungsdomäne verwendet werden, in der sie erstellt wurden.  Anstatt `__clrcall`\-Funktionszeiger über Anwendungsdomänen hinweg zu übergeben, verwenden Sie <xref:System.CrossAppDomainDelegate>.  Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
## Beispiel  
  
```  
// clrcall.cpp  
// compile with: /clr:oldSyntax /LD  
void __clrcall Test1( ) {}  
void (__clrcall *fpTest1)( ) = &Test1;  
```  
  
## Beispiel  
 Beachten Sie, dass Code nach Bedarf generiert wird, wenn eine Funktion mit `__clrcall` deklariert wird. Dies ist beispielsweise der Fall, wenn eine Funktion aufgerufen wird.  
  
```  
// clrcall2.cpp  
// compile with: /clr  
using namespace System;  
int __clrcall Func1() {  
   Console::WriteLine("in Func1");  
   return 0;  
}  
  
// Func1 hasn't been used at this point (code has not been generated),   
// so runtime returns the adddress of a stub to the function  
int (__clrcall *pf)() = &Func1;  
  
// code calls the function, code generated at difference address  
int i = pf();   // comment this line and comparison will pass  
  
int main() {  
   if (&Func1 == pf)  
      Console::WriteLine("&Func1 == pf, comparison succeeds");  
   else   
      Console::WriteLine("&Func1 != pf, comparison fails");  
  
   // even though comparison fails, stub and function call are correct  
   pf();  
   Func1();  
}  
```  
  
  **in Func1**  
**&Func1 \!\= pf schlägt der Vergleich fehl**  
**in Func1**  
**in Func1**   
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Funktionszeiger so definiert werden kann, dass deklariert wird, dass der Funktionszeiger nur von verwaltetem Code aufgerufen wird.  Dies ermöglicht es dem Compiler, die verwaltete Funktion direkt aufzurufen und den systemeigenen Einstiegspunkt \(doppeltes Thunk\-Problem\) zu vermeiden.  
  
```  
// clrcall3.cpp  
// compile with: /clr  
void Test() {  
   System::Console::WriteLine("in Test");  
}  
  
int main() {  
   void (*pTest)() = &Test;  
   (*pTest)();  
  
   void (__clrcall *pTest2)() = &Test;  
   (*pTest2)();  
}  
```  
  
## Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)