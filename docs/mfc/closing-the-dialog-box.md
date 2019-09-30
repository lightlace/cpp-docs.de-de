---
title: Schließen des Dialogfelds
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 48ea954552b3ea9aa7193a47fc2a66d731312d77
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685377"
---
# <a name="closing-the-dialog-box"></a>Schließen des Dialogfelds

Ein modales Dialogfeld wird geschlossen, wenn der Benutzer eine seiner Schaltflächen auswählt, in der Regel die Schaltfläche OK oder die Schaltfläche Abbrechen. Wenn Sie die Schaltfläche OK oder Abbrechen auswählen, sendet Windows das Dialog Objekt eine **BN_CLICKED** -Steuerelement Benachrichtigungs Meldung mit der ID der Schaltfläche ( **IDOK** oder **IDCANCEL**). `CDialog` stellt standardhandlerfunktionen für diese Nachrichten bereit: `OnOK` und `OnCancel`. Mit den Standard Handlern wird die `EndDialog`-Member-Funktion aufgerufen, um das Dialogfenster zu schließen. Sie können auch `EndDialog` aus Ihrem eigenen Code abrufen. Weitere Informationen finden Sie in der " [EndDialog](../mfc/reference/cdialog-class.md#enddialog) "-Member-Funktion der Klasse "`CDialog`" in der *MFC-Referenz*.

Wenn Sie das Schließen und Löschen eines nicht modaldialog Felds anordnen möchten, überschreiben Sie `PostNcDestroy`, und rufen Sie den **Delete** -Operator für **diesen** Zeiger auf. Durch [das zerstören des Dialog](../mfc/destroying-the-dialog-box.md) Felds wird erläutert, was als nächstes geschieht.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
