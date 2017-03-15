---
title: "Gewusst wie: Marshallen von R&#252;ckrufen und Delegaten mit C++-Interop"
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
  - "C++ Interop, Rückrufe und Delegaten"
  - "Rückrufe [C++], Marshalling"
  - "Datenmarshalling [C++], Rückrufe und Delegaten"
  - "Delegaten [C++], Marshalling"
  - "Interop [C++], Rückrufe und Delegaten"
  - "Marshaling [C++], Rückrufe und Delegaten"
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von R&#252;ckrufen und Delegaten mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt wird das Marshallen von Rückrufen und Delegaten \(die verwaltete Version eines Rückrufs\) zwischen verwaltetem und nicht verwaltetem Code unter Verwendung von Visual C\+\+ erläutert.  
  
 In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md) \#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Die Funktionen können jedoch auch in separaten Dateien definiert werden.  Dateien, die ausschließlich nicht verwaltete Funktionen enthalten, müssen nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine nicht verwaltete API konfiguriert wird, um einen verwalteten Delegaten auszulösen.  Ein verwalteter Delegat wird erstellt, und eine der Interop\-Methoden \(<xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate*>\) wird zum Abrufen des zugrunde liegenden Einstiegspunkts für den Delegaten verwendet.  Diese Adresse wird anschließend an die nicht verwaltete Funktion übergeben, die diese aufruft. Die Funktion hat dabei keine Kenntnis davon, dass die Adresse als verwaltete Funktion implementiert ist.  
  
 Es ist möglich, jedoch nicht zwingend erforderlich, den Delegaten mithilfe von [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) zu fixieren, um zu verhindern, dass er verschoben oder vom Garbage Collector verworfen wird.  Der Schutz vor vorzeitiger Garbage Collection ist notwendig, das Fixieren bietet jedoch größeren Schutz als erforderlich, da dadurch sowohl das Verwerfen als auch das Verschieben verhindert werden.  
  
 Wird ein Delegat bei einer Garbage Collection verschoben, wird der zugrunde liegende verwaltete Rückruf dadurch nicht beeinflusst. Mit <xref:System.Runtime.InteropServices.GCHandle.Alloc*> kann dem Delegaten eine Referenz hinzugefügt werden, die das Verschieben des Delegaten ermöglicht, seine Verwerfung jedoch verhindert.  Durch Verwendung von GCHandle anstelle von pin\_ptr wird das Fragmentierungspotenzial des verwalteten Heaps verringert.  
  
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
  
## Beispiel  
 Das folgende Beispiel ähnelt dem vorherigen. In diesem Fall wird der vorhandene Funktionszeiger jedoch von der nicht verwalteten API gespeichert. Somit kann er jederzeit aufgerufen werden unter der Bedingung, dass die Garbage Collection für eine beliebige Zeitspanne unterdrückt wird.  Aus diesem Grund wird im folgenden Beispiel eine globale Instanz von <xref:System.Runtime.InteropServices.GCHandle> verwendet, um unabhängig vom Gültigkeitsbereich der Funktion zu verhindern, dass der Delegat verschoben wird.  Wie im ersten Beispiel erläutert, ist die Verwendung von pin\_ptr in diesen Beispielen nicht erforderlich. In diesem Fall würde pin\_ptr jedoch nicht funktionieren, da der entsprechende Gültigkeitsbereich auf eine einzelne Funktion begrenzt ist.  
  
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
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)