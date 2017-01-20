---
title: "Problembehandlung bei Ausnahmen: System.Net.Sockets.SocketException"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "SocketException-Klasse"
ms.assetid: 89e8194d-83b0-450f-91f5-548e5c13944d
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: System.Net.Sockets.SocketException
Eine <xref:System.Net.Sockets.SocketException>\-Ausnahme wird von der <xref:System.Net.Sockets.Socket>\-Klasse und der <xref:System.Net.Dns>\-Klasse ausgelöst, wenn ein Fehler mit dem Netzwerk auftritt.  
  
## Tipps  
 **Überprüfen Sie die ErrorCode\-Eigenschaft, um festzustellen, warum der Socketfehler aufgetreten ist.**  
 Der Standardkonstruktor für die <xref:System.Net.Sockets.SocketException>\-Klasse legt die <xref:System.Net.Sockets.SocketException.ErrorCode*>\-Eigenschaft auf den zuletzt aufgetretenen Betriebssystemsocketfehler fest.  
  
## Siehe auch  
 <xref:System.Net.Sockets.SocketException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Verwenden von Secure Sockets Layer](../Topic/Using%20Secure%20Sockets%20Layer.md)