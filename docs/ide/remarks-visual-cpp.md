---
title: "&lt;remarks&gt; (Visual C++)"
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
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<remarks> C++-XML-Tag"
  - "remarks (C++-XML-Tag)"
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;remarks&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mittels des \<remarks\>\-Tags werden Informationen über einen Typ hinzugefügt. Diese dienen als Ergänzung zu den mit [\<summary\>](../ide/summary-visual-cpp.md) angegebenen Informationen.  Diese Informationen werden in [Objektkatalog](assetId:///f89acfc5-1152-413d-9f56-3dc16e3f0470) und im Webbericht über Codekommentare angezeigt.  
  
## Syntax  
  
```  
<remarks>description</remarks>  
```  
  
#### Parameter  
 `description`  
 eine Beschreibung des Members.  
  
## Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## Beispiel  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)