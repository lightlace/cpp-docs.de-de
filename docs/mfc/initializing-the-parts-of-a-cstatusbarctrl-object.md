---
title: Initialisieren der Teile eines CStatusBarCtrl-Objekts | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89cea1516924530f821003affd96e2848687882b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Initialisieren der Teile eines CStatusBarCtrl-Objekts
Standardmäßig wird eine Statusleiste Statusinformationen über separate Bereiche angezeigt: Diese Bereiche (auch als Komponenten bezeichnet) können entweder eine Textzeichenfolge, ein Symbol oder beides enthalten.  
  
 Verwendung [Sie SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) zum definieren, wie viele Teile und die Länge die Statusleiste haben wird. Nachdem Sie die Teile der Statusleiste erstellt haben, Aufrufe an [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) und [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) der Text bzw. kein Symbol für einen bestimmten Teil der Statusleiste festlegen. Nachdem das Webpart erfolgreich festgelegt wurde, wird das Steuerelement automatisch neu gezeichnet.  
  
 Im folgende Beispiel initialisiert eine vorhandene `CStatusBarCtrl` Objekt (`m_StatusBarCtrl`) mit vier Bereichen und legt dann im zweiten Schritt werden ein Symbol (IDI_ICON1) und etwas Text.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 Weitere Informationen zum Festlegen des eine `CStatusBarCtrl` Objekt, das einfache, finden Sie unter [Festlegen des CStatusBarCtrl-Objekts](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

