---
title: "&lt;list&gt; (Visual C++)"
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
  - "list"
  - "<list>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<list> C++-XML-Tag"
  - "list (C++-XML-Tag)"
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;list&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der \<listheader\>\-Block wird zur Definition der Überschriftenzeile einer Tabelle oder einer Definitionsliste verwendet.  Wenn eine Tabelle definiert wird, muss nur ein Eintrag für "term" in der Überschrift angegeben werden.  
  
## Syntax  
  
```  
<list type="bullet" | "number" | "table">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### Parameter  
 `term`  
 Ein zu definierender Term, der in `description` definiert wird.  
  
 `description`  
 ein Element in einer Aufzählung oder nummerierten Liste oder die Definition eines `term`s.  
  
## Hinweise  
 Jedes Element der Liste wird mit einem \<item\>\-Block angegeben.  Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.  Für eine Tabelle, eine Aufzählung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.  
  
 Eine Liste oder Tabelle kann so viele \<item\>\-Blöcke enthalten, wie benötigt werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
  
```  
// xml_list_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_list_tag.dll  
/// <remarks>Here is an example of a bulleted list:  
/// <list type="bullet">  
/// <item>  
/// <description>Item 1.</description>  
/// </item>  
/// <item>  
/// <description>Item 2.</description>  
/// </item>  
/// </list>  
/// </remarks>  
class MyClass {};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)