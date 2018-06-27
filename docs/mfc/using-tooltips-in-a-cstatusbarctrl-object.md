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
ms.openlocfilehash: 9cce98e4a3b3ffd506607529b9fea6f0c1114cc3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951265"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt
Erstellen Sie zum Aktivieren von QuickInfos für ein Statusleisten-Steuerelement die `CStatusBarCtrl` Objekt mit dem SBT_TOOLTIPS-Format.  
  
> [!NOTE]
>  Bei Verwendung einer `CStatusBar` Objekt, das die Statusleiste implementieren, verwenden Sie die `CStatusBar::CreateEx` Funktion. Sie können Sie weitere Formate für den eingebetteten angeben `CStatusBarCtrl` Objekt.  
  
 Sobald die `CStatusBarCtrl` Objekt wurde erfolgreich erstellt wurde, verwenden Sie [CStatusBarCtrl:: setTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) und [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) festlegen und Abrufen der QuickInfo-Text für einen bestimmten Bereich.  
  
 Sobald die QuickInfo festgelegt wurde, wird es angezeigt, nur, wenn das Webpart besitzt, werden ein Symbol und kein Text oder gesamten Text innerhalb des Bereichs angezeigt werden kann. QuickInfos werden im einfachen Modus nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

