---
title: "OLE-bezogene Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Klassen [C++]"
  - "OLE [C++], Klassen"
  - "OLE-Klassen [C++]"
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-bezogene Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen stellen verschiedene Dienste und reichen von Ausnahmen zu Dateieingabe und Ausgabe.  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 Wird verwendet, um Elemente zu erstellen, wenn Sie aus anderen Containern angefordert werden.  Diese Klasse dient als Basisklasse für mehrere bestimmte Typen von Factorys, einschließlich `COleTemplateServer`.  
  
 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 Wird verwendet, um Parallelität mit einfachen Remoteprozeduraufrufen \(LRPC\) zu verwalten OLE.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 Verwendet die Schnittstelle COM\- `IStream`, um `CFile` Zugriff an Verbunddateien zu ermöglichen.  Diese Klasse \(abgeleitet von `CFile`\) können MFC\-Serialisierung, um strukturierten OLE Speicherung zu.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Wird verwendet, um das Verschieben, Ändern und Neuausrichtung direkter Elementen zu ermöglichen.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)