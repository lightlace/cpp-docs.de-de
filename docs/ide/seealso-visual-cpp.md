---
title: "&lt;seealso&gt; (Visual C++)"
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
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<seealso> C++-XML-Tag"
  - "seealso (C++-XML-Tag)"
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;seealso&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem \<seealso\>\-Tag kann der Text, der möglicherweise in einem "Siehe auch"\-Abschnitt angezeigt werden soll, angegeben werden.  Mit [\<see\>](../ide/see-visual-cpp.md) wird ein Link im Text angegeben.  
  
## Syntax  
  
```  
<seealso cref="member"/>  
```  
  
#### Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, der bzw. das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  
  
 Die Compilerprüfungen, ob das angegebene Codeelement `member` dem Elementnamen in der Ausgabe XML vorhanden und auflöst.  Der Compiler gibt eine Warnung aus, wenn nicht `member` sucht.  
  
 Informationen für das Erstellen von cref\-Verweisen auf einen generischen Typ finden Sie unter [\<see\>](../ide/see-visual-cpp.md).  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
 Siehe [\<summary\>](../ide/summary-visual-cpp.md) als ein Beispiel für die Verwendung von \<seealso\>.  
  
 Der Visual C\+\+\-Compiler versucht, cref Verweise in einer Durchlauf durch die Dokumentationskommentare aufzulösen.  Wenn, die C\+\+\-Suchenregeln verwenden, ein Symbol vom Compiler nicht gefunden wird, wird der Verweis markiert, wie nicht aufgelöst.  
  
## Beispiel  
 Im folgenden Beispiel wird ein nicht aufgelöstes Symbol in ein cref verwiesen.  Der XML\-Kommentar für das cref zu B::Test ist `<seealso cref="!:B::Test" />`, während der Verweis auf A::Test wohl geformtes `<seealso cref="M:A.Test" />` ist.  
  
```  
// xml_seealso_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_seealso_tag.dll  
  
/// Text for class A.  
public ref struct A {  
   /// <summary><seealso cref="A::Test"/>  
   /// <seealso cref="B::Test"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void Test() {}  
};  
  
/// Text for class B.  
public ref struct B {  
   void Test() {}  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)