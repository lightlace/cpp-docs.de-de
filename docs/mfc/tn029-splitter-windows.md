---
title: 'TN029: Splitterfenster'
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: 6c2f619d9cd619ca598c66ca657faa1b9dccaaa2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305709"
---
# <a name="tn029-splitter-windows"></a>TN029: Splitterfenster

In diesem Hinweis wird beschrieben, die MFC-Bibliothek [CSplitterWnd-Klasse](../mfc/reference/csplitterwnd-class.md), dort finden Sie im Fenster unterteilt und verwaltet der Größenänderung des anderen Fenster im Bereich.

## <a name="splitter-styles"></a>Splitter-Stile

Ein `CSplitterWnd` unterstützt zwei verschiedene Formate der Aufteilung von Windows.

In "statischen Splitterfenstern" erstellt Teilungsfenster. die Bereiche aus, wenn es erstellt wird. Die Reihenfolge und Anzahl der Bereiche ändern sich nie. Teilerleisten werden zum Ändern der Größe der verschiedenen Bereichen. Sie können dieses Format verwenden, eine andere Ansicht-Klasse in den einzelnen Bereichen angezeigt. Die Grafik-Editor von Visual C++ und den Datei-Manager von Windows sind Beispiele für Programme, die diesem Splitter-Format verwenden. Diese Art der Teilungsfenster verwendet Splitter Felder nicht.

In "dynamischen Splitterfenstern" werden als Teilungen und un-unterteilt neuen Ansichten dem Benutzer zusätzliche Bereiche erstellt und zerstört. Dieses Splitters beginnt mit einer einzigen Ansicht und bietet Splitter-Felder für den Benutzer zum Aufteilen von initiieren. Teilungsfenster erstellt ein neues Objekt dynamisch, wenn die Ansicht in eine Richtung aufgeteilt wird. Dieses neue Objekt stellt im neuen dar. Wenn die Sicht mithilfe der Tastatur-Benutzeroberfläche in zwei Richtungen aufgeteilt wird, erstellt Teilungsfenster drei neue Ansichtsobjekte für die drei neuen Bereiche. Während die Teilung aktiv ist, zeigt Windows das Splitter-Feld als eine Teilerleiste zwischen den Bereichen an. Windows zerstört zusätzliche Objekte, wenn der Benutzer eine Teilung entfernt, aber die ursprüngliche Ansicht bleibt bis Teilungsfenster selbst zerstört wird. Microsoft Excel und Microsoft Word sind Beispiele für Anwendungen, die den Stil dynamischer Splitter verwenden.

Wenn Sie beide Arten von Teilungsfenster erstellen, müssen Sie die maximale Anzahl von Zeilen und Spalten, die festlegen, der Splitter angeben. Ein statischer Splitter erstellt Bereiche, um alle Zeilen und Spalten zu füllen. Ein dynamischer Splitter wird nur den ersten Bereich erstellt bei der `CSplitterWnd` erstellt wird.

Die maximale Anzahl der Bereiche, die Sie für den statischen Splitterfenstern angeben können, ist 16 Zeilen von 16 Spalten. Die empfohlenen Konfigurationen sind:

- 1 Zeile X 2 Spalten: in der Regel mit unterschiedlicher Bereiche

- Spalte 2 Zeilen X 1: in der Regel mit unterschiedlicher Bereiche

- 2 Zeilen X 2 Spalten: in der Regel mit ähnliche Bereiche

Die maximale Anzahl der Bereiche, die Sie für den dynamischen Splitterfenstern angeben können, ist 2 Zeilen und 2 Spalten. Die empfohlenen Konfigurationen sind:

- 1 Zeile X 2 Spalten: für Spaltendaten

- Spalte 2 Zeilen X 1: Text oder andere Daten

- 2 Zeilen X 2 Spalten: für Raster oder Tabelle orientierte Daten

## <a name="splitter-examples"></a>Splitter-Beispiele

Viele der MFC-Beispiel-Programmen verwenden Splitterfenster, direkt oder indirekt. Im allgemeinen MFC-Beispiel [VIEWEX](../overview/visual-cpp-samples.md) veranschaulicht verschiedene Verwendungen von statischen Splitterfenstern, wie Sie eine Aufteilung in eine Aufteilung zu platzieren.

Sie können auch Klassen-Assistenten verwenden, zum Erstellen eines neuen mehrere Document Interface (MDI) untergeordneten Rahmenfenster (Klasse), die ein Teilungsfenster enthält. Weitere Informationen über Splitterfenster, finden Sie unter [mehrere Dokumenttypen, Ansichten und Frame Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="terminology-used-by-implementation"></a>Durch Implementierung verwendete Terminologie

Hier ist eine Liste von Begriffen, die für Splitterfenster spezifisch sind:

`CSplitterWnd`: Ein Fenster, der Steuerelemente im Bereich aufteilen und Bildlaufleisten, die alle Bereiche auf einer Zeile oder Spalte gemeinsam verwendet werden. Sie geben mit nullbasierte Anzahl Zeilen und Spalten (der erste Bereich ist die Zeile = 0 und Spalte = 0).

Bereich: Eine anwendungsspezifische-Fenster, die eine `CSplitterWnd` verwaltet. Ein Bereich ist in der Regel ein Objekt, das von abgeleitet ist die [CView-Klasse](../mfc/reference/cview-class.md), jedoch kann [CWnd](../mfc/reference/cwnd-class.md) -Objekt, das über die ID der entsprechenden untergeordneten Fenster verfügt

Verwenden einer `CWnd`-abgeleitete Objekt, und übergeben Sie die RUNTIME_CLASS des Objekts, das die `CreateView` funktionieren wie bei der Verwendung von eine `CView`-abgeleitete Klasse. Die Klasse muss DECLARE_DYNCREATE und IMPLEMENT_DYNCREATE verwenden, da das Framework die dynamische Erstellung zur Laufzeit verwendet. Aber es eine Menge von Code in gibt `CSplitterWnd` ist, die spezifisch für die `CView` -Klasse, [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) wird immer verwendet werden, bevor diese Aktionen ausgeführt werden.

Trennleiste: Ein Steuerelement, das zwischen Zeilen und Spalten der Bereiche eingefügt wird. Es kann verwendet werden, um die Größe der Zeilen oder Spalten der Bereiche anzupassen.

Splitter-Feld: Ein Steuerelement in einer dynamischen `CSplitterWnd` , dass Sie zum Erstellen von neuen Zeilen oder Spalten mit Bereichen verwenden können. Es befindet sich oben auf der vertikalen Bildlaufleiste oder auf der linken Seite der horizontalen Bildlaufleiste.

Splitter-Schnittmenge: Die Schnittmenge von einer vertikalen Trennleiste und einer horizontalen Trennleiste. Sie können sie die Größe einer Zeile und Spalte Bereiche gleichzeitig anpassen ziehen.

## <a name="shared-scroll-bars"></a>Freigegebene Bildlaufleisten

Die `CSplitterWnd` Klasse unterstützt auch die freigegebenen Bildlaufleisten. Diese Schiebeleisten-Steuerelemente sind untergeordnete Elemente von der `CSplitterWnd` und die verschiedenen Bereiche, die in der Splitter freigegeben werden.

Z. B. in einem Fenster 1 Zeile X 2 Spalte können Angabe WS_VSCROLL beim Erstellen der `CSplitterWnd`. Windows erstellt ein spezieller Schiebeleisten-Steuerelement, die zwischen den beiden Fenstern gemeinsam genutzt wird.

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

Wenn der Benutzer die Bildlaufleiste bewegt, werden mit beiden Ansichten WM_VSCROLL-Meldungen gesendet. Wenn beide anzeigen die Position der Schiebeleiste setzt, wird die freigegebenen Bildlaufleiste festgelegt werden.

Beachten Sie, dass freigegebene Bildlaufleisten mit ähnlichen Ansichtsobjekte besonders hilfreich sind. Wenn Sie Sichten, die von anderen Typen in eine Aufteilung kombinieren, müssen Sie möglicherweise speziellen Code zum Koordinieren ihrer Bildlaufpositionen zu schreiben. Alle `CView`-abgeleitete Klasse, verwendet der `CWnd` Bildlaufleiste APIs auf die freigegebene Bildlaufleiste delegieren werden, wenn es vorhanden ist. Die `CScrollView` Implementierung ist ein Beispiel für eine `CView` Klasse, die unterstützt freigegebene Bildlaufleisten. Nicht von abgeleiteten Klassen `CView`, Klassen, die kein Steuerelement Bildlaufleisten verwenden oder Klassen, die Windows-standardimplementierungen verwenden (z. B. `CEditView`) funktioniert nicht mit der freigegebenen Scroll Bar-Funktion von `CSplitterWnd`.

## <a name="minimum-sizes"></a>Minimale Größe

Für jede Zeile eine minimale Zeilenhöhe vorhanden ist, und für jede Spalte ist eine minimale Spaltenbreite. Diesem Minimalwert wird sichergestellt, dass ein Bereich nicht zu klein, um die vollständige detailliert angezeigt werden.

Für ein statisches Splitterfenster ist die anfängliche minimale Zeilengröße Zeilenhöhe und Spaltenbreite 0. Für ein dynamisches Teilungsfenster, werden die anfängliche minimale Zeilengröße Zeilenhöhe und Spaltenbreite festgelegt, durch die *SizeMin* Parameter der `CSplitterWnd::Create` Funktion.

Sie können diese Mindestgrößen ändern, indem Sie mit der [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) und [CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) Funktionen.

## <a name="actual-vs-ideal-sizes"></a>Tatsächliche im Vergleich zu Ideale Größe

Das Layout der Bereiche in einem Splitterfenster hängt von der Größe des Frames, die sie enthält. Wenn ein Benutzer ändert die Größe des Frames mit der `CSplitterWnd` positioniert und ändert die Größe der Bereiche, damit sie möglichst hohe Leistungsfähigkeit verwendet werden.

Der Benutzer kann manuell die Zeile Zeilenhöhe und Width-Größen, oder das Programm festgelegt die optimale Größe mithilfe der `CSplitterWnd` Klasse. Die tatsächliche Größe kann kleiner oder größer als das Ideal sein. Windows wird die tatsächliche Größe angepasst, wenn es nicht genügend Platz ist, um die optimale Größe anzuzeigen oder zu viel Platz auf den rechten oder unteren Rand des Splitterfensters vorhanden ist.

## <a name="custom-controls"></a>Benutzerdefinierte Steuerelemente

Sie können viele Funktionen zum Anpassen des Verhaltens und eine benutzerdefinierte Benutzeroberfläche bereitstellen überschreiben. Sie können diesen ersten Satz alternativen Bilder für die verschiedenen grafischen Komponenten eines unterteilten Fensters zu überschreiben.

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

Rufen Sie diese Funktion, um ein freigegebenes Bildlaufleistensteuerelement zu erstellen. Sie können es zum Erstellen von zusätzlichen Steuerelemente neben die Bildlaufleiste überschreiben.

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

Diese Funktionen implementieren die Logik der dynamisches Teilungsfenster. Sie können diese Optionen, um erweiterte Splitter Logik bereitzustellen, überschreiben.

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>CView-Funktion

Die `CView` Klasse verwendet die folgenden Befehle aus auf hoher Ebene für die Delegierung an die `CSplitterWnd` Implementierung. Da sind die folgenden Befehle virtuell, dem Standard `CView` Implementierung erfordert nicht die gesamte `CSplitterWnd` Implementierung, die verknüpft werden. Für Anwendungen mit `CView` , nicht jedoch `CSplitterWnd`, `CSplitterWnd` Implementierung nicht mit der Anwendung verknüpft werden.

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   Überprüft, ob ID_NEXT_PANE oder ID_PREV_PANE derzeit möglich ist.

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   Führt den Befehl "Nächster Bereich" oder "Vorheriger Bereich".

- `virtual BOOL DoKeyboardSplit();`

   Führt den Tastaturteilbefehl aus, in der Regel "Window Split".

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
