---
title: "Wie: Marshallen von Rückrufen und Delegaten mit C++-Interop | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dbae96aeb7b11105a1a2aa30aa513c8d94011a91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Gewusst wie: Marshallen von Rückrufen und Delegaten mit C++-Interop
Dieses Thema veranschaulicht, das Marshallen von Rückrufen und Delegaten (die verwaltete Version eines Rückrufs) zwischen verwaltetem und nicht verwaltetem Code mithilfe von Visual C++.  
  
 Im folgenden Codebeispiel Beispiele verwenden die [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Direktiven zum Implementieren verwalteten und nicht verwaltete Funktionen in derselben Datei, aber die Funktionen ebenfalls in separaten Dateien definiert werden. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht kompiliert werden, mit der [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine nicht verwaltete API, um einen verwalteten Delegaten auszulösen. Ein verwalteter Delegat wird erstellt und eine der Interop-Methoden <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, dient zum Abrufen des zugrunde liegenden Einstiegspunkts für den Delegaten. Diese Adresse wird dann an die nicht verwaltete Funktion übergeben, bezeichneten ohne Kenntnisse der Tatsache, dass es als eine verwaltete Funktion implementiert wird.  
  
 Beachten Sie, dass ist es möglich, aber nicht notwendig ist, um die Pin den Delegaten mit [Pin_ptr (C + c++ / CLI)](../windows/pin-ptr-cpp-cli.md) um zu verhindern, dass sie erneut gespeichert oder vom Garbage Collector freigegeben. Schutz von der vorzeitige Garbagecollection ist erforderlich, aber anheften bietet mehr Schutz erforderlich ist, wird verhindert, dass Auflistung aber auch verhindert die Umsetzung ist.  
  
 Ein Delegat durch eine Garbagecollection erneut geschützt, wirkt sich nicht die zugrunde liegende verwaltete Rückruf daher <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> wird verwendet, um einen Verweis auf den Delegaten, sodass Verschiebung des Delegaten, aber dadurch hinzufügen. Pin_ptr GCHandle anstelle verringert Fragmentierungspotenzial des verwalteten Heaps.  
  
```  
// MarshalDelegate1.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n, m);  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   return n + m;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   GCHandle gch = GCHandle::Alloc(fp);  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
// force garbage collection cycle to prove  
// that the delegate doesn't get disposed  
   GC::Collect();  
  
   int answer = TakesCallback(cb, 243, 257);  
  
// release reference to delegate  
   gch.Free();  
}  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel ähnelt dem vorherigen Beispiel, jedoch in diesem Fall wird der bereitgestellten Funktionszeiger von der nicht verwalteten API gespeichert, damit er jederzeit aufgerufen werden kann, erfordern, dass Garbagecollection für eine beliebige Zeitspanne unterdrückt werden. Im folgenden Beispiel wird daher eine globale Instanz von <xref:System.Runtime.InteropServices.GCHandle> zu verhindern, dass der Delegat verschobenen, unabhängig vom Gültigkeitsbereich der Funktion festgelegt wird. Wie im ersten Beispiel erläutert wird, wird die Verwendung Pin_ptr für diese Beispiele nicht erforderlich, jedoch in diesem Fall wäre nicht trotzdem funktionieren, da der Rahmen Pin_ptr auf eine einzelne Funktion beschränkt ist.  
  
```  
// MarshalDelegate2.cpp  
// compile with: /clr   
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
static ANSWERCB cb;  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   cb = fp;  
   if (cb) {  
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);  
      return cb(n, m);  
   }  
   printf_s("[unmanaged] unregistering callback");  
   return 0;  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
  
   return n + m + x;  
}  
  
static GCHandle gch;  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
  
   gch = GCHandle::Alloc(fp);  
  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TakesCallback(cb, 243, 257);  
  
   // possibly much later (in another function)...  
  
   Console::WriteLine("[managed] releasing callback mechanisms...");  
   TakesCallback(0, 243, 257);  
   gch.Free();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)