---
title: "&lt;param&gt; (Visual C++)"
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
  - "param"
  - "<param>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<param> C++-XML-Tag"
  - "param (C++-XML-Tag)"
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;param&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das \<param\>\-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter der Methode zu beschreiben.  
  
## Syntax  
  
```  
<param name='name'>description</param>  
```  
  
#### Parameter  
 `name`  
 der Name des Methodenparameters.  Fügen Sie den Namen in einfache oder doppelte Anführungszeichen eingeschlossen werden.  Der Compiler gibt eine Warnung aus, wenn nicht `name` sucht.  
  
 `description`  
 eine Beschreibung für den Parameter.  
  
## Hinweise  
 Der Text für das \<param\>\-Tag wird in IntelliSense, [Objektkatalog](assetId:///f89acfc5-1152-413d-9f56-3dc16e3f0470) und im Webbericht über Codekommentare angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
  
```  
// xml_param_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_param_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <param name="Int1">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
   }  
};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)