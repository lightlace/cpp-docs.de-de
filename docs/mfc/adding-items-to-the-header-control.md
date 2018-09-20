---
title: Hinzufügen von Elementen zum Headersteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0eb06a15cac87b063ada1cbe8f130b3464be0b0a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447179"
---
# <a name="adding-items-to-the-header-control"></a>Hinzufügen von Elementen zum Headersteuerelement

Nach dem Erstellen Ihrer Kopfzeilen-Steuerelements ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) in das übergeordnete Fenster, wie viele Headerelemente hinzufügen, "" wie Sie benötigen: in der Regel eine pro Spalte.

### <a name="to-add-a-header-item"></a>Ein Headerelement hinzufügen

1. Vorbereiten einer [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) Struktur.

1. Rufen Sie [InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), indem Sie die Struktur.

1. Wiederholen Sie die Schritte 1 und 2 für zusätzliche Elemente.

Weitere Informationen finden Sie unter [Hinzufügen eines Elements zu einem Kopfzeilen-Steuerelement](/windows/desktop/Controls/header-controls) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

