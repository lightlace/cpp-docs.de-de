---
title: "Klassen für Steuerleisten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44fcecbf1d7ddb6c46469f25349d972c8b317809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="control-bar-classes"></a>Klassen für Steuerleisten
Steuerleisten werden an einem Rahmenfenster angefügt. Sie enthalten Schaltflächen, Statusbereiche oder einer Dialogfeldvorlage. Nicht typisierte Steuerleisten Toolpaletten, so genannte werden implementiert, durch das Anfügen zu einer [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) Objekt.  
  
## <a name="framework-control-bars"></a>Framework-Steuerleisten  
 Diese Schiebeleisten-Steuerelemente sind ein wesentlicher Bestandteil der MFC-Framework. Sie sind einfacher zu verwenden und leistungsfähiger als die Windows Balken steuern, da das Framework integriert sind. Die meisten MFC-Anwendungen verwenden diese Steuerleisten statt der Windows-Steuerleisten.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 Die Basisklasse für MFC-Steuerleisten, die in diesem Abschnitt aufgeführt. Eine Steuerleiste ist ein Fenster, die am Rand eines Rahmenfensters ausgerichtet. Steuerleiste enthält entweder `HWND`-basierte untergeordnete Steuerelemente oder Steuerelemente, die nicht auf Grundlage einer `HWND`, z. B. Schaltflächen der Symbolleiste.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Eine Steuerleiste, die auf einer Dialogfeldvorlage basiert.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Unterstützt eine Symbolleiste, die zusätzliche untergeordnete Fenster in Form von Steuerelementen enthalten kann.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Symbolleisten-Steuerelement Windows, die nicht mithilfe einer Bitmap Befehlsschaltflächen enthalten basierend auf einer `HWND`. Die meisten MFC-Anwendungen verwenden Sie diese Klasse anstelle `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 Die Basisklasse für Statusleiste Steuerelement Windows. Die meisten MFC-Anwendungen verwenden Sie diese Klasse anstelle `CStatusBarCtrl`.  
  
## <a name="windows-control-bars"></a>Windows-Steuerleisten  
 Diese Steuerleisten sind teilschemas für die entsprechenden Windows-Steuerelemente. Da sie nicht mit dem Framework integriert sind, sind sie schwieriger zu verwenden als die oben genannten Steuerleisten. Die meisten MFC-Anwendungen verwenden die zuvor aufgeführten Steuerleisten.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 Implementiert das interne Steuerelement von der `CRebar` Objekt.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Ein horizontales Fenster unterteilt in der Regel Bereiche, in dem eine Anwendung Statusinformationen anzeigen kann.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Stellt die Funktionalität des allgemeinen Windows-Symbolleisten-Steuerelements bereit.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Ein kleines Popupfenster, in dem eine einzelne Textzeile, beschreibt den Zweck eines Tools in einer Anwendung angezeigt.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Verarbeitet die persistente Speicherung von Zustandsdaten Steuerleisten andocken.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

