---
title: "ALIAS (MASM)"
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
  - "Alias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIAS directive"
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ALIAS (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **ALIAS**\-Direktive erstellen einen alternativen Namen für eine benutzerdefinierte Funktion.  Auf diese Weise können Sie mehrere Namen für eine Funktion erstellen oder legt ihn fest, die den Linker Bibliotheken \(LINK.exe\) ermöglichen um eine alte Funktion einer neuen Funktion zugeordnet werden soll.  
  
## Syntax  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### Parameter  
 `actual-name`  
 Der tatsächliche Name der Funktion oder Prozedur.  Die spitzen Klammern sind erforderlich.  
  
 `alias`  
 Das Alternativen\- oder Alias.  Die spitzen Klammern sind erforderlich.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)