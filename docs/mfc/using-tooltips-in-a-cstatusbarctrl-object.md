---
title: Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt | Microsoft Docs
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
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 323f2861da9fcc498e34792c30c763b4dffb2fd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt
Damit QuickInfos für ein Statusleisten-Steuerelement, erstellen die `CStatusBarCtrl` -Objekt mit den **SBT_TOOLTIPS** Stil.  
  
> [!NOTE]
>  Bei Verwendung einer `CStatusBar` Objekt, das die Statusleiste implementieren, verwenden Sie die `CStatusBar::CreateEx` Funktion. Sie können Sie weitere Formate für den eingebetteten angeben **CStatusBarCtrl** Objekt.  
  
 Sobald die `CStatusBarCtrl` Objekt wurde erfolgreich erstellt wurde, verwenden Sie [CStatusBarCtrl:: setTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) und [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) festlegen und Abrufen der QuickInfo-Text für einen bestimmten Bereich.  
  
 Sobald die QuickInfo festgelegt wurde, wird es angezeigt, nur, wenn das Webpart besitzt, werden ein Symbol und kein Text oder gesamten Text innerhalb des Bereichs angezeigt werden kann. QuickInfos werden im einfachen Modus nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

