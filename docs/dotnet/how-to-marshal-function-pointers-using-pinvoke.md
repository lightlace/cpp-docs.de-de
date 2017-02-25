---
title: "Gewusst wie: Marshallen von Funktionszeigern mit PInvoke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenmarshalling [C++], Rückrufe und Delegaten"
  - "Interop [C++], Rückrufe und Delegaten"
  - "Marshaling [C++], Rückrufe und Delegaten"
  - "Plattformaufruf [C++], Rückrufe und Delegaten"
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Gewusst wie: Marshallen von Funktionszeigern mit PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie mit P\/Invoke\-Funktionen von .NET Framework verwaltete Delegaten anstelle von Funktionszeigern für die Interoperation mit nicht verwalteten Funktionen verwendet werden können.  Visual C\+\+\-Programmierern wird jedoch empfohlen, stattdessen \(sofern möglich\) die C\+\+\-Interop\-Funktionen zu verwenden, da P\/Invoke eine sehr eingeschränkte Berichterstattung von Kompilierungsfehlern bietet, nicht typsicher ist und eine aufwändige Implementierung erfordern kann.  Wenn die nicht verwaltete API als DLL gepackt und der Quellcode nicht verfügbar ist, stellt P\/Invoke die einzige Option dar.  Beachten Sie andernfalls die folgenden Themen:  
  
-   [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Gewusst wie: Marshallen von Rückrufen und Delegaten mit C\+\+\-Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 Nicht verwaltete APIs, die Funktionszeiger als Argumente übernehmen, können vom verwalteten Code mit einem verwalteten Delegaten anstelle des systemeigenen Funktionszeigers aufgerufen werden.  Vom Compiler werden die Delegaten automatisch als Funktionszeiger zu nicht verwalteten Funktionen gemarshallt, und der erforderliche Übergangscode zwischen verwalteten und nicht verwalteten Funktionen wird eingefügt.  
  
## Beispiel  
 Der folgende Code besteht aus einem nicht verwalteten und einem verwalteten Modul.  Das nicht verwaltete Modul ist eine DLL, die eine Funktion mit dem Namen TakesCallback definiert, die einen Funktionszeiger akzeptiert.  Diese Adresse wird verwendet, um die Funktion auszuführen.  
  
 Das verwaltete Modul definiert einen Delegaten, der als Funktionszeiger zu systemeigenem Code gemarshallt wird, und es verwendet das <xref:System.Runtime.InteropServices.DllImportAttribute>\-Attribut, um die systemeigenen TakesCallback\-Funktion für den verwalteten Code verfügbar zu machen.  In der Hauptfunktion wird eine Instanz des Delegaten erstellt und an die TakesCallback\-Funktion übergeben.  Die Programmausgabe zeigt, dass diese Funktion von der systemeigenen TakesCallback\-Funktion ausgeführt wird.  
  
 Die verwaltete Funktion unterdrückt die Garbage Collection für den verwalteten Delegaten, um das Verschieben des Delegaten durch die .NET Framework\-Garbage Collection während der Ausführung der systemeigenen Funktion zu verhindern.  
  
 Das verwaltete Modul wird mit \/clr kompiliert, es kann jedoch auch \/clr:pure verwendet werden.  
  
```  
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
  
```  
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
  
 Beachten Sie, dass mithilfe der herkömmlichen \#include\-Direktive kein Teil der DLL für den verwalteten Code verfügbar gemacht wird.  Tatsächlich wird auf die DLL nur bei der Ausführung zugegriffen, sodass Probleme mit Funktionen, die mit <xref:System.Runtime.InteropServices.DllImportAttribute> importiert wurden, zur Kompilierungszeit nicht erkannt werden.  
  
## Siehe auch  
 [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)