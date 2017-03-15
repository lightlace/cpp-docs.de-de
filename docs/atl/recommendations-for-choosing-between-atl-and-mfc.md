---
title: "Recommendations for Choosing Between ATL and MFC | Microsoft Docs"
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
  - "ATL, und MFC (Vergleich)"
  - "MFC, ATL-Unterstützung"
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Recommendations for Choosing Between ATL and MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie Komponenten und Anwendungen entwickeln, können Sie zwischen zwei Ansätzen auswählen \- ATL und MFC \(Microsoft Foundation Class\-Bibliothek\).  
  
## Verwenden von ATL  
 ATL ist eine schnelle, einfache Möglichkeit zu erstellen eine COM\-Komponente in C\+\+ und behalten einen kleinen bei Bedarf.  Verwenden Sie ATL, ein Steuerelement zu erstellen, wenn Sie nicht alle integrierte Funktionen benötigen, die MFC automatisch bereitstellt.  
  
## Verwenden von MFC  
 MFC ermöglicht es Ihnen, vollständige Anwendungen, ActiveX\-Steuerelemente und aktive Dokumente zu erstellen.  Wenn bereits ein Steuerelement mit MFC erstellt haben, können Sie Entwicklung in MFC fortsetzen.  Wenn Sie ein neues Steuerelement erstellen, überprüfen Sie mit ATL, wenn Sie nicht die gesamte integrierte Funktion MFC erfordern.  
  
## Verwenden von ATL in einem MFC\-Projekt  
 Sie können Unterstützung für die Verwendung von ATL in einem vorhandenen MFC\-Projekt hinzufügen, indem Sie einen Assistenten ausführen.  Ausführliche Informationen finden Sie unter [Hinzufügen von ATL\-Unterstützung zu einem MFC\-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
## Siehe auch  
 [Einführung in ATL](../atl/introduction-to-atl.md)