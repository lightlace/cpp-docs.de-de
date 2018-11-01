---
title: Schließen des Dialogfelds
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: fe57c5603f1b0e9ea0b6fb9e6ea8d80bec961f6e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448112"
---
# <a name="closing-the-dialog-box"></a>Schließen des Dialogfelds

Ein modales Dialogfeld wird geschlossen, wenn der Benutzer die Schaltflächen, in der Regel auf die Schaltfläche "OK" oder "Abbrechen"-Schaltfläche auswählt. Wählen die Schaltfläche "OK" oder "Abbrechen" bewirkt, dass Windows, um das Dialogfeldobjekt senden eine **BN_CLICKED** Steuerelement-Benachrichtigung mit der Schaltfläche-ID des, entweder **IDOK** oder **IDCANCEL**. `CDialog` Handlerfunktionen für diese Nachrichten stellt: `OnOK` und `OnCancel`. Der Standard-Handler-Aufruf die `EndDialog` Member-Funktion, um das Dialogfeld zu schließen. Sie können auch aufrufen `EndDialog` über Ihren eigenen Code. Weitere Informationen finden Sie unter den [EndDialog](../mfc/reference/cdialog-class.md#enddialog) Memberfunktion der Klasse `CDialog` in die *MFC-Referenz*.

Ordnen Sie zum Schließen und das Löschen eines nicht modalen Dialogfelds, außer Kraft setzen `PostNcDestroy` und Aufrufen der **löschen** Operators für die **dies** Zeiger. [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md) wird erläutert, was als Nächstes geschieht.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

