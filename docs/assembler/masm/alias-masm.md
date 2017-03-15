---
title: "ALIAS (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Alias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIAS directive"
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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