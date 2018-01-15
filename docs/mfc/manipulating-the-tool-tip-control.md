---
title: Bearbeiten des QuickInfo-Steuerelements | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae30c39a26379aaa8a6f786b5fe2542abde2c2df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="manipulating-the-tool-tip-control"></a>Bearbeiten des QuickInfo-Steuerelements
Klasse `CToolTipCtrl` bietet eine Gruppe von Member Funktionen, die die verschiedenen Attribute steuern die `CToolTipCtrl` Objekt und das QuickInfo-Fenster.  
  
 Die anfängliche, Popup- und Wiederholungsdauern für QuickInfo-Fenster können festgelegt und, die durch Aufrufe von abgerufen [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) und [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime).  
  
 Ändern Sie die Darstellung der QuickInfo-Fenster mit den folgenden Funktionen:  
  
-   [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) und [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) ab oder legt der Abstand zwischen dem QuickInfo-Rahmen und das Tool QuickInfo-Text.  
  
-   [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) und [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) ab oder legt die maximale Breite des Tools QuickInfo-Fensters.  
  
-   [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) und [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) ab oder legt die Farbe des Hintergrunds des Tools QuickInfo-Fensters.  
  
-   [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) und [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) ab oder legt die Textfarbe des Tools QuickInfo-Fensters.  
  
 In der Reihenfolge für das QuickInfo-Steuerelement von wichtige Nachrichten benachrichtigt werden, z. B. **WM_LBUTTONXXX** Nachrichten, Sie müssen die Nachrichten weiterleiten, um die QuickInfo-Steuerelement. Die beste Methode für dieses Relay wird, um einen Aufruf an [CToolTipCtrl:: RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)in die `PreTranslateMessage` Funktion des Besitzerfensters. Das folgende Beispiel veranschaulicht eine mögliche Methode (vorausgesetzt, das QuickInfo-Steuerelement heißt `m_ToolTip`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]  
  
 Um ein Tipp Toolfenster sofort zu entfernen, rufen Sie die [Pop](../mfc/reference/ctooltipctrl-class.md#pop) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

