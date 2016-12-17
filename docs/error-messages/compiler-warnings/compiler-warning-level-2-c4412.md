---
title: "Compilerwarnung (Stufe 2) C4412"
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
  - "C4412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4412"
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Funktionssignatur enthält Typ 'Typ'; C\+\+\-Objekte können nicht sicher zwischen reinem und gemischtem oder systemeigenem Code übergeben werden.  
  
 Vom Compiler wurde eine potenziell unsichere Situation entdeckt, die zu einem Laufzeitfehler führen könnte: Eine über dllimport importierte Funktion wird von einer **\/clr:pure**\-Kompiliereinheit aufgerufen, und die Funktionssignatur enthält einen unsicheren Typ.  Ein Typ ist unsicher, wenn er eine Memberfunktion enthält oder ein Datenmember besitzt, das ein unsicherer Typ oder eine Dereferenzierung auf einen unsicheren Typ ist.  
  
 Dies ist aufgrund der unterschiedlichen Standardaufrufkonventionen von reinem und systemeigenem Code \(oder gemischtem systemeigenen und verwaltetem Code\) unsicher.  Stellen Sie beim Importieren einer Funktion \(über `dllimport`\) in eine **\/clr:pure**\-Kompiliereinheit sicher, dass die Deklarationen der einzelnen Typen in der Signatur mit denjenigen in der Kompiliereinheit identisch sind, die die Funktion exportiert \(achten Sie besonders auf die Unterschiede der impliziten Aufrufkonventionen\).  
  
 Eine virtuelle Memberfunktion ist besonders anfällig für unerwartete Ergebnisse.  Es sollten jedoch auch nicht virtuelle Funktionen getestet werden, um sicherzustellen, dass Sie korrekte Ergebnisse erhalten.  Wenn Sie sicher sind, dass Sie korrekte Ergebnisse erhalten, können Sie diese Warnung ignorieren.  
  
 Weitere Information zu **\/clr:pure** finden Sie unter [Gewusst wie: Migrieren auf \/clr:pure](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
 C4412 ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) und [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
 Um diese Warnung zu vermeiden, entfernen Sie alle Funktionen aus dem Typ.  
  
## Beispiel  
 Im folgenden Beispiel wird C4412 generiert.  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## Beispiel  
 Das folgende Beispiel ist eine Headerdatei, in der zwei Typen deklariert werden.  Der `Unsafe`\-Typ ist unsicher, da er eine Memberfunktion besitzt.  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## Beispiel  
 In diesem Beispiel werden Funktionen mit den in der Headerdatei definierten Typen exportiert.  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## Beispiel  
 Die Standardaufrufkonvention in einer **\/clr:pure**\-Kompilierung unterscheidet sich von derjenigen bei einer systemeigenen Kompilierung.  Wenn C4412.h eingeschlossen wird, ist `Test` der Standard für `__clrcall`.  Wenn Sie dieses Programm kompilieren und ausführen \(verwenden Sie nicht **\/c**\), verursacht das Programm eine Ausnahme.  
  
 Im folgenden Beispiel wird C4412 generiert.  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```