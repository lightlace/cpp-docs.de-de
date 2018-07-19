---
title: 'Wie: Marshallen von COM-Zeichenfolgen mit C++-Interop | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 918825dd6563f59167baa844b94edfc1033498a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133328"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Gewusst wie: Marshallen von COM-Zeichenfolgen mit C++-Interop
In diesem Thema wird veranschaulicht, wie BSTR (das grundlegende Zeichenfolgenformat bevorzugt wird in COM-Programmierung) werden kann von einer verwalteten an eine nicht verwaltete Funktion (und umgekehrt) übergeben. Zusammenarbeit mit anderen Zeichenfolgen-Datentypen, finden Sie unter den folgenden Themen:  
  
-   [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 Im folgenden Codebeispiel Beispiele verwenden die [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) #pragma-Direktiven zum Implementieren verwalteten und nicht verwaltete Funktionen in derselben Datei, aber diese Funktionen auf dieselbe Weise zusammenarbeiten, wenn in separaten Dateien definiert. Dateien, die ausschließlich nicht verwaltete Funktionen müssen nicht kompiliert werden [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie ein BSTR (ein Zeichenfolgenformat in COM-Programmierung verwendet) übergeben werden kann von einer verwalteten an eine nicht verwaltete Funktion. Der aufrufende verwaltete Funktion verwendet <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> die Adresse einer BSTR-Darstellung des Inhalts eines beziehen. This-Zeiger ist fixiert mit [Pin_ptr (C + c++ / CLI)](../windows/pin-ptr-cpp-cli.md) um sicherzustellen, dass seine physische Adresse während einer Garbage Collection-Zyklus nicht geändert wird, während die nicht verwaltete Funktion ausgeführt wird. Der Garbage Collector untersagt Arbeitsspeicher verschieben, bis die [Pin_ptr (C + c++ / CLI)](../windows/pin-ptr-cpp-cli.md) den Gültigkeitsbereich verlässt.  
  
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
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie ein BSTR übergeben werden kann von einer nicht verwalteten an eine nicht verwaltete Funktion. Der empfangenden verwalteten Funktion kann entweder die Zeichenfolge als BSTR verwenden oder <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> , die sie zum Konvertieren einer <xref:System.String> für die Verwendung mit anderen verwaltete Funktionen. Da der BSTR darstellende Arbeitsspeicher auf dem nicht verwalteten Heap zugewiesen ist, ist keine Fixierung erforderlich, da es keine Garbagecollection auf dem nicht verwalteten Heap wird.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)