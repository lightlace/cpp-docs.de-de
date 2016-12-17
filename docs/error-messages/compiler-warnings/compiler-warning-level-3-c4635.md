---
title: "Compilerwarnung (Stufe 3) C4635"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4635"
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML\-Dokumentkommentarziel: Ungültige XML: Grund  
  
 Der Compiler hat ein Problem mit XML\-Tags gefunden.  Beheben Sie das Problem, und führen Sie die Kompilierung erneut durch.  
  
 Im folgenden Beispiel wird C4635 generiert:  
  
```  
// C4635.cpp // compile with: /doc /clr /W3 /c /// <summary> /// The contents of the folder have changed. /// <summary/>   // C4635 // try the following line instead // /// </summary> public ref class Test {};  
```  
  
 Beachten Sie, dass die Ausgabe für dieses Beispiel wie folgt lautet: **Das Endtag 'member' stimmt nicht mit dem Starttag 'summary' überein.**  
  
 Das Problem bei diesem Beispiel ist, dass das Endtag für \<summary\> nicht ordnungsgemäß formuliert ist, und der Compiler erkennt es nicht als \<summary\>\-Endtag.  Das \<member\>\-Tag wird vom Compiler in jeder „\/doc“\-Kompilierung in der XDC\-Datei eingebettet.  Hier ist also das Problem, dass das Endtag \<\/member\> nicht mit dem vorherigen Starttag übereinstimmt, das vom Compiler verarbeitet wurde \(\<summary\>\).