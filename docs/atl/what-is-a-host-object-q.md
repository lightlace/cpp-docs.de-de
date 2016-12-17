---
title: "What Is a Host Object?"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "host objects"
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# What Is a Host Object?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Hostobjekt ist ein COM\-Objekt, das den ActiveX\-Steuerelementcontainer darstellt, der über ATL für ein bestimmtes Fenster angegeben wird.  Das Hostobjekt ordnet das Containerfenster, sodass es Meldungen an das Steuerelement feststellen kann, es stellt die notwendigen durch das Steuerelement unter verwendet werden Containerschnittstellen, und macht die [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) und [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md)\-Schnittstellen verfügbar, die es Ihnen ermöglichen, die Umgebung des Steuerelements zu konfigurieren.  
  
 Sie können das Hostobjekt verwenden, um die Ambient\-Eigenschaften des Containers festzulegen.  
  
## Siehe auch  
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)