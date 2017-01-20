---
title: "SDI und MDI"
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
  - "Rahmenfenster, MDI-Anwendungen"
  - "Rahmenfenster, SDI-Anwendungen"
  - "MDI, und SDI (Vergleich)"
  - "MFC, Fenster"
  - "Einzeldokumentoberfläche (SDI), Anwendungen"
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# SDI und MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC ist es einfach, mit Anwendungen \(MDI\)\- des \(Single Document Interface \(SDI\) und des untergeordneten \(Multiple\-Document zu arbeiten.  
  
 SDI\-Anwendungen ermöglichen nur ein Rahmenfenster des geöffneten Dokuments auf einmal.  MDI\-Anwendungen können mehrere Dokumentrahmenfenstern, um in der gleichen Instanz einer Anwendung geöffnet sein.  Eine MDI\-Anwendung verfügt ein Fenster, in dem mehrere untergeordnete MDI\-Fenster, die selbst Rahmenfenster sind, geöffnet werden können, jedes, das ein separates Dokument enthält.  In einigen Anwendungen können die untergeordneten Fenster aus verschiedenen Typen, z Diagrammfenstern und Arbeitsblattfenstern sein.  In diesem Fall kann die Menüleiste ändern, solange untergeordnete MDI\-Fenster verschiedene Typen aktiviert sind.  
  
> [!NOTE]
>  Unter Windows 95 und höher, sind Anwendungen häufig SDI, da das Betriebssystem eine "Dokument\-zentrierte" Ansicht angenommen hat.  
  
 Weitere Informationen finden Sie unter [Dokumente, Ansichten und Framework](../mfc/documents-views-and-the-framework.md).  
  
## Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)