---
title: 'Vorgehensweise: Deklarieren von Handles in systemeigenen Typen | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
f1_keywords:
- gcroot
dev_langs:
- C++
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4573aac37eedecceab861eb41a70fc858b409fec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130970"
---
# <a name="how-to-declare-handles-in-native-types"></a>Gewusst wie: Deklarieren von Handles in systemeigenen Typen
Einen Handletyp in einen systemeigenen Typ nicht deklariert werden. Vcclr.h stellt die Wrappervorlage als typsicherer `gcroot` zum Verweisen auf ein CLR-Objekt aus dem Heap. Dieser Vorlage können Sie ein virtuelles Handle in einen systemeigenen Typ einbetten und es zu behandeln, als handele es sich um den zugrunde liegenden Typ. In den meisten Fällen können Sie die `gcroot` Objekt als eingebetteten Typ ohne Umwandlung. Allerdings bei [für jedes in](../dotnet/for-each-in.md), müssen Sie `static_cast` um den zugrunde liegenden verwalteten Verweis abzurufen.  
  
 Die `gcroot` Vorlage mithilfe von den Funktionen der Wertklasse System::Runtime::InteropServices::GCHandle, die "Handles" bietet in die Garbage collection-Heap implementiert wird. Beachten Sie, dass die Handles selbst keine Garbage Collection bereinigt werden und nicht mehr in Verwendung freigegeben werden, die durch den Destruktor der `gcroot` Klasse (dieser Destruktor kann nicht manuell aufgerufen werden). Wenn Sie Instanziieren einer `gcroot` Objekt auf dem systemeigenen Heap, rufen Sie auf diese Ressource löschen.  
  
 Die Common Language Runtime behält eine Zuordnung zwischen dem Handle und die CLR-Objekt, das es verweist. Wenn das CLR-Objekt mit dem Heap der Garbage Collection verschoben wird, gibt das Handle die neue Adresse des Objekts zurück. Eine Variable muss nicht angeheftet werden, bevor er zugewiesen wurde eine `gcroot` Vorlage.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie zum Erstellen einer `gcroot` den systemeigenen Stapel-Objekt.  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
```Output  
hello  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie zum Erstellen einer `gcroot` Objekt auf dem systemeigenen Heap.  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
```Output  
hello  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie `gcroot` für Verweise auf Werttypen (nicht Referenztypen) in einem systemeigenen Typ mit `gcroot` auf den geschachtelten Typ.  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)