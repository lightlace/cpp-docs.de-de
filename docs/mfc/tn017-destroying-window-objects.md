---
title: 'TN017: Zerstören von Fensterobjekten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.objects
dev_langs:
- C++
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8286622ec8e7cb739e55a39ce42ed658395551ba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407672"
---
# <a name="tn017-destroying-window-objects"></a>TN017: Zerstören von Fensterobjekten

Dieser Hinweis beschreibt die Verwendung von der [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) Methode. Verwenden Sie diese Methode, wenn Sie benutzerdefinierte Zuordnung möchten `CWnd`--abgeleitete Objekte. In diesem Hinweis wird auch erläutert, warum Sie verwenden sollten [CWnd:: DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) zerstört ein C++-Windows-Objekt, anstatt die **löschen** Operator.

Wenn Sie die Richtlinien in diesem Thema befolgen, müssen Sie einige Probleme der Bereinigung. Diese Probleme können dazu führen, Probleme wie z. B. das Versäumnis, C++-Arbeitsspeicher, Versäumnis, Systemressourcen wie Delete/free `HWND`s oder Freigeben von Objekten zu viele Versuche.

## <a name="the-problem"></a>Das Problem

Jedes Windows-Objekt (Objekt einer Klasse abgeleitet `CWnd`) stellt ein C++-Objekt und ein `HWND`. C++-Objekte im Heap der Anwendung zugeordnet sind und `HWND`s werden die vom Fenstermanager in Systemressourcen zugeordnet. Da es mehrere Möglichkeiten gibt, ein Window-Objekt zu zerstören, müssen wir eine Reihe von Regeln, die das System zu verhindern bieten Ressourcen- oder Arbeitsspeicherverluste. Diese Regeln müssen auch Objekte und Windows-Handles verhindern, dass mehr als einmal zerstört wird.

## <a name="destroying-windows"></a>Zerstören von Windows

Es folgen zwei zulässigen Möglichkeiten, eine Windows-Objekt zu zerstören:

- Aufrufen von `CWnd::DestroyWindow` oder der Windows-API- `DestroyWindow`.

- Löschen explizit mit der **löschen** Operator.

Der erste Fall tritt bei weitem der am häufigsten verwendeten. Dieser Fall gilt, auch wenn Ihr Code nicht aufruft `DestroyWindow` direkt. Wenn der Benutzer direkt ein Rahmenfenster schließt, diese Aktion die WM_CLOSE-Meldung generiert und die Standardantwort für diese Nachricht zum Aufrufen wird `DestroyWindow.` Wenn ein übergeordnetes Fenster zerstört wird, ruft Windows `DestroyWindow` für alle untergeordneten Elemente.

Im zweiten Fall, die Verwendung der **löschen** Operator für Windows-Objekte, dürfte selten passieren. Im folgenden sind einige Fälle, die Verwendung **löschen** die richtige Wahl.

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>Automatische Bereinigung mit CWnd::PostNcDestroy

Wenn das System über ein Windows-Fenster zerstört, ist die letzte Windows-Meldung an das Fenster gesendet WM_NCDESTROY an. Der Standardwert `CWnd` Handler für diese Nachricht ist [zerstören](../mfc/reference/cwnd-class.md#onncdestroy). `OnNcDestroy` Trennen wird die `HWND` aus C++ Objekt, und rufen Sie die virtuelle Funktion `PostNcDestroy`. Einige Klassen überschreiben dieser Funktion können Sie das C++-Objekt zu löschen.

Die standardmäßige Implementierung des `CWnd::PostNcDestroy` nichts, eignet sich für Windows-Objekte, die auf dem Stapelrahmen zugeordnet oder eingebettet in anderen Objekten. Dies ist nicht für Windows-Objekte, die entwickelt wurden, auf dem Heap, ohne alle anderen Objekte zugeordnet werden. Das heißt, ist es nicht für Windows-Objekte, die in anderen C++-Objekte nicht eingebettet werden.

Überschreiben Sie die Klassen, die entwickelt wurden, um allein auf dem Heap reserviert werden die `PostNcDestroy` Methode zum Durchführen einer **löschen**. Diese Anweisung gibt das C++-Objekt zugeordneten Arbeitsspeicher frei. Obwohl der Standardwert `CWnd` Destruktoraufrufe `DestroyWindow` Wenn *M_hWnd* ist nicht NULL ist, dies führt nicht zu einer Endlosschleife, da das Handle während der Phase Cleanup getrennt und NULL werden kann.

> [!NOTE]
>  Das System in der Regel ruft `CWnd::PostNcDestroy` , nachdem sie die Windows-WM_NCDESTROY-Nachricht verarbeitet und die `HWND` und nicht mehr das C++-Fensterobjekt verbunden sind. Das System ruft auch `CWnd::PostNcDestroy` in der Implementierung der meisten [CWnd:: Create](../mfc/reference/cwnd-class.md#create) aufruft, wenn ein Fehler auftritt. Die Regeln für das automatische Cleanup werden weiter unten in diesem Thema beschrieben.

## <a name="auto-cleanup-classes"></a>Automatisches Cleanup-Klassen

Die folgenden Klassen dienen nicht zur automatischen Bereinigung. Sie werden in der Regel in anderen C++-Objekte oder auf dem Stapel eingebettet:

- Alle Windows-Standardsteuerelemente (`CStatic`, `CEdit`, `CListBox`und so weiter).

- Keine untergeordneten Fenster direkt aus dem abgeleiteten `CWnd` (z. B. benutzerdefinierte Steuerelemente).

- Splitterfenster (`CSplitterWnd`).

- Standard-Schiebeleisten-Steuerelemente (abgeleitete Klassen von `CControlBar`, finden Sie unter [technischer Hinweis 31](../mfc/tn031-control-bars.md) für automatisches Löschen von steuerleistenobjekte aktivieren).

- Dialogfelder (`CDialog`) für modale Dialogfelder im Stapelrahmen konzipiert.

- Alle standardmäßigen Dialogfelder, mit Ausnahme von `CFindReplaceDialog`.

- Die Standard-Dialogfelder von Datensatzfeldern von ClassWizard erstellt.

Die folgenden Klassen dienen zur automatischen Bereinigung. In der Regel werden selbst auf dem Heap zugewiesen:

- Main-Frame-Fensters (direkt oder indirekt von abgeleiteten `CFrameWnd`).

- Anzeigen von Windows (direkt oder indirekt von abgeleiteten `CView`).

Wenn Sie diese Regeln unterbrechen möchten, müssen Sie Sie überschreiben die `PostNcDestroy` -Methode in der abgeleiteten Klasse. Klicken Sie zum automatischen Bereinigung der-Klasse hinzufügen, Ihrer Basisklasse aufrufen, und führen Sie dann eine **löschen**. Rufen Sie zum automatischen Bereinigung von Ihrer Klasse entfernen `CWnd::PostNcDestroy` direkt anstelle von der `PostNcDestroy` -Methode der direkten Basisklasse.

Die häufigste Verwendung der automatischen Bereinigungsverhalten ändern ist, erstellen ein nicht modales Dialogfeld an, das zugeordnet werden kann, auf dem Heap.

## <a name="when-to-call-delete"></a>Die Aufruf-löschen

Es wird empfohlen, die Sie aufrufen `DestroyWindow` zerstört ein Windows-Objekt, die C++-Methode oder der globalen `DestroyWindow` API.

Rufen Sie nicht die globale `DestroyWindow` -API, um ein untergeordnetes MDI-Fenster zu zerstören. Verwenden Sie die virtuelle Methode `CWnd::DestroyWindow` stattdessen.

Weitere C++-Fenster führen, die keine automatische Bereinigung von Objekten, mithilfe der **löschen** Operator kann einen Speicherverlust verursachen, wenn Sie versuchen, Sie rufen `DestroyWindow` in die `CWnd::~CWnd` Destruktor, wenn die VTBL nicht in die ordnungsgemäß abgeleitete Klasse verweist. Dies tritt auf, da das System nicht, dass die entsprechende Methode finden kann aufrufen, zerstört. Mithilfe von `DestroyWindow` anstelle von **löschen** werden diese Probleme vermieden. Da dies eine geringfügige Fehler sein kann, wird beim Kompilieren im Debugmodus die folgende Warnung generiert, wenn Sie gefährdet sind.

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

Im Fall von C++-Windows-Objekten, die automatischen Bereinigung durchführen, müssen Sie aufrufen `DestroyWindow`. Bei Verwendung der **löschen** Operator direkt die MFC-Diagnose-Speicherbelegungsfunktion benachrichtigt Sie, dass Sie doppelt so groß wie Freigeben von Arbeitsspeicher sind. Der obigen Abbildung sind, Ihre erste expliziter Aufruf und der indirekten Aufruf von **löschen** in der Implementierung der automatischen Bereinigung der `PostNcDestroy`.

Nach dem Aufruf `DestroyWindow` auf ein nicht-automatischen Bereinigung-Objekt, das C++-Objekt werden weiterhin, aber *M_hWnd* werden auf NULL. Nach dem Aufruf `DestroyWindow` in einem automatischen Bereinigung-Objekt, das C++-Objekt nicht mehr verfügbar, freigegeben, indem der C++-Delete-Operator in der Implementierung der automatischen Bereinigung der `PostNcDestroy`.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

