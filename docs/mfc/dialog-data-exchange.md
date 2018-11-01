---
title: Dialogdatenaustausch
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
ms.openlocfilehash: a72be4daf6c10a7d16b8558bfdddb8337ff1b1be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566282"
---
# <a name="dialog-data-exchange"></a>Dialogdatenaustausch

Wenn Sie den DDX-Mechanismus verwenden, Sie legen die Anfangswerte des Dialogfelds Membervariablen des Objekts, in der Regel in Ihre `OnInitDialog` Ereignishandler oder der Dialogfeldkonstruktor. Sofort die Framework DDX-Mechanismus bevor das Dialogfeld angezeigt wird, die Werte der Membervariablen auf die Steuerelemente in das Dialogfeld, überträgt, in dem sie angezeigt werden, wenn das Dialogfeld angezeigt wird als Reaktion auf `DoModal` oder `Create`. Die standardmäßige Implementierung des `OnInitDialog` in `CDialog` Aufrufe der `UpdateData` Memberfunktion der Klasse `CWnd` um die Steuerelemente in das Dialogfeld zu initialisieren.

Derselbe Mechanismus überträgt die Werte aus den Steuerelementen, die die Membervariablen klickt der Benutzer die Schaltfläche "OK" (oder bei jedem Aufruf der `UpdateData` Member-Funktion mit dem Argument **"true"**). Der Mechanismus Dialogfeld zur Überprüfung überprüft, ob alle Datenelemente, die für die Sie Validierungsregeln angegeben.

Die folgende Abbildung veranschaulicht die Dialogfeld-Datenaustausch.

![Dialogfeld-Datenaustausch](../mfc/media/vc379d1.gif "vc379d1") Dialogfeld-Datenaustausch

`UpdateData` funktioniert in beide Richtungen, laut der **"bool"** Parameter übergeben. Um den Austausch, die durchzuführen `UpdateData` richtet eine `CDataExchange` -Objekt und ruft der Dialogfeldklasse-Überschreibung `CDialog`des `DoDataExchange` Member-Funktion. `DoDataExchange` akzeptiert ein Argument des Typs `CDataExchange`. Die `CDataExchange` -Objekt übergeben, um `UpdateData` stellt den Kontext des Exchange, definieren solche Informationen als die Richtung der Exchange-dar.

Wenn Sie (oder eines Code-Assistenten) außer Kraft setzen `DoDataExchange`, geben Sie einen Aufruf einer DDX-Funktion pro Datenmember (Steuerelement). Jede Funktion DDX weiß, wie Datenaustausch in beide Richtungen basierend auf dem Kontext vom die `CDataExchange` Argument übergeben wird, um Ihre `DoDataExchange` von `UpdateData`.

MFC bietet viele DDX-Funktionen für verschiedene Arten von Exchange. Das folgende Beispiel zeigt eine `DoDataExchange` außer Kraft setzen, die in der zwei DDX-Funktionen und eine DDV-Funktion aufgerufen werden:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

Die `DDX_` und `DDV_` Linien stehen für eine datenzuordnung. Die Beispiel-DDX- und DDV Funktionen jeweils sind bzw. für ein Kontrollkästchen-Steuerelement und ein Eingabefeld Steuerelement.

Wenn der Benutzer ein modales Dialogfeld, bricht der `OnCancel` Memberfunktion schließt das Dialogfeld und `DoModal` gibt den Wert **IDCANCEL**. In diesem Fall werden keine Daten zwischen das Dialogfeld und dem Dialogfeldobjekt ausgetauscht.

## <a name="see-also"></a>Siehe auch

[Dialogdatenaustausch und -validierung](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Validieren von Dialogfelddaten](../mfc/dialog-data-validation.md)

