---
title: "Verwalten von untergeordneten MDI-Fenstern"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MDICLIENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Untergeordnete Fenster"
  - "Untergeordnete Fenster, und MDICLIENT-Fenster"
  - "Rahmenfenster [C++], Untergeordnetes MDI-Fenster"
  - "MDI [C++], Untergeordnete Fenster"
  - "MDI [C++], Rahmenfenster"
  - "MDICLIENT-Fenster"
  - "Fenster [C++], MDI"
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwalten von untergeordneten MDI-Fenstern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MDI\-Hauptrahmenfenster \(eines pro Anwendung\) enthalten ein bestimmtes untergeordnetes Fenster, das das Fenster **MDICLIENT** aufgerufen wird.  Das **MDICLIENT** Fenster verwaltet den Clientbereich des Hauptrahmenfensters, und untergeordnete Fenster selbst hat: die Dokumentfenster, wird von `CMDIChildWnd` abgeleitet.  Da die Dokumentfenster Rahmenfenster selbst \(untergeordnete MDI\-Fenster\), können Sie ihre eigenen untergeordneten Elemente verfügen.  In allen diesen Fällen, verwaltet das übergeordnete Fenster untergeordneten Fenster und leitet einige Befehle an sie weiter.  
  
 In einem MDI\-Rahmenfenster verwaltet das Rahmenfenster das **MDICLIENT** Fenster und weist dieses zusammen mit Steuerleisten neu an.  Das **MDICLIENT** Fenster verwaltet wiederum alle untergeordneten MDI\-Rahmenfenster.  Die folgende Abbildung zeigt die Beziehung zwischen einem **MDICLIENT** MDI\-Rahmenfenster, dem Fenster und alle untergeordneten Dokumentrahmenfenstern an.  
  
 ![Untergeordnete Fenster in einem MDI&#45;Rahmenfenster](../mfc/media/vc37gb1.png "vc37GB1")  
MDI\-Rahmenfenster und untergeordnete Fenster  
  
 Ein MDI\-Rahmenfenster funktioniert auch in Verbindung mit dem aktuellen untergeordneten MDI\-Fenster, wenn eines gibt.  Die MDI\-Rahmenfensterdelegat\-Befehlsmeldungen dem untergeordneten MDI\-Formular, bevor versucht, sie zu behandeln selbst.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erstellen von Dokumentrahmenfenstern](../mfc/creating-document-frame-windows.md)  
  
-   [Rahmenfensterformate](../mfc/frame-window-styles-cpp.md)  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)