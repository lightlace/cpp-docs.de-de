---
title: 'Vorgehensweise: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c1e3d9d3d08ef0386a1ab85e0e5b6860f5d504cc
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681280"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Gewusst wie: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke
Funktionen, die in nicht verwaltete DLLs implementiert sind, können in verwaltetem Code mithilfe von Plattformaufruf (P/Invoke) Funktionen aufgerufen werden. Wenn der Quellcode für die DLL nicht verfügbar ist, ist P/Invoke die einzige Option für die Interoperation. Im Gegensatz zu anderen .NET-Sprachen bietet Visual C++ jedoch eine Alternative zum P/Invoke. Weitere Informationen finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mithilfe der Win32- [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics) Funktion zum Abrufen der aktuellen Auflösung des Bildschirms in Pixel.  
  
 Für Funktionen, die nur systeminterne Typen als Argumente und Rückgabewerte verwenden, ist kein zusätzlicher Aufwand erforderlich. Andere Datentypen, z. B. Funktionszeiger, Arrays und Strukturen, erfordern zusätzliche Attribute, um sicherzustellen, dass der richtige Daten-Marshalling.  
  
 Obwohl es nicht erforderlich ist, ist es empfiehlt sich, die P/Invoke-Deklarationen, statische Member einer Wertklasse vornehmen, damit sie in den globalen Namespace nicht vorhanden sind, wie im folgenden Beispiel veranschaulicht.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)