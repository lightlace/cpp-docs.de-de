---
title: "Gewusst wie: Marshallen von Unicode-Zeichenfolgen mit C++-Interop"
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
  - "Datenmarshalling [C++], Zeichenfolgen"
  - "Interop [C++], Zeichenfolgen"
  - "Marshaling [C++], Zeichenfolgen"
  - "Unicode, Marshallen von Zeichenfolgen"
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von Unicode-Zeichenfolgen mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema veranschaulicht einen Aspekt der Visual C\+\+\-Interoperabilität.  Weitere Informationen finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-\#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Diese Funktionen arbeiten jedoch auf dieselbe Weise zusammen, wenn sie in separaten Dateien definiert werden.  Dateien, die ausschließlich nicht verwaltete Funktionen enthalten, müssen nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
 In diesem Thema wird beschrieben, wie Unicode\-Zeichenfolgen von einer verwalteten an eine nicht verwaltete Funktion und umgekehrt übergeben werden können.  Informationen zur Interoperation mit anderen Zeichenfolgentypen finden Sie in den folgenden Themen:  
  
-   [Gewusst wie: Marshallen von ANSI\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von COM\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## Beispiel  
 Zum Übergeben einer Unicode\-Zeichenfolge von einer verwalteten an eine nicht verwaltete Funktion kann die PtrToStringChars\-Funktion \(in Vcclr.h deklariert\) für den Zugriff auf den Speicher verwendet werden, in dem die verwaltete Zeichenfolge gespeichert ist.  Da diese Adresse an die systemeigene Funktion übergeben wird, ist es wichtig, den Speicher mit [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) zu fixieren, damit die Zeichenfolgendaten nicht verschoben werden, falls während der Ausführung der nicht verwalteten Funktion ein Garbage Collection\-Zyklus erfolgt.  
  
```  
// MarshalUnicode1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const wchar_t* p) {  
   printf_s("(native) received '%S'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("test string");  
   pin_ptr<const wchar_t> str = PtrToStringChars(s);  
  
   Console::WriteLine("(managed) passing string to native func...");  
   NativeTakesAString( str );  
}  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt das erforderliche Datenmarshalling für den Zugriff auf die Unicode\-Zeichenfolge in einer verwalteten Funktion, die von einer nicht verwalteten Funktion aufgerufen wird.  Die von der verwalteten Funktion empfangene systemeigene Unicode\-Zeichenfolge wird mit der <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni*>\-Methode in eine verwaltete Zeichenfolge konvertiert.  
  
```  
// MarshalUnicode2.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(wchar_t* s) {  
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);  
   Console::WriteLine("(managed) received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(unmanaged) calling managed func...\n";  
   ManagedStringFunc(L"test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)