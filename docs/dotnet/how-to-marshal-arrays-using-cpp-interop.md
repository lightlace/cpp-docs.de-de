---
title: "Gewusst wie: Marshallen von Arrays mit C++-Interop"
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
  - "Arrays [C++], Marshalling"
  - "C++ Interop, Arrays"
  - "Datenmarshalling [C++], Arrays"
  - "Interop [C++], Arrays"
  - "Marshaling [C++], Arrays"
ms.assetid: c2b37ab1-8acf-4855-ad3c-7d2864826b14
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von Arrays mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema veranschaulicht einen Aspekt der Visual C\+\+\-Interoperabilität.  Weitere Informationen finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-\#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Diese Funktionen arbeiten jedoch auf dieselbe Weise zusammen, wenn sie in separaten Dateien definiert werden.  Dateien, die ausschließlich nicht verwaltete Funktionen enthalten, müssen nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird dargestellt, wie ein verwaltetes Array an eine nicht verwaltete Funktion übergeben wird.  Die verwaltete Funktion verwendet [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md), um Garbage Collection für das Array zu unterdrücken, bevor die nicht verwaltete Funktion aufgerufen wird.  Indem die nicht verwaltete Funktion mit einem fixierten Zeiger auf den GC\-Heap versehen wird, kann der zusätzliche Aufwand durch das Kopieren des Arrays vermieden werden.  Um zu verdeutlichen, dass die nicht verwaltete Funktion auf den Arbeitsspeicher auf dem GC\-Heap zugreift, wird durch die nicht verwaltete Funktion der Inhalt des Arrays geändert. Diese Änderungen werden wiedergegeben, wenn die verwaltete Funktion die Steuerung erneut übernimmt.  
  
```  
// PassArray1.cpp  
// compile with: /clr  
#ifndef _CRT_RAND_S  
#define _CRT_RAND_S  
#endif  
  
#include <iostream>  
#include <stdlib.h>  
using namespace std;  
  
using namespace System;  
  
#pragma unmanaged  
  
void TakesAnArray(int* a, int c) {  
   cout << "(unmanaged) array received:\n";  
   for (int i=0; i<c; i++)  
      cout << "a[" << i << "] = " << a[i] << "\n";  
  
   unsigned int number;  
   errno_t err;  
  
   cout << "(unmanaged) modifying array contents...\n";  
   for (int i=0; i<c; i++) {  
      err = rand_s( &number );  
      if ( err == 0 )  
         a[i] = number % 100;  
   }  
}  
  
#pragma managed  
  
int main() {  
   array<int>^ nums = gcnew array<int>(5);  
  
   nums[0] = 0;  
   nums[1] = 1;  
   nums[2] = 2;  
   nums[3] = 3;  
   nums[4] = 4;  
  
   Console::WriteLine("(managed) array created:");  
   for (int i=0; i<5; i++)  
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);  
  
   pin_ptr<int> pp = &nums[0];  
   TakesAnArray(pp, 5);  
  
   Console::WriteLine("(managed) contents:");  
   for (int i=0; i<5; i++)  
      Console::WriteLine("a[{0}] = {1}", i, nums[i]);  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird die Übergabe eines nicht verwalteten Arrays an eine verwaltete Funktion dargestellt.  Die verwaltete Funktion greift direkt auf den Arrayspeicher zu \(im Gegensatz zum Erstellen eines verwalteten Arrays und Kopieren des Arrayinhalts\). Dadurch können von der verwalteten Funktion Änderungen vorgenommen werden, die in der nicht verwalteten Funktion wiedergegeben werden, wenn diese erneut die Steuerung übernimmt.  
  
```  
// PassArray2.cpp  
// compile with: /clr   
#include <iostream>  
using namespace std;  
  
using namespace System;  
  
#pragma managed  
  
void ManagedTakesAnArray(int* a, int c) {  
   Console::WriteLine("(managed) array received:");  
   for (int i=0; i<c; i++)  
      Console::WriteLine("a[{0}] = {1}", i, a[i]);  
  
   cout << "(managed) modifying array contents...\n";  
   Random^ r = gcnew Random(DateTime::Now.Second);  
   for (int i=0; i<c; i++)  
      a[i] = r->Next(100);  
}  
  
#pragma unmanaged  
  
void NativeFunc() {  
   int nums[5] = { 0, 1, 2, 3, 4 };  
  
   printf_s("(unmanaged) array created:\n");  
   for (int i=0; i<5; i++)  
      printf_s("a[%d] = %d\n", i, nums[i]);  
  
   ManagedTakesAnArray(nums, 5);  
  
   printf_s("(ummanaged) contents:\n");  
   for (int i=0; i<5; i++)  
      printf_s("a[%d] = %d\n", i, nums[i]);  
}  
  
#pragma managed  
  
int main() {  
   NativeFunc();  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)