---
title: 'Wie: Marshallen von Unicode-Zeichenfolgen mit C++-Interop | Microsoft Docs'
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
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9226eaf035cee7614f2d072a5e2493c067012c2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>Gewusst wie: Marshallen von Unicode-Zeichenfolgen mit C++-Interop
Dieses Thema veranschaulicht einen Aspekt der Visual C++-Interoperabilität. Weitere Informationen finden Sie unter [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Im folgenden Codebeispiel Beispiele verwenden die [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Direktiven zum Implementieren verwalteten und nicht verwaltete Funktionen in derselben Datei, aber diese Funktionen auf dieselbe Weise zusammenarbeiten, wenn in separaten Dateien definiert. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht kompiliert werden [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 In diesem Thema wird veranschaulicht, wie ein Unicode-Zeichenfolgen werden können von einer verwalteten an eine nicht verwaltete Funktion (und umgekehrt) übergeben. Zusammenarbeit mit anderen Zeichenfolgen-Datentypen, finden Sie unter den folgenden Themen:  
  
-   [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## <a name="example"></a>Beispiel  
 Um eine Unicode-Zeichenfolge von einer verwalteten an eine nicht verwaltete Funktion übergeben werden soll, kann die PtrToStringChars-Funktion (deklariert in Vcclr.h) kann verwendet werden, Zugriff auf den Speicher, in dem die verwaltete Zeichenfolge gespeichert ist. Da diese Adresse an eine systemeigene Funktion übergeben wird, ist es wichtig, dass der Arbeitsspeicher mit angeheftet werden [Pin_ptr (C + c++ / CLI)](../windows/pin-ptr-cpp-cli.md) um zu verhindern, dass die Zeichenfolgendaten verschoben wird, sollte ein Zyklus der Garbage Collection erfolgen während der nicht verwaltete Funktion ausgeführt wird.  
  
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
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Marshalling von Daten erforderlich, um eine Unicode-Zeichenfolge in einer verwalteten Funktion wird aufgerufen, indem Sie eine nicht verwaltete Funktion zuzugreifen. Die verwaltete Funktion, nach dem Empfangen der systemeigenen Unicode-Zeichenfolge konvertiert es in eine verwaltete Zeichenfolge mit der <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> Methode.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)