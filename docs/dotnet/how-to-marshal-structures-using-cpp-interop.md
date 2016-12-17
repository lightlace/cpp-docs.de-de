---
title: "Gewusst wie: Marshallen von Strukturen mit C++-Interop"
ms.custom: na
ms.date: "12/14/2016"
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
  - "C++ Interop, Strukturen"
  - "Datenmarshalling [C++], Strukturen"
  - "Interop [C++], Strukturen"
  - "Marshaling [C++], Strukturen"
  - "Strukturen [C++], Marshalling"
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von Strukturen mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema veranschaulicht einen Aspekt der Visual C\+\+\-Interoperabilität.  Weitere Informationen finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-\#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Diese Funktionen arbeiten jedoch auf dieselbe Weise zusammen, wenn sie in separaten Dateien definiert werden.  Dateien, die ausschließlich nicht verwaltete Funktionen enthalten, müssen nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie eine Struktur sowohl als Verweis als auch als Wert von einer verwalteten Funktion an eine nicht verwaltete Funktion übergeben wird.  Da die Struktur in diesem Beispiel lediglich einfache, systeminterne Datentypen enthält \(siehe [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), ist kein besonderes Marshalling erforderlich.  Informationen zum Marshallen nicht blitfähiger Strukturen, die beispielsweise Zeiger enthalten, finden Sie unter [Gewusst wie: Marshallen von eingebetteten Zeigern mit C\+\+\-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
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
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie eine Struktur sowohl als Verweis als auch als Wert von einer nicht verwalteten Funktion an eine verwaltete Funktion übergeben wird,   Da die Struktur in diesem Beispiel lediglich einfache, systeminterne Datentypen enthält \(siehe [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), ist kein besonderes Marshalling erforderlich.  Informationen zum Marshallen nicht blitfähiger Strukturen, die beispielsweise Zeiger enthalten, finden Sie unter [Gewusst wie: Marshallen von eingebetteten Zeigern mit C\+\+\-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
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
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)