---
title: "&lt;exception&gt; (Visual C++)"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<exception> C++-XML-Tag"
  - "exception (C++ XML-Tag)"
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;exception&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem \<exception\>\-Tag können Sie festlegen, welche Ausnahmen ausgelöst werden können.  Dieses Tag wird auf eine Methodendefinition angewendet.  
  
## Syntax  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Parameter  
 `member`  
 ein Verweis auf eine Ausnahme, die in der aktuellen Kompilierungsumgebung verfügbar ist.  Verwenden der Namesuchenregeln die Compilerprüfungen, ob die angegebene Ausnahme vorhanden ist und `member` den kanonischen Elementnamen in der Ausgabe XML übersetzt.  Der Compiler gibt eine Warnung aus, wenn nicht `member` sucht.  
  
 Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  
  
 Informationen für das Erstellen von cref\-Verweisen auf einen generischen Typ finden Sie unter [\<see\>](../ide/see-visual-cpp.md).  
  
 `description`  
 eine Beschreibung.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
 Der Visual C\+\+\-Compiler versucht, cref Verweise in einer Durchlauf durch die Dokumentationskommentare aufzulösen.  Wenn, die C\+\+\-Suchenregeln verwenden, ein Symbol vom Compiler nicht gefunden wird, wird der Verweis markiert, wie nicht aufgelöst.  Weitere Informationen finden Sie unter [\<seealso\>](../ide/seealso-visual-cpp.md).  
  
## Beispiel  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)