---
title: "ATL-Verbindungspunkte | Microsoft Docs"
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
  - "ATL, Verbindungspunkte"
  - "Verbindungspunkte [C++], Info über Verbindungspunkte"
  - "Verbindungen, Verbindungspunkte"
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL-Verbindungspunkte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein verbindungsfähiges Objekt ist eines, das Ausgangsschnittstellen unterstützt.  Eine Ausgangsschnittstelle ermöglicht dem Objekt die Kommunikation mit einem Client.  Für jede Ausgangsschnittstelle macht das verbindungsfähige Objekt einen Verbindungspunkt verfügbar.  Jede Ausgangsschnittstelle wird von einem Client auf einem Objekt, das als Sink bezeichnet wird, implementiert.  
  
 ![Verbindungspunkte](../atl/media/vc2zw31.png "vc2ZW31")  
  
 Jeder Verbindungspunkt unterstützt die [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)\-Schnittstelle.  Das verbindungsfähige Objekt macht seine Verbindungspunkte am Client über die [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)\-Schnittstelle verfügbar.  
  
## In diesem Abschnitt  
 [ATL\-Connection Point\-Klassen](../atl/atl-connection-point-classes.md)  
 Beschreibt kurz die ATL\-Klassen, die Verbindungspunkte unterstützen.  
  
 [Hinzufügen von Verbindungspunkten zu einem Objekt](../atl/adding-connection-points-to-an-object.md)  
 Beschreibt die Schritte, um einem Objekt Verbindungspunkte hinzuzufügen.  
  
 [Beispiel für ATL\-Verbindungspunkt](../atl/atl-connection-point-example.md)  
 Enthält ein Beispiel für das Deklarieren eines Verbindungspunktes.  
  
## Verwandte Abschnitte  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)