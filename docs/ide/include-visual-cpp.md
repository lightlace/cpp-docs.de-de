---
title: "&lt;include&gt; (Visual C++)"
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
  - "include"
  - "<include>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<include> (C++-XML-Tag)"
  - "include (C++-XML-Tag)"
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;include&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem \<include\>\-Tag kann auf Kommentare in anderen Dateien verwiesen werden, die die Typen und Member im Quellcode beschreiben.  Dies stellt eine Alternative zum direkten Positionieren der Dokumentationskommentare in Quellcodedateien dar.  Beispielsweise können Sie \<include\> verwenden, um Standardkommentare "des vorformulierten Satzes" einzufügen, die im Team oder Unternehmen verwendet werden.  
  
## Syntax  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### Parameter  
 `filename`  
 der Name der Datei, die die Dokumentation enthält.  Der Dateiname kann mit einem Pfad gekennzeichnet sein.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  Der Compiler gibt eine Warnung aus, wenn nicht `filename` sucht.  
  
 `tagpath`  
 Ein gültiger XPath\-Ausdruck, der die gewünschte Knotengruppe auswählt, enthielt in der Datei.  
  
 `name`  
 Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` weist eine `id` auf.  
  
 `id`  
 die ID für das Tag, das sich vor den Kommentaren befindet.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  
  
## Hinweise  
 Das \<include\>\-Tag verwendet die XPath\-Syntax von XML.  Siehe XPath\-Dokumentation, sodass Methoden mit \<include\>anpassen.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
 Hierbei handelt es sich um ein Beispiel mit mehreren Dateien.  Die erste Datei, die \<include\>verwendet, enthält die folgenden Dokumentationskommentare:  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 Die zweite Datei, **xml\_include\_tag.doc**, enthält die folgenden Dokumentationskommentare:  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## Programmausgabe  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)