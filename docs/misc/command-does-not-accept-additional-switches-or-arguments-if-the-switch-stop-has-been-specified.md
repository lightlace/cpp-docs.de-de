---
title: "Command does not accept additional switches or arguments if the switch &quot;/stop&quot; has been specified."
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
  - "vs.message.0x800A00CD"
  - "vs.message.VS_E_NOTVALIDWITHSTOP"
ms.assetid: 1dea2450-034e-4a7f-b959-2060811329b6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# Command does not accept additional switches or arguments if the switch &quot;/stop&quot; has been specified.
Im Allgemeinen tritt dieser Fehler auf, wenn der Schalter `/stop` mit weiteren Schaltern für die Befehle **Suche in Dateien** oder **In Dateien ersetzen** eingegeben wurde.  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn Sie die aktuelle Operation **Suche in Dateien** beenden möchten, geben Sie Folgendes ein:  
  
    ```  
    Edit.FindinFiles /stop.  
    ```  
  
2.  Wenn Sie die aktuelle Operation **In Dateien ersetzen** beenden möchten, geben Sie Folgendes ein:  
  
    ```  
    Edit.ReplaceinFiles /stop  
    ```  
  
3.  Wenn Sie eine neue Operation **Suche in Dateien** oder **In Dateien ersetzen** starten möchten, geben Sie den Befehl ohne `/stop` erneut ein.  
  
## Siehe auch  
 [Befehl "In Dateien ersetzen"](../Topic/Replace%20In%20Files%20Command.md)   
 [Befehl "In Dateien suchen"](../Topic/Find%20in%20Files%20Command.md)   
 [Visual Studio\-Befehle](../Topic/Visual%20Studio%20Commands.md)