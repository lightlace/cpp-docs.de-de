---
title: "Aggregation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++]"
  - "aggregation [C++]"
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Aggregation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt Situationen, in denen die Implementierung eines Objekts die Dienste verwenden möchte, die von anderen bereitgestellt wurden, vordefiniertes Objekt.  Darüber hinaus möchte es, dass dieses zweite Objekt als natürlicher Teil des ersten angezeigt wird.  COM erreicht beide Ziele durch Kapselung und Aggregation.  
  
 Aggregation bedeutet, dass das enthaltende \(äußere\) Objekt das enthaltende Objekt \(innere\) als Teil des Erstellungsprozesses erstellt und Schnittstellen des inneren Objekts vom äußeren verfügbar gemacht werden.  Ein Objekt können sich, um aggregierbar sind oder nicht.  Wenn es ist, muss bestimmte Regeln beachtet, damit Aggregation ordnungsgemäß funktioniert.  
  
 Hauptsächlich müssen alle **IUnknown**\-Methodenaufrufe auf dem enthaltenden Objekt zum enthaltenden Objekt delegieren.  
  
## Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Reusing Objects](http://msdn.microsoft.com/library/windows/desktop/ms678443)