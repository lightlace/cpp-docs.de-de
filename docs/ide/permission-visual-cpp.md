---
title: "&lt;permission&gt; (Visual C++)"
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
  - "permission"
  - "<permission>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<permission> C++-XML-Tag"
  - "permission (C++-XML-Tag)"
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;permission&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem \<permission\>\-Tag kann der Zugriff auf einen Member dokumentiert werden.  <xref:System.Security.PermissionSet> können Sie den Zugriff auf einen Member angeben.  
  
## Syntax  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, der bzw. das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übersetzt `member` in den in der XML\-Ausgabe enthaltenen kanonischen Elementnamen.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  
  
 Der Compiler gibt eine Warnung aus, wenn nicht `member` sucht.  
  
 Informationen für das Erstellen von cref\-Verweisen auf einen generischen Typ finden Sie unter [\<see\>](../ide/see-visual-cpp.md).  
  
 `description`  
 Eine Beschreibung des Zugriffs auf den Member.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
 Der Visual C\+\+\-Compiler versucht, cref Verweise in einer Durchlauf durch die Dokumentationskommentare aufzulösen.  Wenn, die C\+\+\-Suchenregeln verwenden, ein Symbol vom Compiler nicht gefunden wird, wird der Verweis markiert, wie nicht aufgelöst.  Weitere Informationen finden Sie unter [\<seealso\>](../ide/seealso-visual-cpp.md).  
  
## Beispiel  
  
```  
// xml_permission_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_permission_tag.dll  
using namespace System;  
/// Text for class TestClass.  
public ref class TestClass {  
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>  
   void Test() {}  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)