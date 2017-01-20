---
title: "Problembehandlung bei Ausnahmen: System.DuplicateWaitObjectException"
ms.custom: na
ms.date: "10/29/2016"
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
  - "DuplicateWaitObjectException-Klasse"
ms.assetid: b9ff6932-a7cf-4a89-bd7d-e4ef1a3ff353
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: System.DuplicateWaitObjectException
Eine <xref:System.DuplicateWaitObjectException>\-Ausnahme wird ausgelöst, wenn das Array aus <xref:System.Threading.WaitHandle>\-Objekten, das an <xref:System.Threading.WaitHandle.WaitAll*> oder <xref:System.Threading.WaitHandle.WaitAny*> übergeben wurde, doppelte Betriebssystemhandles enthält.  
  
## Tipps  
 **Stellen Sie sicher, dass die WaitHandle\-Objekte, die an WaitAll oder WaitAny übergeben wurden, eindeutig sind.**  
 Ein <xref:System.Threading.WaitHandle>\-Array kann nicht mehrere Verweise auf dasselbe Objekt enthalten.  
  
### Hinweise  
 Die Common Language Runtime \(CLR\) stellt einen Threadsynchronisierungsmechanismus bereit, der auf Synchronisierungsobjekten basiert, die in einem <xref:System.Threading.WaitHandle>\-Objektarray auf ihre Ausführung warten.  
  
## Siehe auch  
 <xref:System.DuplicateWaitObjectException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)