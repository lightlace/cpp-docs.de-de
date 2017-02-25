---
title: "OLE-Automatisierungsklassen | Microsoft Docs"
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
  - "Automatisierungsklassen"
  - "Automatisierungsklassen, OLE-Klassen"
  - "Automatisierung, Klassen"
  - "OLE-Automatisierung"
  - "OLE-Automatisierung, Klassen"
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Automatisierungsklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen unterstützen Automatisierungsclients \(Anwendungen, die andere Anwendungen steuern\).  Automatisierungsserver \(Anwendungen, die von anderen Anwendungen gesteuert werden können\), werden von [Dispatchzuordnungen](../mfc/reference/dispatch-maps.md) unterstützt.  
  
 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)  
 Wird verwendet, um aus dem Automatisierungsserver Automatisierungsclient aufzurufen.  Wenn Sie einer Klasse hinzufügen, wird diese Klasse verwendet, um für Automatisierungsserver typsichere Klassen zu erstellen, die eine Typbibliothek erzeugen.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Eine Ausnahme, erstellten aus einem Fehler während der OLE\-Automatisierung.  Automatisierungsausnahmen werden durch Automatisierungsserver ausgelöst und abgefangen von den Automatisierungsclients.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)