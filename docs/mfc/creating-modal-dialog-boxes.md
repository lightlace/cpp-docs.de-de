---
title: Erstellen von modalen Dialogfeldern
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: eb9aab7e8579fbbbfdf5d0f2dca9b6e6abea0066
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657338"
---
# <a name="creating-modal-dialog-boxes"></a>Erstellen von modalen Dialogfeldern

Rufen Sie zum Erstellen eines modalen Dialogfelds eine der zwei öffentliche Konstruktoren, deklariert im [CDialog](../mfc/reference/cdialog-class.md). Rufen Sie als Nächstes des Dialogfeldobjekts [DoModal](../mfc/reference/cdialog-class.md#domodal) Memberfunktion, um das Dialogfeld anzuzeigen und Interaktion mit der Anwendung verwalten, bis der Benutzer, OK auswählt oder Abbrechen. Diese Verwaltung durch `DoModal` ist, was die modales Dialogfeld. Für modale Dialogfelder `DoModal` lädt die Ressource.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

