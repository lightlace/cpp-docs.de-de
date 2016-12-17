---
title: "Gewusst wie: Marshallen von COM-Zeichenfolgen mit C++-Interop"
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
  - "C++ Interop, Zeichenfolgen"
  - "COM [C++], Marshallen von Zeichenfolgen"
  - "Datenmarshalling [C++], Zeichenfolgen"
  - "Interop [C++], Zeichenfolgen"
  - "Marshaling [C++], Zeichenfolgen"
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von COM-Zeichenfolgen mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie BSTR \(das bei der COM\-Programmierung bevorzugte grundlegende Zeichenfolgenformat\) von einer verwalteten an eine nicht verwaltete Funktion und umgekehrt übergeben werden kann.  Informationen zur Interoperation mit anderen Zeichenfolgentypen finden Sie in den folgenden Themen:  
  
-   [Gewusst wie: Marshallen von Unicode\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von ANSI\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-\#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Diese Funktionen arbeiten jedoch auf dieselbe Weise zusammen, wenn sie in separaten Dateien definiert werden.  Dateien, die ausschließlich nicht verwaltete Funktionen enthalten, müssen nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie BSTR \(ein in der COM\-Programmierung verwendetes Zeichenfolgenformat\) von einer verwalteten an eine nicht verwaltete Funktion übergeben werden kann.  Die aufrufende verwaltete Funktion verwendet <xref:System.Runtime.InteropServices.Marshal.StringToBSTR*> zum Abrufen der Adresse einer BSTR\-Darstellung der Inhalte eines .NET\-System.String.  Dieser Zeiger wird mit [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) fixiert, um sicherzustellen, dass seine physische Adresse während eines Garbage Collection\-Zyklus bei Ausführung einer nicht verwalteten Funktion nicht geändert wird.  Der Garbage Collector kann so lange keinen Arbeitsspeicher verschieben, bis [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) den Bereich verlassen hat.  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine BSTR\-Zeichenfolge von einer nicht verwalteten an eine verwaltete Funktion übergeben werden kann.  Die empfangende verwaltete Funktion kann entweder die Zeichenfolge als BSTR übernehmen oder <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR*> zur Konvertierung in <xref:System.String> verwenden, damit sie mit anderen verwalteten Funktionen verwendet werden kann.  Da der BSTR darstellende Arbeitsspeicher auf dem nicht verwalteten Heap belegt ist, ist keine Fixierung erforderlich, denn auf dem nicht verwalteten Heap erfolgt keine Garbage Collection.  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)