---
title: "&lt;see&gt; (Visual C++)"
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
  - "<see>"
  - "see"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<see> C++-XML-Tag"
  - "see (C++-XML-Tag)"
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;see&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem \<see\>\-Tag kann ein Link im Text angegeben werden.  Verwendung [\<seealso\>](../ide/seealso-visual-cpp.md), Text anzugeben, die Sie in einem Abschnitt Siehe auch angezeigt werden sollen.  
  
## Syntax  
  
```  
<see cref="member"/>  
```  
  
#### Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, der bzw. das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  
  
 Die Compilerprüfungen, ob das angegebene Codeelement `member` dem Elementnamen in der Ausgabe XML vorhanden und auflöst.  Der Compiler gibt eine Warnung aus, wenn nicht `member` sucht.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
 Siehe [\<summary\>](../ide/summary-visual-cpp.md) als ein Beispiel für die Verwendung von \<see\>.  
  
 Der Visual C\+\+\-Compiler versucht, cref Verweise in einer Durchlauf durch die Dokumentationskommentare aufzulösen.  Wenn, die C\+\+\-Suchenregeln verwenden, ein Symbol vom Compiler nicht gefunden wird, wird der Verweis markiert, wie nicht aufgelöst.  Weitere Informationen finden Sie unter [\<seealso\>](../ide/seealso-visual-cpp.md).  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie cref Bezug auf einen generischen Typ ausführen können, so, dass, der Compiler den Verweis auflöst.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)