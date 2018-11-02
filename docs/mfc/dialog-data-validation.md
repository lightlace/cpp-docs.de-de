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
ms.openlocfilehash: 2283806d3fe7c4ff6bd3abc2ae6a86f5dd176d10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483346"
---
# <a name="dialog-data-validation"></a>Validieren von Dialogfelddaten

Sie können Überprüfung zusätzlich zu den Datenaustausch durch Aufrufen von Funktionen DDV angeben, wie im Beispiel gezeigt [Dialogdatenaustausch](../mfc/dialog-data-exchange.md). Die `DDV_MaxChars` Aufruf im Beispiel wird überprüft, dass die in das Textfeld Steuerelement eingegebene Zeichenfolge nicht mehr als 20 Zeichen ist. Die DDV-Funktion Warnungen in der Regel den Benutzer ein Meldungsfeld an, wenn die Überprüfung schlägt fehl, und legt den Fokus des betreffenden Steuerelements, sodass der Benutzer die Daten erneut eingeben kann. Eine DDV-Funktion für ein bestimmtes Steuerelement muss unmittelbar auf den DDX-Funktion für das gleiche Steuerelement aufgerufen werden.

Sie können auch Ihre eigenen benutzerdefinierten DDX- und DDV-Routinen definieren. Weitere Informationen zu diesem und anderen Aspekte der DDX- und DDV finden Sie unter [MFC technischer Hinweis 26](../mfc/tn026-ddx-and-ddv-routines.md).

Die [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) Schreiben aller der DDX und DDV, die in der datenzuordnung für Sie aufruft.

## <a name="see-also"></a>Siehe auch

[Dialogdatenaustausch und -validierung](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Dialogdatenaustausch](../mfc/dialog-data-exchange.md)

