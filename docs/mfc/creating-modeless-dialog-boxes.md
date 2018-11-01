---
title: Erstellen von nicht modalen Dialogfeldern
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 4cc2bc0ce54ad658a8bf13e70a8fa54479cbbf79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453703"
---
# <a name="creating-modeless-dialog-boxes"></a>Erstellen von nicht modalen Dialogfeldern

Für ein nicht modales Dialogfeld müssen Sie Ihre eigenen öffentlichen Konstruktor in der Dialogfeldklasse angeben. Klicken Sie zum Erstellen eines nicht modalen Dialogfelds rufen Sie Ihre öffentlichen Konstruktor, und rufen Sie dann des Dialogfeldobjekts [erstellen](../mfc/reference/cdialog-class.md#create) Member-Funktion, um die Ressource zu laden. Rufen Sie **erstellen** während oder nach dem Konstruktoraufruf. Wenn die Ressource, die Eigenschaft hat **WS_VISIBLE**, sofort auf das Dialogfeld wird angezeigt. Wenn nicht, die Sie aufrufen müssen die [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

