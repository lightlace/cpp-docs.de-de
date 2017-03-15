---
title: "Gewusst wie: Marshallen von ANSI-Zeichenfolgen mit C++-Interop"
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
  - "ANSI [C++], Marshallen von Zeichenfolgen"
  - "C++ Interop, Zeichenfolgen"
  - "Datenmarshalling [C++], Zeichenfolgen"
  - "Interop [C++], Zeichenfolgen"
  - "Marshaling [C++], Zeichenfolgen"
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von ANSI-Zeichenfolgen mit C++-Interop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird gezeigt, wie ANSI\-Zeichenfolgen mit C\+\+\-Interop übergeben werden. .NET Framework <xref:System.String> stellt Zeichenfolgen jedoch im Unicode\-Format dar, sodass die Konvertierung in ANSI einen zusätzlichen Schritt darstellt.  Informationen zur Interoperation mit anderen Zeichenfolgentypen finden Sie in den folgenden Themen:  
  
-   [Gewusst wie: Marshallen von Unicode\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von COM\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 In den folgenden Codebeispielen werden die [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-\#pragma\-Direktiven verwendet, um verwaltete und nicht verwaltete Funktionen in derselben Datei zu implementieren. Diese Funktionen arbeiten jedoch auf dieselbe Weise zusammen, wenn sie in separaten Dateien definiert werden.  Da Dateien, die lediglich nicht verwaltete Funktionen enthalten, nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden müssen, behalten diese ihre Leistungsmerkmale bei.  
  
## Beispiel  
 In diesem Beispiel wird die Übergabe einer ANSI\-Zeichenfolge von einer verwalteten Funktion an eine nicht verwaltete Funktion mithilfe von <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi*> dargestellt.  Durch diese Methode wird Arbeitsspeicher auf dem nicht verwalteten Heap belegt und die Adresse nach Durchführen der Konvertierung zurückgegeben.  Aus diesem Grund ist keine Fixierung erforderlich, denn der Speicher auf dem GC\-Heap wird nicht an die nicht verwaltete Funktion übergeben, und der von <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi*> zurückgegebene IntPtr muss explizit freigegeben werden, da sonst Memory Leakage auftritt.  
  
```  
// MarshalANSI1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const char* p) {  
   printf_s("(native) received '%s'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("sample string");  
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);  
   const char* str = static_cast<const char*>(ip.ToPointer());  
  
   Console::WriteLine("(managed) passing string...");  
   NativeTakesAString( str );  
  
   Marshal::FreeHGlobal( ip );  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird das Datenmarshalling dargestellt, das für den Zugriff auf eine ANSI\-Zeichenfolge in einer verwalteten Funktion erforderlich ist, die von einer nicht verwalteten Funktion aufgerufen wird.  Die verwaltetete Funktion kann die empfangene sytemeigene Zeichenfolge sofort verwenden oder mithilfe der <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi*>\-Methode wie dargestellt in eine verwaltete Zeichenfolge konvertieren.  
  
```  
// MarshalANSI2.cpp  
// compile with: /clr  
#include <iostream>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(char* s) {  
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));  
   Console::WriteLine("(managed): received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(native) calling managed func...\n";  
   ManagedStringFunc("test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)