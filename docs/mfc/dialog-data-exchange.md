---
title: Dialogdatenaustausch
ms.date: 11/19/2018
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
ms.openlocfilehash: 9a0199577ea46520c2eadc308812de8a1ce4b514
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "71685807"
---
# <a name="dialog-data-exchange"></a>Dialogdatenaustausch

Wenn Sie den DDX-Mechanismus verwenden, legen Sie die Anfangswerte der Element Variablen des Dialog Objekts fest, in der Regel in Ihrem `OnInitDialog` Handler oder im Dialog-Konstruktor. Unmittelbar bevor das Dialogfeld angezeigt wird, überträgt der DDX-Mechanismus des Frameworks die Werte der Element Variablen an die Steuerelemente im Dialogfeld, wo Sie angezeigt werden, wenn das Dialogfeld selbst als Reaktion auf `DoModal` oder `Create` angezeigt wird. Die Standard Implementierung von `OnInitDialog` in `CDialog` die `UpdateData` Member-Funktion der-Klasse `CWnd` aufruft, um die Steuerelemente im Dialogfeld zu initialisieren.

Derselbe Mechanismus überträgt Werte aus den Steuerelementen an die Element Variablen, wenn der Benutzer auf die Schaltfläche OK klickt (oder wenn Sie die `UpdateData` Member-Funktion mit dem Argument **true**aufrufen). Der Mechanismus für die Validierung von Dialog Daten überprüft alle Datenelemente, für die Sie Validierungsregeln angegeben haben.

In der folgenden Abbildung wird der Dialog Datenaustausch veranschaulicht.

![Dialog Feld-Datenaustausch](../mfc/media/vc379d1.gif "Dialogfeld-Datenaustausch") <br/>
Dialogdatenaustausch

`UpdateData` funktioniert in beiden Richtungen, wie durch den **bool** -Parameter angegeben, der an ihn übergeben wird. Um den Austausch auszuführen, richtet `UpdateData` ein `CDataExchange`-Objekt ein und ruft die außer Kraft setzung der Dialogfeld Klasse der `DoDataExchange` Member-Funktion von `CDialog` auf. `DoDataExchange` ein Argument vom Typ "`CDataExchange`" annimmt. Das `CDataExchange`-Objekt, das an `UpdateData` übergebenen wird, stellt den Kontext des Austauschs dar und definiert solche Informationen als Richtung des Austauschs.

Wenn Sie (oder einen Code-Assistenten) `DoDataExchange` überschreiben, geben Sie einen Rückruf für eine DDX-Funktion pro Datenmember (-Steuerelement) an. Jede DDX-Funktion weiß, wie Sie Daten in beiden Richtungen austauschen können, basierend auf dem Kontext, der durch das `CDataExchange` Argument, das von `UpdateData` an Ihre `DoDataExchange` übergeben wird

MFC bietet viele DDX-Funktionen für verschiedene Arten von Exchange. Das folgende Beispiel zeigt eine `DoDataExchange` Überschreibung, bei der zwei DDX-Funktionen und eine DDV-Funktion aufgerufen werden:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

Die `DDX_`-und `DDV_` Zeilen sind eine Datenzuordnung. Die gezeigten DDX-und DDV-Beispiel Funktionen sind für ein Kontrollkästchen-Steuerelement und ein Bearbeitungsfeld-Steuerelement vorgesehen.

Wenn der Benutzer ein modales Dialogfeld abbricht, wird das Dialogfeld von der `OnCancel` Member-Funktion beendet, und `DoModal` gibt den Wert **IDCANCEL**zurück. In diesem Fall werden keine Daten zwischen dem Dialogfeld und dem Dialogfeld Objekt ausgetauscht.

## <a name="see-also"></a>Siehe auch

[Dialogdatenaustausch und -validierung](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Validieren von Dialogfelddaten](../mfc/dialog-data-validation.md)
