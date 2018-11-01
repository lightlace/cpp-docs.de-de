---
title: Verwenden von CToolTipCtrl zum Erstellen und Bearbeiten eines CToolTipCtrl-Objekts
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: cc5ea515aa132bb390fa5e273cedc5f125bb3046
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561251"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>Verwenden von CToolTipCtrl zum Erstellen und Bearbeiten eines CToolTipCtrl-Objekts

Es folgt ein Beispiel der [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) Nutzung:

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Zum Erstellen und Bearbeiten von CToolTipCtrl

1. Erstellen der `CToolTipCtrl` Objekt.

1. Rufen Sie [erstellen](../mfc/reference/ctooltipctrl-class.md#create) zum Erstellen von Windows QuickInfo common-Steuerelements, und fügen Sie ihn auf die `CToolTipCtrl` Objekt.

1. Rufen Sie [Sie AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) um ein Tool mit dem QuickInfo-Steuerelement, zu registrieren, damit die Informationen gespeichert, in der QuickInfo angezeigt wird, wenn der Cursor auf das Tool befindet.

1. Rufen Sie [Sie SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) , legen Sie die Informationen, die eine QuickInfo für ein Tool verwaltet.

1. Rufen Sie [Sie SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) um eine neue umschließende Rechteck für ein Tool festzulegen.

1. Rufen Sie [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) um einen Punkt, um zu bestimmen, ob es das umschließende Rechteck des angegebenen Tools befindet und wenn dies der Fall zu testen, Abrufen von Informationen zu diesem Tool.

1. Rufen Sie [Sie GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) zum Abrufen der Anzahl der Tools, die bei der QuickInfo-Steuerelement registriert.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

