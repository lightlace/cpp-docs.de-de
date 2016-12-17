---
title: "Rahmenfensterklassen"
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
  - "Klassen [C++], Fenster"
  - "Dokumentrahmenfenster, Klassen"
  - "Rahmenfensterklassen"
  - "Rahmenfensterklassen, Informationen über Rahmenfensterklassen"
  - "MDI [C++], Rahmenfenster"
  - "MFC [C++], Rahmenfenster"
  - "Einzeldokumentoberfläche (SDI), Rahmenfenster"
  - "Fensterklassen, Rahmen"
  - "Fenster [C++], MDI"
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Rahmenfensterklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Anwendung verfügt über ein "Hauptrahmenfenster," ein Desktopfenster, das normalerweise den Anwendungsnamen in seiner Beschriftung hat.  Jedes Dokument verfügt normalerweise ein Dokumentrahmenfenster "." Ein Dokumentrahmenfenster enthält mindestens einer Ansicht, die die Daten des Dokuments darstellt.  
  
## SDI\- und MDI\-Anwendungen Rahmenfenster in  
 Eine SDI\-Anwendung gibt es ein Rahmenfenster, das von der [CFrameWnd](../mfc/reference/cframewnd-class.md) abgeleitet wird.  Dieses Fenster ist das Hauptrahmenfenster und das Dokumentrahmenfenster.  Für eine MDI\-Anwendung wird das Hauptrahmenfenster von der [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) abgeleitet wird, und die Dokumentrahmenfenster, die untergeordnete MDI\-Fenster sind, werden aus der [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)\- Klasse abgeleitet.  
  
## Verwenden Sie die Rahmenfenster\-Klasse, oder leiten Sie von ihr?  
 Diese Klassen stellen die meisten der Rahmenfensterfunktionalität, die für Ihre Anwendungen benötigen.  Unter normalen Umständen entsprechen das Standardverhalten und die Darstellung, die sie bereitstellen, den Anforderungen.  Wenn Sie zusätzliche Features benötigen, leiten Sie von diesen Klassen.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Rahmenfensterklassen vom Anwendungs\-Assistenten erstellt wurde](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Rahmenfensterformate](../mfc/frame-window-styles-cpp.md)  
  
-   [Die Formate eines Fensters geändert wird, erstellt von MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## Siehe auch  
 [Rahmenfenster](../mfc/frame-windows.md)