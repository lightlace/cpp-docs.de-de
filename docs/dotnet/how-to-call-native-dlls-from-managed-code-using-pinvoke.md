---
title: "Gewusst wie: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenmarshalling [C++], Aufrufen systemeigener DLLs"
  - "Interop [C++], Aufrufen systemeigener DLLs"
  - "Marshaling [C++], Aufrufen systemeigener DLLs"
  - "Plattformaufruf [C++], Aufrufen systemeigener DLLs"
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Funktionen, die in nicht verwalteten DLLs implementiert sind, können von verwaltetem Code über Plattformaufrufe \(P\/Invoke\) aufgerufen werden.  Wenn der Quellcode für die DLL nicht verfügbar ist, ist P\/Invoke die einzige Option für die Interoperation.  Im Gegensatz zu anderen .NET\-Sprachen stellt Visual C\+\+ jedoch eine Alternative zu P\/Invoke bereit.  Weitere Informationen finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## Beispiel  
 Im folgenden Codebeispiel wird mit der [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385)\-Funktion von Win32 die aktuelle Auflösung des Bildschirms in Pixel abgerufen.  
  
 Bei Funktionen, die als Argumente und Rückgabewerte nur systeminterne Typen verwenden, müssen keine weiteren Aufgaben durchgeführt werden.  Für andere Datentypen wie Funktionszeiger, Arrays und Strukturen sind weitere Attribute erforderlich, um ein ordnungsgemäßes Datenmarshalling sicher zu stellen.  
  
 Obwohl dies nicht erforderlich ist, stellt es eine gute Übung dar, die P\/Invoke\-Deklarationen als statische Member einer Werteklasse zu erstellen. Wie im folgenden Beispiel dargestellt, sind die Deklarationen auf diese Weise nicht im globalen Namespace vorhanden.  
  
```  
// pinvoke_basic.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value class Win32 {  
public:  
   [DllImport("User32.dll")]  
   static int GetSystemMetrics(int);  
  
   enum class SystemMetricIndex {  
      // Same values as those defined in winuser.h.  
      SM_CXSCREEN = 0,  
      SM_CYSCREEN = 1  
   };  
};  
  
int main() {  
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );  
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );  
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);  
}  
```  
  
## Siehe auch  
 [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)