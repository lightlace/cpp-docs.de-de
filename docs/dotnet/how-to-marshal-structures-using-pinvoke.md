---
title: 'Wie: Marshallen von Strukturen mit PInvoke | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4ff1801c9bb2de06ae2717e8f69bcd39fdf3bc98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Gewusst wie: Marshallen von Strukturen mit PInvoke
Dieses Dokument wird erläutert, wie systemeigene Funktionen, die Strukturen im C-Format von von verwalteten Funktionen aufgerufen werden können, mit P/Invoke akzeptieren. Obwohl wir empfehlen die Verwendung von C++-Interop-Features anstelle von können P/Invoke da P/Invoke wenig Kompilierzeitfehler reporting, bietet nicht typsicher, und einfacher zu implementieren, wenn die nicht verwaltete API als DLL verpackt wird und der Quellcode nicht, P/Invoke verfügbar ist, ist die einzige Option. Andernfalls finden Sie unter den folgenden Dokumenten:  
  
-   [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
  
-   [Vorgehensweise: Marshallen von Zeichenfolgen mit PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)
  
 Standardmäßig werden systemeigene und verwaltete Strukturen unterschiedlich im Arbeitsspeicher angeordnet erfolgreich übergeben von Strukturen Apartmentgrenze verwalteten und unverwalteten zusätzliche Schritte, um die Datenintegrität beizubehalten erfordert.  
  
 Dieses Dokument erläutert die erforderlichen Schritte zum Definieren der verwalteter Entsprechungen der systemeigenen Strukturen und wie die resultierenden Strukturen an nicht verwaltete Funktionen übergeben werden können. Dieses Dokument setzt voraus, dass einfache Strukturen – diejenigen, die keine Zeichenfolgen oder Zeiger enthalten – verwendet werden. Informationen zur Interoperabilität blitfähige finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke sind keine nicht blitfähige Typen als Rückgabewert. Blitfähige Typen verfügen über die gleiche Darstellung in verwaltetem und nicht verwaltetem Code. Weitere Informationen finden Sie unter [blitfähige und nicht blitfähige Typen](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3).  
  
 Marshallen von einfachen blitfähige Strukturen Apartmentgrenze verwalteten und unverwalteten erfordert, dass verwaltete Versionen aller systemeigenen Strukturen definiert werden. Diese Strukturen können gültigen Namen haben. Es gibt keine Beziehung zwischen der systemeigenen und verwalteten Version von beiden Strukturen als ihr Datenlayout. Daher ist es wichtig, dass die verwaltete Version Felder enthält, die die gleiche Größe und in der gleichen Reihenfolge wie die native Version sind. (Es gibt keinen Mechanismus zum sicherstellen, dass die verwalteten und systemeigenen Versionen der Struktur äquivalent sind, damit Inkompatibilitäten nicht offensichtlich bis zur Laufzeit werden soll. Es dem Programmierer ist dafür verantwortlich sicherzustellen, dass die beiden Strukturen dasselbe Datenlayout haben.)  
  
 Da die Member des verwalteten Strukturen manchmal zur leistungsverbesserung neu angeordnet werden, ist es notwendig, verwenden die <xref:System.Runtime.InteropServices.StructLayoutAttribute> Attribut, um anzugeben, dass die Struktur sequenziell angelegt werden. Es ist auch eine gute Idee, die die Struktur Packen Einstellung identisch, die von der systemeigenen Struktur verwendet werden kann explizit festzulegen. (Zwar wird standardmäßig verwendet Visual C++ eine 8-Byte-Struktur, die für sowohl verwalteten Code packen.)  
  
1.  Verwenden Sie als Nächstes <xref:System.Runtime.InteropServices.DllImportAttribute> Einstiegspunkte, die nicht verwalteten Funktionen entsprechen, die die Struktur akzeptieren deklarieren, aber verwenden Sie die verwaltete Version der Struktur in den Funktionssignaturen Funktionssignaturen ist, wenn Sie den gleichen Namen für beide Versionen verwenden die -Struktur.  
  
2.  Jetzt kann verwalteter Code die verwaltete Version der Struktur an die nicht verwalteten Funktionen übergeben, als wären sie tatsächlich verwaltete Funktionen sind. Diese Strukturen können als Wert oder als Verweis übergeben werden, wie im folgenden Beispiel gezeigt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code besteht aus einem nicht verwalteten und ein verwaltetes Modul. Nicht verwaltete Modul ist eine DLL, die eine Struktur, die aufgerufen werden, Speicherort und eine Funktion namens GetDistance, das akzeptiert, zwei Instanzen der Speicherort-Struktur definiert. Das zweite Modul ist eine verwaltete befehlszeilenanwendung, die importiert der GetDistance-Funktion, aber es im Hinblick auf eine verwaltete Entsprechung der Speicherort-Struktur MLocation definiert. In der Praxis würden die gleiche Namen wahrscheinlich für beide Versionen der Struktur verwendet werden. Allerdings wird hier ein anderen Namen verwendet, um zu veranschaulichen, dass das DllImport-Prototyp im Hinblick auf die verwaltete Version definiert ist.  
  
 Beachten Sie, dass kein Teil der DLL bereitgestellt wird, auf den verwalteten Code, der mithilfe der herkömmlichen #include-Direktive. Tatsächlich wird die DLL zur Laufzeit nur zugegriffen, sodass Probleme mit Funktionen, die mit DllImport importiert wurden, zum Zeitpunkt der Kompilierung nicht erkannt werden.  
  
```  
// TraditionalDll3.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#include <stdio.h>  
#include <math.h>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
   #define TRADITIONALDLL_API __declspec(dllexport)  
#else  
   #define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct Location {  
   int x;  
   int y;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API double GetDistance(Location, Location);  
   TRADITIONALDLL_API void InitLocation(Location*);  
}  
  
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
```  
  
## <a name="example"></a>Beispiel  
  
```  
// MarshalStruct_pi.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MLocation {  
   int x;  
   int y;  
};  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL3.dll")]  
   static public double GetDistance(MLocation, MLocation);  
   [DllImport("TraditionalDLL3.dll")]  
   static public double InitLocation(MLocation*);  
};  
  
int main() {  
   MLocation loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   MLocation loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = TraditionalDLL::GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   MLocation loc3;  
   TraditionalDLL::InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
```Output  
[unmanaged] loc1(0,0) loc2(100,100)  
[managed] distance = 141.42135623731  
[unmanaged] Initializing location...  
[managed] x=50 y=50  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
