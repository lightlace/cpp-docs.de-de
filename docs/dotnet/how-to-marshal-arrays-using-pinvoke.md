---
title: "Gewusst wie: Marshallen von Arrays mit PInvoke | Microsoft Docs"
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
  - "Datenmarshalling [C++], Arrays"
  - "Interop [C++], Arrays"
  - "Marshaling [C++], Arrays"
  - "Plattformaufruf [C++], Arrays"
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Gewusst wie: Marshallen von Arrays mit PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie systemeigene Funktionen, die Zeichenfolgen in C\-Format akzeptieren, über den CLR\-Zeichenfolgentyp <xref:System.String> aufgerufen werden können, indem die .NET Framework\-Unterstützung für Plattformaufrufe verwendet wird.  Visual C\+\+\-Programmierern wird empfohlen, stattdessen \(sofern möglich\) die C\+\+\-Interop\-Funktionen zu verwenden, da P\/Invoke eine sehr eingeschränkte Berichterstattung von Kompilierungsfehlern bietet, nicht typsicher ist und eine aufwändige Implementierung erfordern kann.  Wenn die nicht verwaltete API als DLL gepackt und der Quellcode nicht verfügbar ist, stellt P\/Invoke die einzige Option dar \(andernfalls siehe [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)\).  
  
## Beispiel  
 Da systemeigene und verwaltete Arrays im Speicher unterschiedlich angeordnet sind, erfordert die erfolgreiche Übergabe zwischen verwalteten und nicht verwalteten Funktionen eine Konvertierung oder Marshalling.  In diesem Thema wird dargestellt, wie ein Array aus einfachen \(blitfähigen\) Elementen aus verwaltetem Code an systemeigene Funktionen übergeben werden kann.  
  
 Wie beim Datenmarshalling von verwalteten zu nicht verwalteten Daten allgemein, wird das <xref:System.Runtime.InteropServices.DllImportAttribute>\-Attribut verwendet, um einen verwalteten Einstiegspunkt für jede verwendete systemeigene Funktion zu erstellen.  Für den Fall, dass Funktionen Arrays als Argumente verwenden, muss das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut auch verwendet werden, um dem Compiler anzugeben, wie die Daten gemarshallt werden.  Im folgenden Beispiel wird die <xref:System.Runtime.InteropServices.UnmanagedType>\-Enumeration verwendet, um anzugeben, dass das verwaltete Array als ein Array in C\-Format gemarshallt wird.  
  
 Der folgende Code besteht aus einem nicht verwalteten und einem verwalteten Modul.  Das nicht verwaltete Modul ist eine DLL, die eine Funktion definiert, die ein Array von ganzen Zahlen akzeptiert.  Beim zweiten Modul handelt es sich um eine verwaltete Befehlszeilenanwendung, die diese Funktion importiert, sie jedoch als ein verwaltetes Array definiert. Dabei wird das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut verwendet, um anzugeben, dass das Array beim Aufruf in ein systemeigenes Array konvertiert werden soll.  
  
 Das verwaltete Modul wird mit \/clr kompiliert, es kann jedoch auch \/clr:pure verwendet werden.  
  
```  
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
  
```  
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
  
 Beachten Sie, dass mithilfe der herkömmlichen \#include\-Direktive kein Teil der DLL für den verwalteten Code verfügbar gemacht wird.  Tatsächlich wird auf die DLL nur bei der Ausführung zugegriffen, sodass Probleme mit Funktionen, die mit <xref:System.Runtime.InteropServices.DllImportAttribute> importiert wurden, zur Kompilierungszeit nicht erkannt werden.  
  
## Siehe auch  
 [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)