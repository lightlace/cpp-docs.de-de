---
title: Initialisieren der Teile eines CStatusBarCtrl-Objekts | Microsoft-Dokumentation
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
ms.openlocfilehash: 5fa5c4da3bb91983eceea739d42fae12e73b9b0f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406736"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Initialisieren der Teile eines CStatusBarCtrl-Objekts

Standardmäßig werden in eine Statusleiste Statusinformationen, die über separate Bereiche angezeigt. Diese Bereiche (auch als Teile bezeichnet) können entweder eine Textzeichenfolge, einem Symbol oder beides enthalten.

Verwendung [Sie SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) zum definieren, wie viele Teile und die Länge der Statusleiste angezeigt haben. Nachdem Sie die Teile der Statusleiste erstellt haben, führen Aufrufe an [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) und [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) den Text oder das Symbol für einen bestimmten Teil der Statusleiste fest. Nachdem das Webpart erfolgreich festgelegt wurde, wird das Steuerelement automatisch neu gezeichnet.

Im folgende Beispiel initialisiert eine vorhandene `CStatusBarCtrl` Objekt (`m_StatusBarCtrl`) mit vier Bereiche zur Verfügung, und klicken Sie dann ein Symbol (IDI_ICON1) und Text im zweiten Teil festgelegt.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Weitere Informationen zum Festlegen des einer `CStatusBarCtrl` Objekt, das einfach, finden Sie unter [Festlegen des CStatusBarCtrl-Objektmodus](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

