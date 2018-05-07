---
title: 'Wie: Marshallen von Zeichenfolgen mit PInvoke | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a377e7074e72693a1a63e392c64a6d60c5995b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Gewusst wie: Marshallen von Zeichenfolgen mit PInvoke
In diesem Thema wird erläutert, wie systemeigene Funktionen, die Zeichenfolgen im C-Stil können aufgerufen werden, mithilfe der CLR-Zeichenfolge akzeptieren System:: String mithilfe der Plattformaufruf von .NET Framework-Unterstützung. Visual C++-Programmierern werden empfohlen, stattdessen die C++-Interop-Funktionen (wenn möglich), da P/Invoke bietet nur wenig Kompilierzeitfehler reporting, ist nicht typsicher, und kann einfacher zu implementieren. Wenn die nicht verwaltete API wird als DLL verpackt, und der Quellcode nicht verfügbar ist, klicken Sie dann P/Invoke ist die einzige Option, jedoch andernfalls finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Verwaltete und nicht verwaltete Zeichenfolgen werden angeordnet, anders als im Arbeitsspeicher, also die Übergabe von Zeichenfolgen aus verwaltetem zu nicht verwalteten Funktionen erfordert die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut, um den Compiler anzuweisen, fügen Sie die erforderliche Konvertierung Mechanismen für das Marshalling von Zeichenfolgendaten ordnungsgemäß und sicher.  
  
 Wie bei Funktionen, die nur systeminterne Datentypen verwenden <xref:System.Runtime.InteropServices.DllImportAttribute> wird verwendet, um verwaltete Einstiegspunkte in die systemeigenen Funktionen allerdings--für die Übergabe von Zeichenfolgen--anstatt diese Einstiegspunkte als Zeichenfolgen im C-Stil, ein Handle für dauert deklarieren die <xref:System.String> Typ Stattdessen verwendet werden können. Dies fordert den Compiler Code einfügen, der die erforderliche Konvertierung ausführt. Für jedes Funktionsargument in eine nicht verwaltete Funktion, die eine Zeichenfolge akzeptiert die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut sollte verwendet werden, um anzugeben, dass das String-Objekt an die systemeigene Funktion als eine Zeichenfolge im C-Stil gemarshallt werden sollen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code besteht aus einem nicht verwalteten und ein verwaltetes Modul. Nicht verwaltete Modul ist eine DLL, die eine Funktion aufgerufen, die eine C-Stil ANSI-Zeichenfolge in Form von Char * akzeptiert TakesAString definiert. Verwaltete Modul ist eine befehlszeilenanwendung, die die Funktion TakesAString importiert, aber wird definiert als eine verwaltete System.String anstelle von Char dauert\*. Die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut wird verwendet, um anzugeben, wie die verwaltete Zeichenfolge gemarshallt werden sollen, wenn TakesAString aufgerufen wird.  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 Dieses Verfahren wird eine Kopie der Zeichenfolge, die auf dem nicht verwalteten Heap erstellt werden, damit die Änderungen auf die Zeichenfolge von der systemeigenen Funktion nicht in der verwalteten Kopie der Zeichenfolge reflektiert werden.  
  
 Beachten Sie, dass kein Teil der DLL, auf den verwalteten Code über die herkömmliche bereitgestellt wird #include-Direktive. Tatsächlich wird die DLL nur zur Laufzeit zugegriffen, damit Probleme mit Funktionen mit importiert `DllImport` zum Zeitpunkt der Kompilierung nicht erkannt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)