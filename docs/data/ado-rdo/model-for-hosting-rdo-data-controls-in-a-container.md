---
title: "Hostmodell f&#252;r RDO-Datensteuerelemente in einem Container | Microsoft Docs"
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
  - "RDO-Remote-Datensteuerelement, Hostmodell"
  - "RemoteData-Steuerelement, Hostmodell"
ms.assetid: ca598bac-9fef-40e6-b6cd-03d817e16b2e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Hostmodell f&#252;r RDO-Datensteuerelemente in einem Container
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Container werden folgendermaßen als Host für RDO\-Datensteuerelemente verwendet:  
  
-   Der Container erhält eine **IVBDSC**\-Schnittstelle vom Datensteuerelement.  Wenn IVBDSC nicht auffindbar ist, handelt es sich nicht um ein Datensteuerelement.  
  
-   Der Container erhält die **ICursor**\-Schnittstellen des Datensteuerelements.  Diese Schnittstellen stellen ein Cursorobjekt bereit, das von einem Client geändert werden kann.  
  
-   Der Container stellt eine Verknüpfung mit der **INotifyDBEvents**\-Schnittstelle des Datensteuerelements her.  Diese Schnittstelle ermöglicht es dem Container, Benachrichtigungen vom Datensteuerelement zu empfangen.  Der Container sollte zu diesem Zweck die **INotifyDBEventsSink**\-Schnittstelle unterstützen.  
  
 Container werden folgendermaßen als Host für datengebundene RDO\-Steuerelemente verwendet:  
  
-   Das Steuerelement unterstützt die **IBoundObject**\-Schnittstelle und der Container die **IBoundObjectSite**\-Schnittstelle.  Das Steuerelement erhält die **IBoundObjectSite**\-Schnittstelle des Containers, und der Container erhält die **IBoundObject**\-Schnittstelle vom Steuerelement.  
  
-   Das Steuerelement unterstützt die **IPropNotifySink**\-Schnittstelle und stellt eine Verknüpfung mit dem Container her.  Auf diese Weise kann der Container Benachrichtigungen vom Steuerelement empfangen.  
  
-   Wenn das Steuerelement **INotifyDBEventsSink** unterstützt, kann es Benachrichtigungen von einem RDO\-Datensteuerelement empfangen, nachdem eine Verbindung mit der **INotifyDBEvents**\-Schnittstelle des Datensteuerelements hergestellt wurde.  
  
-   Anschließend kann das Steuerelement \(direkt oder über den Container\) Cursorobjekte vom Datensteuerelement empfangen.  Cursor unterstützen dann Änderungen und die Durchführung von Bildläufen.  Jetzt ist das datengebundene RDO\-Steuerelement erfolgreich gebunden.  
  
## Siehe auch  
 [RDO\-Datenbindung](../../data/ado-rdo/rdo-databinding.md)   
 [Verwenden der RDO\-Datenbindung in Visual C\+\+](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)