---
title: "Gewusst wie: Marshallen von Zeichenfolgen mit PInvoke | Microsoft Docs"
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
  - "Datenmarshalling [C++], Zeichenfolgen"
  - "Interop [C++], Zeichenfolgen"
  - "Marshaling [C++], Zeichenfolgen"
  - "Plattformaufruf [C++], Zeichenfolgen"
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Gewusst wie: Marshallen von Zeichenfolgen mit PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie systemeigene Funktionen, die Zeichenfolgen in C\-Format akzeptieren, über den CLR\-Zeichenfolgentyp System::String aufgerufen werden können, indem die .NET Framework\-Unterstützung für Plattformaufrufe verwendet wird.  Visual C\+\+\-Programmierern wird empfohlen, stattdessen \(sofern möglich\) die C\+\+\-Interop\-Funktionen zu verwenden, da P\/Invoke eine sehr eingeschränkte Berichterstattung von Kompilierungsfehlern bietet, nicht typsicher ist und eine aufwändige Implementierung erfordern kann.  Wenn die nicht verwaltete API als DLL gepackt und der Quellcode nicht verfügbar ist, stellt P\/Invoke die einzige Option dar, andernfalls siehe [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Verwaltete und nicht verwaltete Zeichenfolgen werden im Arbeitsspeicher unterschiedlich angelegt, daher erfordert das Übergeben von Zeichenfolgen von verwalteten an nicht verwaltete Funktionen das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut. Damit wird der Compiler angewiesen, die erforderlichen Konvertierungsmechanismen für das Marshalling der Zeichenfolgedaten korrekt und sicher einzufügen.  
  
 Wie bei Funktionen, die nur systeminterne Datentypen verwenden, wird das <xref:System.Runtime.InteropServices.DllImportAttribute> verwendet, um verwaltete Einstiegspunkte in die systemeigenen Funktionen zu deklarieren. Für die Übergabe von Zeichenfolgen kann anstelle einer Definition dieser Einstiegspunkte für die Übernahme von Zeichenfolgen in C\-Format ein Handle für den <xref:System.String>\-Typ verwendet werden.  Hierdurch wird der Compiler aufgefordert, Code zur Ausführung der erforderlichen Konvertierung einzufügen.  Für jedes Funktionsargument in einer nicht verwalteten Funktion, das eine Zeichenfolge akzeptiert, sollte das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut verwendet werden, um anzugeben, dass das Zeichenfolgenobjekt als Zeichenfolge in C\-Format an die systemeigene Funktion gemarshallt werden soll.  
  
## Beispiel  
 Der folgende Code besteht aus einem verwalteten und einem nicht verwalteten Modul.  Bei dem nicht verwalteten Modul handelt es sich um eine DLL, die eine Funktion mit dem Namen TakesAString definiert, die eine ANSI\-Zeichenfolge in C\-Format als char\* akzeptiert.  Das verwaltete Modul ist eine Befehlszeilenanwendung, von der die TakesAString\-Funktion importiert wird, wobei die Eingabe jedoch nicht als char\*, sondern als verwalteter System.String definiert wird.  Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut wird verwendet, um anzugeben, wie die verwaltete Zeichenfolge beim Aufruf von TakesAString gemarshallt wird.  
  
 Das verwaltete Modul wird mit \/clr kompiliert, es kann jedoch auch \/clr:pure verwendet werden.  
  
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
  
 Bei dieser Technik wird eine Kopie der Zeichenfolge auf dem nicht verwalteten Heap erstellt, daher werden von der systemeigenen Funktion ausgeführte Änderungen der Zeichenfolge in der verwalteten Kopie der Zeichenfolge nicht wiedergegeben.  
  
 Beachten Sie, dass über die herkömmliche \#include\-Direktive kein Teil der DLL für den verwalteten Code verfügbar gemacht wird.  Tatsächlich wird auf die DLL nur zur Laufzeit zugegriffen, sodass Probleme mit Funktionen, die mit `DllImport` importiert wurden, zur Kompilierungszeit nicht erkannt werden.  
  
## Siehe auch  
 [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)