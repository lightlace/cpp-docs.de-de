---
title: 'Wie: Marshallen von ANSI-Zeichenfolgen mit C++-Interop | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e70d62fa7a94a7278080c31f6650b31b71ff35b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Gewusst wie: Marshallen von ANSI-Zeichenfolgen mit C++-Interop
In diesem Thema wird veranschaulicht, wie von ANSI-Zeichenfolgen sein können mithilfe von C++-Interop, aber .NET Framework übergeben <xref:System.String> Zeichenfolgen in Unicode-Format darstellt, damit die Konvertierung in ANSI ein zusätzlicher Schritt ist. Zusammenarbeit mit anderen Zeichenfolgen-Datentypen, finden Sie unter den folgenden Themen:  
  
-   [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 Im folgenden Codebeispiel Beispiele verwenden die [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Direktiven zum Implementieren verwalteten und nicht verwaltete Funktionen in derselben Datei, aber diese Funktionen auf dieselbe Weise zusammenarbeiten, wenn in separaten Dateien definiert. Da Dateien, die ausschließlich nicht verwaltete Funktionen nicht kompiliert werden müssen [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md), behalten sie ihre Leistungsmerkmale.  
  
## <a name="example"></a>Beispiel  
 Im Beispiel wird eine ANSI-Zeichenfolge von einer verwalteten übergeben, um eine nicht verwaltete Funktion mit <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>. Diese Methode auf dem nicht verwalteten Heap belegt und gibt die Adresse nach der Konvertierung zurück. Dies bedeutet, dass keine anheften notwendig ist (da auf dem GC-Heap nicht an die nicht verwaltete Funktion übergeben wird), und dass von IntPtr zurückgegeben <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> muss explizit freigegeben werden oder ein Speicher verbreiten, die Ergebnisse.  
  
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
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Marshalling von Daten erforderlich, um eine ANSI-Zeichenfolge in einer verwalteten Funktion zuzugreifen, die durch eine nicht verwaltete Funktion aufgerufen wird. Die verwaltete Funktion, nach dem Empfangen der systemeigenen Zeichenfolge kann entweder direkt verwenden oder konvertieren Sie ihn in eine verwaltete Zeichenfolge mit der <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> Methode, wie gezeigt.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)