---
title: "Ausnahmen: OLE-Ausnahmen | Microsoft Docs"
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
  - "Ausnahmebehandlung, OLE"
  - "Ausnahmen, OLE"
  - "OLE-Ausnahmen"
  - "OLE-Ausnahmen, Klassen für Behandlung"
  - "OLE, Ausnahmen"
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausnahmen: OLE-Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Techniken und Funktionen zur Ausnahmebehandlung in OLE sind identisch mit denen für das Behandeln anderen Ausnahmen.  Weitere Informationen über Ausnahmebehandlung finden Sie im Artikel [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
 Alle Ausnahmeobjekte werden von der abstrakten Basisklasse `CException` abgeleitet.  MFC stellt zwei Klassen für die Behandlung von OLE\-Ausnahmen bereit:  
  
-   [COleException](../mfc/reference/coleexception-class.md) zur Behandlung allgemeiner OLE\-Ausnahmen.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) zum Generieren und Behandeln von Ausnahmen OLE\-Dispatchs \(Automatisierung\).  
  
 Der Unterschied zwischen diesen beiden Klassen ist die Informationsmenge, die sie bereitstellen und wo sie verwendet werden.  `COleException` verfügt über einen öffentlichen Datenmember, der den OLE\-Statuscode für die Ausnahme enthält.  `COleDispatchException` bietet mehr Informationen, darunter die folgenden:  
  
-   Ein anwendungsspezifischer Fehlercode  
  
-   Eine Fehlerbeschreibung, wie "Datenträger voll"  
  
-   Ein Hilfekontext, den die Anwendung verwenden kann, um zusätzliche Informationen für den Benutzer bereitzustellen  
  
-   Der Name der Hilfedatei der Anwendung  
  
-   Der Name der Anwendung, die die Ausnahme generiert  
  
 `COleDispatchException` bietet mehr Informationen, sodass sie in Produkte wie Microsoft Visual Basic verwendet werden kann.  Die mündliche Fehlerbeschreibung kann in einem Meldungsfeld oder anderer Benachrichtigungen verwendet werden; Hilfeinformationen können verwendet werden, um den Benutzer zu unterstützen, auf die Bedingungen zu reagieren, die die Ausnahme verursacht haben.  
  
 Zwei globale Funktionen entsprechen den zwei OLE\-Ausnahmeklassen: [AfxThrowOleException](../Topic/AfxThrowOleException.md) und [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md).  Verwenden Sie sie, um allgemeine OLE\-Ausnahme\- und OLE\-Dispatchausnahmen auszulösen, bzw.  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)