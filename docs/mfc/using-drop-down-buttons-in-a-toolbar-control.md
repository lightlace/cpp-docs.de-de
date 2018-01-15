---
title: "Verwenden von Dropdown-Schaltflächen in einem Symbolleisten-Steuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs: C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01c09cb2bec4b466928557434767ce49948f46ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Verwenden von DropDown-Schaltflächen in einem Symbolleisten-Steuerelement
Zusätzlich zu Standardschaltflächen kann eine Symbolleiste auch Dropdown-Schaltflächen aufweisen. Eine Dropdown-Schaltfläche wird normalerweise durch das Vorhandensein einer angefügten Pfeil nach unten angegeben.  
  
> [!NOTE]
>  Der angefügte Pfeil nach unten wird nur angezeigt, wenn die `TBSTYLE_EX_DRAWDDARROWS` erweiterten Stil festgelegt wurde.  
  
 Wenn der Benutzer klickt auf diesen Pfeil (oder die Schaltfläche "" selbst, wenn kein Pfeil vorhanden ist), eine `TBN_DROPDOWN` Benachrichtigung an das übergeordnete Element des Symbolleisten-Steuerelements gesendet. Sie können diese Benachrichtigung zu behandeln und ein Popupmenü angezeigt; ähnlich wie das Verhalten von Internet Explorer.  
  
 Das folgende Verfahren veranschaulicht, wie eine Dropdown-Symbolleisten-Schaltfläche ein Popupmenü zu implementieren:  
  
### <a name="to-implement-a-drop-down-button"></a>Implementieren Sie eine Dropdown-Schaltfläche  
  
1.  Einmal Ihre `CToolBarCtrl` Objekt erstellt wurde, legen Sie die `TBSTYLE_EX_DRAWDDARROWS` formatieren, mit dem folgenden Code:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Legen Sie die `TBSTYLE_DROPDOWN` Stil für alle neuen ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) oder [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) oder vorhandenen ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) Schaltflächen, die neben den Dropdown Schaltflächen werden. Das folgende Beispiel veranschaulicht das Ändern einer vorhandenen Schaltfläche in einem `CToolBarCtrl` Objekt:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Hinzufügen einer `TBN_DROPDOWN` Handler zur übergeordneten Klasse des Symbolleistenobjekts.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  Zeigen Sie in den neuen Handler die entsprechenden Popupmenü an Der folgende Code zeigt eine Methode:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

