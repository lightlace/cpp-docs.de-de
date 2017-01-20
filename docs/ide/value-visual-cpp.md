---
title: "&lt;value&gt; (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "value"
  - "<value>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<value> C++-XML-Tag"
  - "value (C++-XML-Tag)"
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;value&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das \<value\>\-Tag können Sie eine Eigenschaft und Gegensatz beschreiben.  Beachten Sie, dass, wenn Sie eine Eigenschaft mit einem Code\-Assistenten in der integrierten Entwicklungsumgebung von Visual Studio hinzufügen, sie ein [\<summary\>](../ide/summary-visual-cpp.md)\-Tag für die neue Eigenschaft hinzugefügt wird.  Sie sollten dann manuell ein \<value\>\-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.  
  
## Syntax  
  
```  
<value>property-description</value>  
```  
  
#### Parameter  
 `property-description`  
 Eine Beschreibung für die Eigenschaft.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
  
```  
// xml_value_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_value_tag.dll  
using namespace System;  
/// Text for class Employee.  
public ref class Employee {  
private:  
   String ^ name;  
   /// <value>Name accesses the value of the name data member</value>  
public:  
   property String ^ Name {  
      String ^ get() {  
         return name;   
      }  
      void set(String ^ i) {  
         name = i;  
      }  
   }  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)