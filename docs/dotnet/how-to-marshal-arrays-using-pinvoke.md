---
title: 'Wie: Marshallen von Arrays mit PInvoke | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3694d6628005c49cc824e52d710e64e060822f96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Gewusst wie: Marshallen von Arrays mit PInvoke
In diesem Thema wird erläutert, wie systemeigene Funktionen, die Zeichenfolgen im C-Stil können aufgerufen werden, mithilfe der CLR-Zeichenfolgentyp akzeptieren <xref:System.String> mithilfe der Plattformaufruf von .NET Framework-Unterstützung. Visual C++-Programmierern werden empfohlen, stattdessen die C++-Interop-Funktionen (wenn möglich), da P/Invoke bietet nur wenig Kompilierzeitfehler reporting, ist nicht typsicher, und kann einfacher zu implementieren. Wenn die nicht verwaltete API wird als DLL verpackt, und der Quellcode nicht verfügbar ist, ist P/Invoke die einzige Option (andernfalls finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).  
  
## <a name="example"></a>Beispiel  
 Systemeigenen und verwalteten Arrays im Arbeitsspeicher anders angeordnet sind, Quellformat, sodass sie erfolgreich die Apartmentgrenze verwalteten und unverwalteten übergeben Konvertierung oder Marshalling. In diesem Thema wird veranschaulicht, wie ein Array von einfachen (blitfähigen) Elementen an systemeigener Funktionen aus verwaltetem Code übergeben werden kann.  
  
 Als "true" von verwaltetem/Daten-Marshalling im Allgemeinen ist die <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut wird verwendet, um einen verwalteten Einstiegspunkt für jede systemeigene Funktion erstellen, die verwendet werden. Im Fall von Funktionen, die Arrays als Argumente akzeptieren die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut muss ebenfalls verwendet werden, um für den Compiler anzugeben, wie die Daten gemarshallt werden. Im folgenden Beispiel die <xref:System.Runtime.InteropServices.UnmanagedType> Enumeration wird verwendet, um anzugeben, dass die verwalteten Arrays als ein Array im C-Format gemarshallt werden.  
  
 Der folgende Code besteht aus einem nicht verwalteten und ein verwaltetes Modul. Nicht verwaltete Modul ist eine DLL, die eine Funktion definiert, die ein Array von ganzen Zahlen akzeptiert. Das zweite Modul ist eine verwaltete-befehlszeilenanwendung, die diese Funktion herstellen, aber wird im Hinblick auf ein verwaltetes Array definiert und verwendet die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut, um anzugeben, dass das Array in ein systemeigenes Array beim Aufruf konvertiert werden soll.  
  
 Verwaltete Modul mit "/ CLR", aber "/ CLR" kompiliert wird: reine funktioniert ebenfalls. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
```cpp  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```cpp  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 Beachten Sie, dass kein Teil der DLL, auf den verwalteten Code mithilfe der herkömmlichen bereitgestellt wird #include-Direktive. In der Tat, da die DLL zur Laufzeit nur erfolgt, Probleme bei Funktionen mit importiert <xref:System.Runtime.InteropServices.DllImportAttribute> zum Zeitpunkt der Kompilierung nicht erkannt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)