---
title: "COM+&#160;1.0-Unterst&#252;tzung in ATL-Projekten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.MTS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, COM+ 1.0-Unterstützung"
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# COM+&#160;1.0-Unterst&#252;tzung in ATL-Projekten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dem [ATL\-Projekt\-Assistenten](../../atl/reference/creating-an-atl-project.md) können Sie ein Projekt erstellen, das grundlegende Unterstützung für COM\+ 1.0\-Komponenten umfasst.  
  
 COM\+ 1.0 ist für die Entwicklung verteilter, komponentenbasierter Anwendungen ausgelegt.  Darüber hinaus bietet es eine Laufzeitinfrastruktur für die Bereitstellung und Verwaltung dieser Anwendungen.  
  
 Wenn Sie das Kontrollkästchen **COM\+ 1.0\-Unterstützung** aktivieren, ändert der Assistent das Buildskript während des Verknüpfungsvorgangs.  Das COM\+ 1.0\-Projekt wird insbesondere mit den folgenden Bibliotheken verknüpft:  
  
-   comsvcs.lib  
  
-   Mtxguid.lib  
  
 Wenn Sie das Kontrollkästchen **COM\+ 1.0\-Unterstützung** aktivieren, können Sie außerdem **Unterstützung für Komponentenregistrierung** auswählen.  Über die Komponentenregistrierung kann das COM\+ 1.0\-Objekt eine Komponentenliste abrufen, Komponenten registrieren oder die Registrierung von Komponenten \(einzeln oder gesamt\) aufheben.  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmieren mit ATL\- und C\-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)