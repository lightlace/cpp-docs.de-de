---
title: Erstellen von modalen Dialogfeldern
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 5de6eeb616f32c7b8829d827988a972e41658530
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174093"
---
# <a name="creating-modal-dialog-boxes"></a>Erstellen von modalen Dialogfeldern

Rufen Sie zum Erstellen eines modalen Dialogfelds eine der zwei öffentliche Konstruktoren, deklariert im [CDialog](../mfc/reference/cdialog-class.md). Rufen Sie als Nächstes des Dialogfeldobjekts [DoModal](../mfc/reference/cdialog-class.md#domodal) Memberfunktion, um das Dialogfeld anzuzeigen und Interaktion mit der Anwendung verwalten, bis der Benutzer, OK auswählt oder Abbrechen. Diese Verwaltung durch `DoModal` ist, was die modales Dialogfeld. Für modale Dialogfelder `DoModal` lädt die Ressource.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
