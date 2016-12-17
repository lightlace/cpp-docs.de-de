---
title: "&lt;c&gt; (Visual C++)"
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
  - "<c>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<c> C++ XML-Tag"
  - "c C++-XML-Tag"
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;c&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das \<c\>\-Tag gibt diesen Text innerhalb einer Beschreibung sollte als Code gekennzeichnet sind.  Zum Angeben mehrerer Zeilen als Code wird [\<code\>](../ide/code-visual-cpp.md) verwendet.  
  
## Syntax  
  
```  
<c>text</c>  
```  
  
#### Parameter  
 `text`  
 Der Text, den Sie als Code angeben möchten.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
  
```  
// xml_c_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_c_tag.xdc  
  
/// Text for class MyClass.  
class MyClass {  
public:  
   int m_i;  
   MyClass() : m_i(0) {}  
  
   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.  
   /// </summary>  
   int MyMethod(MyClass * a) {  
      return a -> m_i;  
   }  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)