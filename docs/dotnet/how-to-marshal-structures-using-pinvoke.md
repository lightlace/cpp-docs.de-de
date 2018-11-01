---
title: 'Gewusst wie: Marshallen von Strukturen mit PInvoke'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
ms.openlocfilehash: e79eb343f81cf2d66e394be7561d2c9727c4c9ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429109"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Gewusst wie: Marshallen von Strukturen mit PInvoke

In diesem Dokument wird erläutert, wie native Funktionen, akzeptieren die C-Stil Strukturen aus verwalteten Funktionen durch mit P/Invoke aufgerufen werden können. Obwohl es wird empfohlen, dass Sie die C++-Interop-Funktionen nicht verwenden P/Invoke da P/Invoke wenig Fehler während der Kompilierung, berichterstellung, bietet ist nicht typsicher, und kann mühsam sein, wenn die nicht verwaltete API als DLL verpackt wird und der Quellcode nicht ist zu implementieren, P/Invoke verfügbar ist, ist die einzige Option. Andernfalls finden Sie unter den folgenden Dokumenten:

- [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Vorgehensweise: Marshallen von Zeichenfolgen mit PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)

Standardmäßig werden systemeigene und verwaltete Strukturen unterschiedlich im Arbeitsspeicher angeordnet erfolgreich zusätzliche Schritte, um die Datenintegrität beizubehalten übergeben von Strukturen über die verwalteten und nicht verwalteten Grenze erfordert werden.

Dieses Dokument erläutert die erforderlichen Schritte zum Definieren der verwalteter Entsprechungen der systemeigenen Strukturen und wie die so erhaltenen Strukturen an nicht verwaltete Funktionen übergeben werden können. In diesem Dokument wird vorausgesetzt, dass einfache Strukturen, die, die keine Zeichenfolgen oder Zeiger enthalten – verwendet werden. Informationen über die Interoperabilität von nicht blitfähigen finden Sie unter [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke sind keine nicht blitfähige Typen als Rückgabewert. Blitfähige Typen haben die gleiche Darstellung in verwaltetem und nicht verwaltetem Code. Weitere Informationen finden Sie unter [blitfähige und nicht blitfähige Typen](/dotnet/framework/interop/blittable-and-non-blittable-types).

Marshallen von einfachen blitfähigen Strukturen über die verwalteten und nicht verwalteten Grenze erfordert, dass verwalteten Versionen der einzelnen systemeigenen Struktur definiert werden. Diese Strukturen, können alle gültigen Namen haben. Es gibt keine Beziehung zwischen der nativen und verwalteten Version der beiden Strukturen als ihr Datenlayout. Aus diesem Grund ist es wichtig, dass die verwaltete Version Felder enthält, die gleiche Größe und in der gleichen Reihenfolge wie die native Version. (Es gibt keinen Mechanismus dafür, dass die verwalteten und systemeigenen Versionen der Struktur äquivalent sind, damit Inkompatibilitäten nicht offensichtlich bis zur Laufzeit werden soll. Es ist der Programmierer dafür verantwortlich sicherzustellen, dass die beiden Strukturen das gleiche Layout verfügen.)

Da die Elemente der verwaltete Strukturen manchmal zur leistungsverbesserung neu angeordnet werden, ist es erforderlich, verwenden die <xref:System.Runtime.InteropServices.StructLayoutAttribute> Attribut, um anzugeben, dass die Struktur nacheinander angeordnet sind. Es ist auch eine gute Idee, die die Struktur, Packen die Einstellung identisch, die von der systemeigenen Struktur verwendet werden kann explizit festgelegt. (Zwar wird standardmäßig verwendet Visual C++ eine 8-Byte-Struktur, die für sowohl verwalteten Code zu verpacken.)

1. Verwenden Sie als Nächstes <xref:System.Runtime.InteropServices.DllImportAttribute> zum Deklarieren von Einstiegspunkten, die nicht verwaltete Funktionen zu entsprechen, die die Struktur zu akzeptieren, aber verwenden die verwaltete Version der Struktur in den Funktionssignaturen, die Funktionssignaturen ist, wenn Sie den gleichen Namen für beide Versionen verwenden die -Struktur.

1. Jetzt kann verwalteter Code die verwaltete Version der Struktur, die nicht verwaltete Funktionen übergeben, als wären sie tatsächlich verwalteten Funktionen sind. Diese Strukturen können als Wert oder als Verweis übergeben werden, wie im folgenden Beispiel gezeigt.

## <a name="example"></a>Beispiel

Der folgende Code besteht aus einer nicht verwalteten und ein verwaltetes Modul. Das nicht verwaltete Modul handelt es sich um eine DLL, die eine Struktur, die aufgerufen wird, Speicherort und eine Funktion namens GetDistance, die akzeptiert zwei Instanzen die Speicherort-Struktur definiert. Das zweite Modul ist eine verwaltete befehlszeilenanwendung, die die GetDistance-Funktion importiert, aber in Bezug auf eine verwaltete Entsprechung der Location-Struktur, MLocation definiert. In der Praxis würde wahrscheinlich der gleiche Namen für beide Versionen der Struktur verwendet werden; Allerdings wird hier ein anderen Namen verwendet, um zu veranschaulichen, dass der Prototyp DllImport in Bezug auf die verwaltete Version definiert ist.

Beachten Sie, dass kein Teil der DLL verfügbar gemacht wird, auf den verwalteten Code mithilfe der herkömmlichen #include-Anweisung. In der Tat ist die DLL zur Laufzeit nur zugegriffen, sodass Probleme mit Funktionen, die mit DllImport importiert wurden, zum Zeitpunkt der Kompilierung nicht erkannt werden.

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
