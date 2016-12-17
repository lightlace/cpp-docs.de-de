---
title: "alloc_text"
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
  - "vc-pragma.alloc_text"
  - "alloc_text_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "alloc_text-Pragma"
  - "Pragmas, alloc_text"
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# alloc_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Namen des Codeabschnitts, in dem sich die angegebenen Funktionsdefinitionen befinden müssen.  Das Pragma muss zwischen einem Funktionsdeklarator und der Funktionsdefinition für die benannten Funktionen auftreten.  
  
## Syntax  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## Hinweise  
 Das **alloc\_text**\-Pragma verarbeitet keine C\+\+\-Memberfunktionen oder überladene Funktionen.  Es ist nur auf Funktionen anwendbar, die mit C\-Verknüpfung deklariert sind – d. h. Funktionen, die mit der **extern "C"**\-Verknüpfungsspezifikation deklariert werden.  Wenn Sie versuchen, diese Pragma für eine Funktion mit C\+\+\-Bindung zu verwenden, wird ein Compilerfehler generiert.  
  
 Da Funktionen, die mithilfe von `__based` adressieren, nicht unterstützt werden, erfordert die Angabe von Abschnittsspeicherorten die Verwendung des **alloc\_text**\-Pragmas.  Der Name, der von *textsection* angegeben wird, muss in doppelte Anführungszeichen gesetzt werden.  
  
 Das **alloc\_text**\-Pragma muss nach den Deklarationen aller angegebenen Funktionen und vor den Definitionen dieser Funktionen angezeigt werden.  
  
 Die Funktionen, auf die in einem **alloc\_text**\-Pragma verwiesen wird, sollten in demselben Modul wie das Pragma definiert sein.  Wenn dies nicht erfolgt ist und es wird eine nicht definierte Funktion später in einen anderen Textbereich kompiliert, ist ungewiss, ob der Fehler abgefangen wird.  Obwohl das Programm in der Regel ordnungsgemäß ausgeführt wird, ist die Funktion nicht in den vorgesehenen Abschnitten zugeordnet.  
  
 Andere Einschränkungen für **alloc\_text** lauten wie folgt:  
  
-   Es kann nicht innerhalb einer Funktion verwendet werden.  
  
-   Es muss verwendet werden, nachdem die Funktion deklariert wurde, aber bevor die Funktion definiert wurde.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)