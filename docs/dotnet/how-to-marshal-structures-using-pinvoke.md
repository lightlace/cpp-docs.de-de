---
title: "Gewusst wie: Marshallen von Strukturen mit PInvoke"
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
  - "Datenmarshalling [C++], Strukturen"
  - "Interop [C++], Strukturen"
  - "Marshaling [C++], Strukturen"
  - "Plattformaufruf [C++], Strukturen"
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
caps.latest.revision: 30
caps.handback.revision: "28"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von Strukturen mit PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird erläutert, wie systemeigene Funktionen, die Zeichenfolgen im C\-Format akzeptieren, von verwalteten Funktionen aufgerufen werden können, indem mithilfe von P\/Invoke eine Instanz von <xref:System.String> bereitgestellt wird.  Auch wenn empfohlen wird, anstelle von P\/Invoke die C\+\+\-Interop\-Funktionen zu verwenden, da P\/Invoke nur eine eingeschränkte Berichterstattung zu Kompilierungsfehlern bietet, nicht typsicher ist und eine aufwändige Implementierung erfordern kann, ist P\/Invoke die einzige Option, wenn die nicht verwaltete API als DLL verpackt wird und der Quellcode nicht verfügbar ist.  Andernfalls finden Sie in den folgenden Dokumenten Informationen:  
  
-   [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [How to: Marshal Structures Using PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
 In der Standardeinstellung werden systemeigene und verwaltete Strukturen im Speicher unterschiedlich angelegt. Die ordnungsgemäße Übergabe von Strukturen über verwaltete\/nicht verwaltete Grenzen hinweg erfordert somit zusätzliche Schritte, um eine Datenintegrität sicherzustellen.  
  
 In diesem Dokument wird erläutert, welche Schritte nötig sind, um verwaltete Äquivalente systemeigener Strukturen zu definieren, und wie die sich daraus ergebenden Strukturen an nicht verwaltete Funktionen übergeben werden können.  In diesem Dokument wird von der Verwendung einfacher Strukturen ausgegangen, die weder Zeichenfolgen noch Zeiger enthalten.  Informationen zur nicht blitfähigen Interoperabilität finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  P\/Invoke kann keine blitfähigen Typen als Rückgabewert besitzen.  Blitfähige Typen werden in verwaltetem und nicht verwaltetem Code identisch dargestellt.  Weitere Informationen finden Sie unter [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md).  
  
 Das Marshallen von einfachen, blitfähigen Strukturen über verwaltete\/nicht verwaltete Grenzen hinweg erfordert, dass verwaltete Versionen aller systemeigenen Strukturen definiert sind.  Diese Strukturen können einen beliebigen gültigen Namen haben. Es gibt keine Beziehung zwischen der systemeigenen und der verwalteten Version zweier Strukturen außer deren Datenlayout.  Daher ist es wichtig, dass die verwaltete Version Felder enthält, die dieselbe Größe haben und sich in derselben Reihenfolge befinden wie in der systemeigenen Version. \(Es gibt keinen Mechanismus, der garantiert, dass die verwaltete und die systemeigene Version der Struktur äquivalent sind. Inkompatibilitäten kommen somit erst bei der Ausführung zum Vorschein.  Es liegt in der Verantwortung des Programmierers, dass beide Strukturen über das gleiche Datenlayout verfügen.\)  
  
 Da die Member verwalteter Strukturen aus Gründen der Leistung gelegentlich neu angeordnet werden, ist die Verwendung des Attributs <xref:System.Runtime.InteropServices.StructLayoutAttribute> notwendig, um anzuzeigen, dass die Strukturen sequenziell angelegt werden.  Es ist außerdem empfehlenswert, die Ausrichtungseinstellung der Struktur explizit festzulegen, damit diese mit der von der systemeigenen Struktur verwendeten identisch ist \(auch wenn Visual C\+\+ in der Standardeinstellung eine 8\-Byte\-Strukturausrichtung für verwalteten Code verwendet\).  
  
1.  Verwenden Sie als Nächstes <xref:System.Runtime.InteropServices.DllImportAttribute>, um Einstiegspunkte zu deklarieren, die allen nicht verwalteten Funktionen entsprechen, welche die Struktur akzeptieren, in den Funktionssignaturen jedoch die verwaltete Version der Struktur verwenden. Dies ist ein strittiger Punkt, wenn Sie für beide Versionen der Struktur denselben Namen verwenden.  
  
2.  Verwalteter Code kann nun die verwaltete Version der Struktur an die nicht verwalteten Funktionen so übergeben, als seien sie tatsächlich verwaltete Funktionen.  Diese Strukturen können entweder als Wert oder als Referenz übergeben werden, wie im folgenden Beispiel erläutert wird.  
  
## Beispiel  
 Der folgende Code besteht aus einem nicht verwalteten und einem verwalteten Modul.  Das nicht verwaltete Modul ist eine DLL, in der eine Struktur mit dem Namen "Location" sowie eine Funktion mit dem Namen "GetDistance" definiert wird. Diese Funktion akzeptiert zwei Instanzen der Struktur "Location".  Das zweite Modul ist eine verwaltete Befehlszeilenanwendung, die die Funktion "GetDistance" importiert, diese jedoch in Ausdrücken eines verwalteten Äquivalents der Struktur "Location" \(MLocation\) definiert.  In der Praxis würde für beide Versionen der Struktur möglicherweise derselbe Name verwendet werden. In diesem Beispiel wird jedoch ein anderer Name verwendet, um zu zeigen, dass der DllImport\-Prototyp in Ausdrücken der verwalteten Version definiert wird.  
  
 Das verwaltete Modul wird mit \/clr kompiliert, es kann jedoch auch \/clr:pure verwendet werden.  
  
 Beachten Sie, dass mithilfe der herkömmlichen \#include\-Direktive kein Teil der DLL für den verwalteten Code verfügbar gemacht wird.  Tatsächlich wird auf die DLL nur bei der Ausführung zugegriffen, sodass Probleme mit Funktionen, die mit DllImport importiert wurden, zur Kompilierungszeit nicht erkannt werden.  
  
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
  
## Beispiel  
  
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
  
  **\[unmanaged\] loc1\(0,0\) loc2\(100,100\)**  
**\[managed\] distance \= 141.42135623731**  
**\[unmanaged\] Initializing location...**  
**\[managed\] x\=50 y\=50**   
## Siehe auch  
 [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)