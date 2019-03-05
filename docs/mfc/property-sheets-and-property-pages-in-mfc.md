---
title: Eigenschaftenblätter und Eigenschaftenseiten in MFC
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: fa8ee3518ad2b32e0eace77f0961eb86ccde1822
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261192"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>Eigenschaftenblätter und Eigenschaftenseiten in MFC

Ein Eigenschaftenblatt, auch bekannt als ein Dialogfeld im Registerformat, wird ein Dialogfeld, das Eigenschaftenseiten enthält. Jede Eigenschaftenseite basiert auf einer Dialogfeldvorlagen-Ressource, und es enthält Steuerelemente. Es wird auf einer Seite mit einer Registerkarte im Vordergrund eingeschlossen. Die Registerkarte die Seite den Namen und gibt seinen Zweck an. Benutzer klicken Sie auf einer Registerkarte im Eigenschaftenfenster Eigenschaft zum Auswählen eines Satzes von Steuerelementen.

Verwenden Sie Seiten, um die Steuerelemente im Eigenschaftenblatt in sinnvolle Sätze zu gruppieren. Das eigenständige Eigenschaftenblatt weist normalerweise auf mehrere Steuerelemente selbst. Diese gelten für alle Seiten.

Eigenschaftenblätter werden basierend auf Klasse [CPropertySheet](../mfc/reference/cpropertysheet-class.md). Eigenschaftenseiten werden basierend auf Klasse [CPropertyPage](../mfc/reference/cpropertypage-class.md).

Ein Eigenschaftenblatt ist eine besondere Art von Dialogfeld, das in der Regel so ändern Sie die Attribute des einige externe Objekt, z. B. die aktuelle Auswahl in einer Ansicht verwendet wird. Das Eigenschaftenblatt besteht aus drei Hauptkomponenten: das Dialogfeld enthält einen oder mehrere Eigenschaftenseiten angezeigten jeweils nur ein, und eine Registerkarte am oberen Rand jeder Seite, die der Benutzer klickt, um diese Seite. Eigenschaftenblätter eignen sich für Situationen, in dem Sie mehrere ähnliche Gruppen von Einstellungen und Optionen zu ändern. Ein Eigenschaftenblatt gruppiert Informationen in einer leicht verständlichen Weise.

> [!NOTE]
>  Wenn Sie versuchen, ein Eigenschaftenblatt mit anzeigen `CPropertySheet::DoModal`, das System möglicherweise eine Ausnahme der ersten Chance zu generieren. Diese Ausnahme tritt auf, da das System versucht, so ändern Sie die [Window-Stile](../mfc/reference/styles-used-by-mfc.md#window-styles) des Objekts vor dem das Objekt erstellt wurde. Weitere Informationen über diese Ausnahme sowie wie Sie die Zukunft zu vermeiden oder zu behandeln, finden Sie unter [CPropertySheet:: DoModal](../mfc/reference/cpropertysheet-class.md#domodal).

## <a name="see-also"></a>Siehe auch

[Eigenschaftenblätter](../mfc/property-sheets-mfc.md)
