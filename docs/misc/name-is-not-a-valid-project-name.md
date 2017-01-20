---
title: "&lt;name&gt; is not a valid project name."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_INVALIDPROJECTNAME"
  - "vs.message.0x800A00D2"
ms.assetid: 2e8f3e58-f5f0-4f12-bae9-3acc58c0dca6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# &lt;name&gt; is not a valid project name.
Im Allgemeinen tritt dieser Fehler auf, wenn der Befehl `File.NewProject` im **Befehlsfenster** oder im Feld **Suchen** ausgegeben und für *projectname* ein falscher Projektname eingegeben wurde.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Projektname keine zusätzlichen Leerzeichen enthält und kein reserviertes Wort wie NUL, CON oder AUX ist.  
  
     – oder –  
  
     Geben Sie den Befehl erneut und ohne den Projektnamen ein.  
  
## Siehe auch  
 [Befehlsfenster](../Topic/Command%20Window.md)