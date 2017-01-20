---
title: "Gewusst wie: Marshallen von eingebetteten Zeigern mit C++-Interop"
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
  - "C++ Interop, Eingebettete Zeiger"
  - "Datenmarshalling [C++], Eingebettete Zeiger"
  - "Interop [C++], Eingebettete Zeiger"
  - "Marshaling [C++], Eingebettete Zeiger"
  - "Zeiger [C++], Marshalling"
  - "Strukturen [C++], Marshallen von eingebetteten Zeigern"
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von eingebetteten Zeigern mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-\#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Diese Funktionen arbeiten jedoch auf dieselbe Weise zusammen, wenn sie in separaten Dateien definiert werden.  Dateien, die ausschließlich nicht verwaltete Funktionen enthalten, müssen nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie eine nicht verwaltete Funktion, die eine Zeiger enthaltende Struktur akzeptiert, durch eine verwaltete Funktion aufgerufen werden kann.  Durch die verwaltete Funktion wird eine Instanz der Struktur erstellt und ein eingebetteter Zeiger mit dem neuen Schlüsselwort initialisiert \(anstelle des [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)\-Schlüsselworts\).  Dadurch wird der Speicher auf dem systemeigenen Heap belegt, und aus diesem Grund ist es nicht erforderlich, das Array für die unterdrückte Garbage Collection zu fixieren.  Der Arbeitsspeicher muss jedoch explizit gelöscht werden, um Memory Leakage zu vermeiden.  
  
```  
// marshal_embedded_pointer.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// unmanaged struct  
struct ListStruct {  
   int count;  
   double* item;  
};  
  
#pragma unmanaged  
  
void UnmanagedTakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
  
#pragma managed  
  
int main() {  
   ListStruct list;  
   list.count = 10;  
   list.item = new double[list.count];  
  
   Console::WriteLine("[managed] count = {0}", list.count);  
   Random^ r = gcnew Random(0);  
   for (int i=0; i<list.count; i++) {  
      list.item[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);  
   }  
  
   UnmanagedTakesListStruct( list );  
   delete list.item;  
}  
```  
  
  **\[managed\] count \= 10**  
**array\[0\] \= 72.624326996796**  
**array\[1\] \= 81.7325359590969**  
**array\[2\] \= 76.8022689394663**  
**array\[3\] \= 55.8161191436537**  
**array\[4\] \= 20.6033154021033**  
**array\[5\] \= 55.8884794618415**  
**array\[6\] \= 90.6027066011926**  
**array\[7\] \= 44.2177873310716**  
**array\[8\] \= 97.754975314138**  
**array\[9\] \= 27.370445768987**  
**\[unmanaged\] count \= 10**  
**array\[0\] \= 72.624327**  
**array\[1\] \= 81.732536**  
**array\[2\] \= 76.802269**  
**array\[3\] \= 55.816119**  
**array\[4\] \= 20.603315**  
**array\[5\] \= 55.888479**  
**array\[6\] \= 90.602707**  
**array\[7\] \= 44.217787**  
**array\[8\] \= 97.754975**  
**array\[9\] \= 27.370446**   
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)