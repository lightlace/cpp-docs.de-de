---
title: "Erstellen eines einfachen schreibgesch&#252;tzten Anbieters"
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
  - "OLE DB-Anbietervorlagen, Erstellen von Anbietern"
  - "OLE DB-Anbieter, Erstellen"
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines einfachen schreibgesch&#252;tzten Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie mithilfe des ATL\-Projekt\-Assistenten und des ATL\-OLE DB\-Anbieter\-Assistenten einen OLE DB\-Anbieter erstellt haben, können Sie weitere zu unterstützende Funktionen hinzufügen.  Entwerfen Sie zunächst den Anbieter, indem Sie feststellen, welche Datentypen an den Consumer gesendet werden und unter welchen Bedingungen dies geschieht.  Dabei ist es wichtig, zu entscheiden, ob Befehle, Transaktionen und sonstige optionale Objekte unterstützt werden müssen.  Ein gut durchdachter Basisentwurf beschleunigt die Implementierung und das Testverfahren.  
  
 Das Beispiel ist in zwei Teile untergliedert:  
  
-   Im ersten Teil erfahren Sie, wie Sie einen [einfachen schreibgeschützten Anbieter erstellen](../../data/oledb/implementing-the-simple-read-only-provider.md), der zwei Zeichenfolgen einliest.  
  
-   Der zweite Teil veranschaulicht, wie Sie den [einfachen schreibgeschützten Anbieter erweitern](../../data/oledb/enhancing-the-simple-read-only-provider.md), indem Sie die `IRowsetLocate`\-Schnittstelle hinzufügen.  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)