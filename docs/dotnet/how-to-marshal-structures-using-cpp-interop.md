---
title: 'Vorgehensweise: Marshallen von Strukturen mit C++-Interop | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ Interop, structures
- structures [C++], marshaling
- data marshaling [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e135dd1cbfc3aeb164449a1f09e6c1cdf6287582
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215119"
---
# <a name="how-to-marshal-structures-using-c-interop"></a>Gewusst wie: Marshallen von Strukturen mit C++-Interop
In diesem Thema wird veranschaulicht, einen Aspekt der Visual C++-Interoperabilität. Weitere Informationen finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Im folgenden code, Beispiele für die Verwendung der [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Anweisungen zum Implementieren verwaltet und nicht verwaltete Funktionen in der gleichen Datei, aber diese Funktionen auf die gleiche Weise interagieren, wenn in separaten Dateien definiert. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht für die Kompilierung mit [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Struktur an eine nicht verwaltete Funktion, von einer verwalteten übergeben, sowohl als Wert und als Verweis. Da die Struktur in diesem Beispiel nur einfache, systeminterne Datentypen enthält (finden Sie unter [blitfähige und nicht blitfähige Typen](https://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)), kein besonderes Marshalling ist erforderlich. Marshallen von nicht blitfähigen Strukturen, z. B. die, die Zeiger enthalten finden Sie unter [Vorgehensweise: Marshallen eingebetteter Zeiger mithilfe C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
```  
// PassStruct1.cpp  
// compile with: /clr  
  
#include <stdio.h>  
#include <math.h>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
struct Location {  
   int x;  
   int y;  
};  
  
double GetDistance(Location loc1, Location loc2) {  
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   printf_s("[unmanaged] Initializing location...\n");  
   lp->x = 50;  
   lp->y = 50;  
}  
  
#pragma managed  
  
int main() {  
   Location loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   Location loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   Location loc3;  
   InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Übergeben einer Struktur aus einer nicht verwalteten für eine verwaltete Funktion, ein, nach Wert und Verweis. Da die Struktur in diesem Beispiel nur einfache, systeminterne Datentypen enthält (finden Sie unter [blitfähige und nicht blitfähige Typen](https://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)), kein besonderes marshalling ist erforderlich. Marshallen von nicht blitfähigen Strukturen, z. B. die, die Zeiger enthalten finden Sie unter [Vorgehensweise: Marshallen eingebetteter Zeiger mithilfe C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
```  
// PassStruct2.cpp  
// compile with: /clr  
#include <stdio.h>  
#include <math.h>  
using namespace System;  
  
// native structure definition  
struct Location {  
   int x;  
   int y;  
};  
  
#pragma managed  
  
double GetDistance(Location loc1, Location loc2) {  
   Console::Write("[managed] got loc1({0},{1})", loc1.x, loc1.y);  
   Console::WriteLine(" loc2({0},{1})", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   Console::WriteLine("[managed] Initializing location...");  
   lp->x = 50;  
   lp->y = 50;  
}  
  
#pragma unmanaged  
  
int UnmanagedFunc() {  
   Location loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   Location loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   printf_s("(unmanaged) loc1=(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2=(%d,%d)\n", loc2.x, loc2.y);  
  
   double dist = GetDistance(loc1, loc2);  
   printf_s("[unmanaged] distance = %f\n", dist);  
  
   Location loc3;  
   InitLocation(&loc3);  
   printf_s("[unmanaged] got x=%d y=%d\n", loc3.x, loc3.y);  
  
    return 0;  
}  
  
#pragma managed  
  
int main() {  
   UnmanagedFunc();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)