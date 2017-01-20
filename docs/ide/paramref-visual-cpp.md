---
title: "&lt;paramref&gt; (Visual C++)"
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
  - "paramref"
  - "<paramref>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<paramref> C++-XML-Tag"
  - "paramref (C++-XML-Tag)"
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;paramref&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das \<paramref\>\-Tag gibt Ihnen die Möglichkeit, anzugeben, dass ein Wort ein Parameter ist.  Die XML\-Datei kann verarbeitet werden, um diesen Parameter auf eine andere Weise zu formatieren.  
  
## Syntax  
  
```  
<paramref name="name"/>  
```  
  
#### Parameter  
 `name`  
 der Name des Parameters, auf den verwiesen werden soll.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  Der Compiler gibt eine Warnung aus, wenn nicht `name` sucht.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
  
```  
// xml_paramref_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_paramref_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// The <paramref name="Int1"/> parameter takes a number.  
   /// </summary>  
   void MyMethod(int Int1) {}  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)