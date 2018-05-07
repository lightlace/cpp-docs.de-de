---
title: 'Wie: Marshallen von Strukturen mit C++-Interop | Microsoft Docs'
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
ms.openlocfilehash: 312fef089262c7e21285d1e3a1fb79de65264d7c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-structures-using-c-interop"></a>Gewusst wie: Marshallen von Strukturen mit C++-Interop
Dieses Thema veranschaulicht einen Aspekt der Visual C++-Interoperabilität. Weitere Informationen finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Im folgenden Codebeispiel Beispiele verwenden die [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Direktiven zum Implementieren verwalteten und nicht verwaltete Funktionen in derselben Datei, aber diese Funktionen auf dieselbe Weise zusammenarbeiten, wenn in separaten Dateien definiert. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht kompiliert werden [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, eine Struktur von einer verwalteten an eine nicht verwaltete Funktion übergeben, sowohl als Wert und als Verweis. Da die Struktur in diesem Beispiel wird nur die einfache, systeminterne Datentypen enthält (finden Sie unter [blitfähige und nicht blitfähige Typen](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)), keine besondere Marshalling erforderlich ist. Marshallen von blitfähige Strukturen, z. B. solche, die Zeiger enthalten finden Sie unter [wie: Marshallen eingebetteter Zeiger mithilfe von C++-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
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
 Im folgende Beispiel wird veranschaulicht, eine Struktur aus einem nicht verwalteten an eine verwaltete Funktion übergeben wird sowohl als Wert und als Verweis. Da die Struktur in diesem Beispiel wird nur die einfache, systeminterne Datentypen enthält (siehe [blitfähige und nicht blitfähige Typen](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)), kein besonderes marshalling erforderlich ist. Marshallen von blitfähige Strukturen, z. B. solche, die Zeiger enthalten finden Sie unter [wie: Marshallen eingebetteter Zeiger mithilfe von C++-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
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