---
title: Validieren von Dialogfelddaten
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: c89ed82b148062ddb64fa85eaabda12f44e59895
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685763"
---
# <a name="dialog-data-validation"></a>Validieren von Dialogfelddaten

Sie können die Überprüfung zusätzlich zum Datenaustausch angeben, indem Sie DDV-Funktionen aufrufen, wie im Beispiel in [Dialog Datenaustausch](../mfc/dialog-data-exchange.md)gezeigt. Der `DDV_MaxChars`-aufrufim Beispiel überprüft, ob die im Textfeld-Steuerelement eingegebene Zeichenfolge nicht länger als 20 Zeichen ist. Die DDV-Funktion warnt den Benutzer in der Regel mit einem Meldungs Feld, wenn die Validierung fehlschlägt, und legt den Fokus auf das verletzende Steuerelement, sodass der Benutzer die Daten erneut eingeben kann. Eine DDV-Funktion für ein bestimmtes Steuerelement muss unmittelbar nach der DDX-Funktion für dasselbe Steuerelement aufgerufen werden.

Sie können auch eigene benutzerdefinierte DDX-und DDV-Routinen definieren. Ausführliche Informationen zu diesen und anderen Aspekten von DDX und DDV finden [Sie unter MFC Technical Note 26](../mfc/tn026-ddx-and-ddv-routines.md).

Mit dem [Assistenten zum Hinzufügen von Mitgliedsvariablen](../ide/add-member-variable-wizard.md) werden alle DDX-und DDV-Aufrufe in der Datenzuordnung geschrieben.

## <a name="see-also"></a>Siehe auch

[Dialogdatenaustausch und -validierung](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Dialogdatenaustausch](../mfc/dialog-data-exchange.md)
