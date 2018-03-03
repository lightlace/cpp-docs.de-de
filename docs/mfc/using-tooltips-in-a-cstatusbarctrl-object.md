---
title: Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf522d17d8abfc4b8dbf53baa24255ab23cfa621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

