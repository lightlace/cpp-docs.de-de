---
title: "Gewusst wie: Deklarieren von Handles in systemeigenen Typen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot-Schlüsselwort [C++]"
  - "Handles, Deklarieren"
  - "Typen [C++], Deklarieren von Handles in"
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Deklarieren von Handles in systemeigenen Typen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können einen Handletyp nicht in einem systemeigenen Typ deklarieren. vcclr.h stellt die typsichere Wrappervorlage `gcroot`, ein CLR\-Objekt vom C\+\+\-Heap zu verweisen.  Mit dieser Vorlage können Sie ein virtuelles Handle in einen systemeigenen Typ einbetten und es behandeln, als sei es der zugrunde liegende Typ.  In den meisten Fällen können Sie das `gcroot`\-Objekt ohne Umwandlung als eingebetteten Typ verwenden.  Bei [for each, in](../dotnet/for-each-in.md) müssen Sie jedoch mithilfe von `static_cast` den zugrunde liegenden verwalteten Verweis abrufen.  
  
 Die `gcroot`\-Vorlage wird mithilfe der Funktionen der Wertklasse System::Runtime::InteropServices::GCHandle implementiert, die "Handles" in einen der Garbage Collection unterliegenden Heap ermöglicht.  Beachten Sie, dass die Handles selbst nicht der Garbage Collection unterliegen und durch den Destruktor der `gcroot`\-Klasse freigegeben werden, wenn sie nicht mehr verwendet werden \(Der Destruktor kann nicht manuell aufgerufen werden\).  Wenn Sie auf dem systemeigenen Heap ein `gcroot`\-Objekt instanziieren, müssen Sie für diese Ressource die delete\-Methode aufrufen.  
  
 Eine Zuordnung zwischen dem Handle und dem CLR\-Objekt, auf das es verweist, wird von der Laufzeit aufrechterhalten.  Wenn das CLR\-Objekt mit dem der Garbage Collection unterliegenden Heap verschoben wird, gibt das Handle die neue Adresse des Objekts zurück.  Eine Variable muss nicht fixiert werden, bevor sie einer `gcroot`\-Vorlage zugewiesen wird.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie ein `gcroot`\-Objekt auf dem systemeigenen Stapel erstellt wird.  
  
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
  
  **Hello**   
## Beispiel  
 Dieses Beispiel zeigt, wie ein `gcroot`\-Objekt auf dem systemeigenen Heap erstellt wird.  
  
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
  
  **Hello**   
## Beispiel  
 Dieses Beispiel zeigt, wie Sie durch Anwendung von `gcroot` auf den geschachtelten Typ erreichen, dass `gcroot` Verweise auf Werttypen \(nicht Referenztypen\) in einem systemeigenen Typ ablegt.  
  
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
  
  **Zeichenfolge in V: Hello**   
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)