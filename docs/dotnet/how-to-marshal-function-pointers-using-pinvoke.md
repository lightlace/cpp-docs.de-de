---
title: 'Wie: Marshallen von Funktionszeigern mit PInvoke | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cf7f23ea9337b499d4ec80b19e3104074429cc71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Gewusst wie: Marshallen von Funktionszeigern mit PInvoke
In diesem Thema wird erläutert, wie verwaltete Delegaten anstelle von Funktionszeigern verwendet werden können, bei der Interoperation mit Funktionen, die mit .NET Framework P/Invoke-Funktionen nicht verwaltetem. Visual C++-Programmierer sind jedoch empfohlen, stattdessen die C++-Interop-Funktionen (wenn möglich), da P/Invoke bietet nur wenig Kompilierzeitfehler reporting, ist nicht typsicher, und kann einfacher zu implementieren. Wenn die nicht verwaltete API wird als DLL verpackt, und der Quellcode nicht verfügbar ist, ist P/Invoke die einzige Option. Andernfalls finden Sie unter den folgenden Themen:  
  
-   [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Vorgehensweise: Marshallen von Rückrufen und Delegaten mit C++-Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 Nicht verwaltete APIs, die Funktionszeiger verwenden, als Argumente aus verwaltetem Code mit einem verwalteten Delegaten anstelle der systemeigenen Funktionszeiger aufgerufen werden können. Der Compiler automatisch der Delegat, der nicht verwalteten Funktionen als Funktionszeiger gemarshallt und fügt die erforderlichen Übergang von verwaltetem /-Code.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code besteht aus einem nicht verwalteten und ein verwaltetes Modul. Nicht verwaltete Modul ist eine DLL, die eine Funktion aufgerufen, die einen Funktionszeiger akzeptiert TakesCallback definiert. Diese Adresse wird verwendet, um die Funktion auszuführen.  
  
 Das verwaltete Modul definiert einen Delegaten, die vom nativen Code als Funktionszeiger gemarshallt, und verwendet die <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut, um die systemeigenen TakesCallback-Funktion auf den verwalteten Code verfügbar zu machen. In der main-Funktion ist eine Instanz des Delegaten erstellt und an die TakesCallback-Funktion übergeben. Der Programmausgabe veranschaulicht, dass diese Funktion von der systemeigenen TakesCallback-Funktion ausgeführt wird.  
  
 Die verwaltete Funktion unterdrückt Garbagecollection für den verwalteten Delegaten, um zu verhindern, dass .NET Framework Garbagecollection des Delegaten verschieben, während der Ausführung der systemeigenen Funktion.  
  
 Verwaltete Modul mit "/ CLR", aber "/ CLR" kompiliert wird: reine funktioniert ebenfalls. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
```cpp  
// TraditionalDll5.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   /* Declare an unmanaged function type that takes two int arguments  
      Note the use of __stdcall for compatibility with managed code */  
   typedef int (__stdcall *CALLBACK)(int);  
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);  
}  
  
int TakesCallback(CALLBACK fp, int n) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n);  
}  
```  
  
```cpp  
// MarshalDelegate.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
public delegate int GetTheAnswerDelegate(int);  
public value struct TraditionalDLL {  
   [DllImport("TraditionalDLL5.dll")]  
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);  
};  
  
int GetNumber(int n) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
   return x + n;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TraditionalDLL::TakesCallback(fp, 42);  
}  
```  
  
 Beachten Sie, dass kein Teil der DLL bereitgestellt wird, auf den verwalteten Code, der mithilfe der herkömmlichen #include-Direktive. Tatsächlich wird die DLL zur Laufzeit nur zugegriffen, damit Probleme mit Funktionen mit importiert <xref:System.Runtime.InteropServices.DllImportAttribute> zum Zeitpunkt der Kompilierung nicht erkannt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)