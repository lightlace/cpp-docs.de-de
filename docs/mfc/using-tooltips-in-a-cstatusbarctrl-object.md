---
title: Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 3f9a1fec7eb951fa76c542e09df751b4c58ddb16
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265085"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt

Erstellen Sie zum Aktivieren von QuickInfos für ein Statusleisten-Steuerelement die `CStatusBarCtrl` Objekt mit dem SBT_TOOLTIPS-Format.

> [!NOTE]
>  Bei Verwendung einer `CStatusBar` Objekt, das die Statusleiste implementieren, verwenden Sie die `CStatusBar::CreateEx` Funktion. Damit können Sie weitere Formate für den eingebetteten angeben `CStatusBarCtrl` Objekt.

Sobald die `CStatusBarCtrl` Objekt wurde erfolgreich erstellt wurde, verwenden Sie [CStatusBarCtrl:: setTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) und [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) festlegen und Abrufen der QuickInfo-Text für einen bestimmten Bereich.

Wenn die QuickInfo festgelegt wurde, wird es angezeigt, nur dann, wenn das Webpart ein Symbol und kein Text besitzt oder wenn der gesamte Text in das Webpart nicht angezeigt werden kann. QuickInfos werden im einfachen Modus nicht unterstützt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
