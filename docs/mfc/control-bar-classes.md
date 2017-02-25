---
title: "Steuerleistenklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerleisten, Klassen"
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Steuerleistenklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Steuerleisten werden einem Rahmenfenster angefügt.  Sie enthalten Schaltflächen, Statusbereiche oder eine Dialogfeldvorlage.  Die verschobenen frei Steuerleisten, ebenfalls aufgerufen Toolpaletten, werden implementiert, indem Sie sie mit einem [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)\-Objekt angefügt werden.  
  
## Framework\-Steuerleisten  
 Diese Steuerleisten ist ein integraler Bestandteil des MFC\-Frameworks.  Sie sind einfacher verwenden und leistungsstärker als die Windows\-Steuerelement\-Leisten, da sie mit dem Framework integriert werden.  Die meisten MFC\-Anwendungen verwenden diese Steuerleisten anstatt die Windows\-Steuerelement\-Leisten.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 Die Basisklasse für MFC\-Steuerleisten aufgeführt in diesem Abschnitt.  Eine Steuerleiste ist ein Fenster, das am Rand eines Rahmenfensters ausgerichtet wird.  Die Symbolleisten enthält entweder \- basierte untergeordnete Steuerelemente oder Steuerelemente `HWND` nicht auf `HWND` basieren, wie z Symbolleisten\-Schaltflächen.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Eine Steuerleiste, die auf einer Dialogvorlage ist.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Unterstützt eine Symbolleiste, die weitere untergeordnete Fenster in Form von Steuerelementen enthalten kann.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Symbolleisten\-Steuerelement\-Fenster, die Bit\-Übersichtsbefehlsschaltflächen nicht auf `HWND` enthalten.  Die meisten MFC\-Anwendungen verwenden diese Klasse statt `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 Die Basisklasse für StatusBar\-Steuerelement\-Fenster.  Die meisten MFC\-Anwendungen verwenden diese Klasse statt `CStatusBarCtrl`.  
  
## Windows\-Steuerelement\-Leisten  
 Diese Steuerleisten ist wenig Wrapper für die entsprechenden Windows\-Steuerelemente.  Da sie nicht mit dem Framework integriert werden, sind jedoch schwieriger sein als die Steuerleisten zuvor aufgeführten zu verwenden.  Die meisten MFC\-Anwendungen verwenden die Steuerleisten zuvor aufgeführten.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 Implementiert das interne Steuerelement des `CRebar`\-Objekts.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Ein horizontales Fenster, normalerweise unterteilt in Bereiche, in denen eine Anwendung Statusinformationen anzeigen kann.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Stellt die Funktionalität des allgemeinen Windows\-Symbolleisten\-Steuerelements bereit.  
  
## Verwandte Klassen  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Ein kleines Popupfenster, das eine einzelne Textzeile den Zweck eines Tools in einer Anwendung beschreibt anzeigt.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Behandelt dauerhafte Speicherung von Daten des angedockten Zustands für Steuerleisten.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)