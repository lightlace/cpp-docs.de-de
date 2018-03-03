---
title: 'TN029: Splitterfenster | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.windows.splitter
dev_langs:
- C++
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95b7db2678c03b0508a1507567f8bedcf243cd4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn029-splitter-windows"></a>TN029: Splitterfenster
In diesem Hinweis werden die MFC-Bibliothek [CSplitterWnd Klasse](../mfc/reference/csplitterwnd-class.md), dort finden Sie im Fenster unterteilt und verwaltet die Größenänderung des anderen Fenstern Bereich.  
  
## <a name="splitter-styles"></a>Splitter-Stile  
 Ein `CSplitterWnd` unterstützt zwei verschiedene Arten von Teilen von Windows.  
  
 In "statischen Splitterfenstern" erstellt Splitterfensters die Bereiche, wenn es erstellt wird. Die Reihenfolge und die Anzahl der Bereiche ändern sich nie. Trennleisten werden verwendet, um die Größe von der einzelnen Bereichen. Dieses Format können Sie eine andere Ansicht-Klasse in den einzelnen Bereichen angezeigt. Die Grafik-Editor von Visual C++ und die Windows-Manager für Dateiserver sind Beispiele für Programme, die diesem Splitter-Format verwenden. Diese Art der unterteiltes Fenster verwendet Splitter Felder nicht.  
  
 In "dynamischen Splitterfenstern" werden als Teilungen und un Teilungen neuen Ansichten dem Benutzer weitere Bereiche erstellt und zerstört. Diese Splitter beginnt mit einer einzigen Ansicht und bietet Splitter Felder für den Benutzer zum Aufteilen von initiieren. Splitterfensters erstellt dynamisch ein neues Objekt aus, wenn die Ansicht in eine Richtung aufgeteilt wird. Dieses neue Ansichtsobjekt Stellt den neuen Bereich dar. Wenn die Sicht mithilfe der Tastatur-Benutzeroberfläche in zwei Richtungen aufgeteilt wird, erstellt Splitterfensters drei neue Ansichtsobjekte für die drei neuen Bereiche. Während die Teilung aktiv ist, wird das Splitter-Feld als eine Teilerleiste zwischen den Bereichen angezeigt. Windows zerstört zusätzliche Sichtobjekte, wenn der Benutzer eine Teilung entfernt, aber die ursprüngliche Ansicht bleibt bis Splitterfensters selbst zerstört wird. Microsoft Excel und Microsoft Word sind Beispiele für Anwendungen, die den Stil dynamischer Splitter verwenden.  
  
 Wenn Sie beide Arten unterteiltes Fenster erstellen, müssen Sie angeben, die maximale Anzahl von Zeilen und Spalten, die der Splitter verwaltet werden sollen. Ein statischer Splitter erstellt Bereiche, um die Zeilen und Spalten zu füllen. Ein dynamischer Splitter wird nur den ersten Bereich erstellt bei der `CSplitterWnd` wird erstellt.  
  
 Die maximale Anzahl der Bereiche, die Sie für den statischen Splitterfenstern angeben können, ist 16 Zeilen von 16 Spalten. Die empfohlenen Konfigurationen sind:  
  
-   1 Zeilenspalten X 2: in der Regel mit unterschiedlichen Bereichen  
  
-   Spalte 2 Zeilen X 1: in der Regel mit unterschiedlichen Bereichen  
  
-   2 Zeilen X 2 Spalten: in der Regel mit ähnlichen Bereiche  
  
 Die maximale Anzahl von Bereichen, die Sie für den dynamischen Splitterfenstern angeben können, ist 2 Zeilen und 2 Spalten. Die empfohlenen Konfigurationen sind:  
  
-   1 Zeilenspalten X 2: Einspaltig Daten  
  
-   Spalte 2 Zeilen X 1: für Text oder andere Daten  
  
-   2 Zeilen X 2 Spalten: für Raster oder eine Tabelle orientierte Daten  
  
## <a name="splitter-examples"></a>Splitter-Beispiele  
 Viele der MFC-Beispielprogramme verwenden Splitterfenster, direkt oder indirekt. Im allgemeinen MFC-Beispiel [VIEWEX](../visual-cpp-samples.md) veranschaulicht verschiedene Verwendungsmöglichkeiten der statischen Splitterfenstern, einschließlich der Erstellung eines Splitters ein Splitters versehen.  
  
 Klassen-Assistenten können auch um mehrere Document Interface (MDI) untergeordneten Rahmenfenster (Klasse) eine neue zu erstellen, die ein unterteiltes Fenster enthält. Weitere Informationen über Splitterfenster, finden Sie unter [mehrere Dokumenttypen, Ansichten und Rahmenfenster](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## <a name="terminology-used-by-implementation"></a>Durch Implementierung verwendete Terminologie  
 Hier ist eine Liste von Begriffen, die für Splitterfenster spezifisch sind:  
  
 `CSplitterWnd`:  
 Ein Fenster, das Teilen von Bereich Steuerelemente und Bildlaufleisten, die von allen Bereichen in einer Zeile oder Spalte gemeinsam genutzt werden. Geben Sie Zeilen und Spalten mit nullbasierte Zahlen (der erste Bereich ist die Zeile = 0 und Spalte = 0).  
  
 Bereich:  
 Eine anwendungsspezifische-Fenster, die eine `CSplitterWnd` verwaltet. Ein Bereich ist in der Regel ein Objekt, das von abgeleitet ist die [CView-Klasse](../mfc/reference/cview-class.md), jedoch kann eine [CWnd](../mfc/reference/cwnd-class.md) -Objekt, das über die entsprechenden untergeordneten Fenster ID verfügt  
  
 Verwenden eine `CWnd`-abgeleitete Objekt, und übergeben der `RUNTIME_CLASS` des Objekts, das die `CreateView` fungieren, als würden Sie verwenden eine `CView`-abgeleitete Klasse. Muss Ihre Klasse verwenden `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE` , da das Framework die dynamische Erstellung zur Laufzeit verwendet. Es gibt zwar viel Code in `CSplitterWnd` speziell für die `CView` -Klasse, [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) wird immer verwendet werden, bevor diese Aktionen ausgeführt werden.  
  
 Teilerleiste:  
 Ein Steuerelement, das zwischen Zeilen und Spalten des Bereiche eingefügt wird. Es kann verwendet werden, um die Größe der Zeilen oder Spalten der Bereiche anzupassen.  
  
 Splitter-Feld:  
 Ein Steuerelement in einer dynamischen `CSplitterWnd` , dass Sie zum Erstellen von neuen Zeilen oder Spalten mit Bereichen verwenden können. Es befindet sich oben auf der linken Seite des horizontalen Bildlaufleisten oder die vertikalen Schiebeleisten.  
  
 Splitter Schnittmenge:  
 Die Schnittmenge von einer vertikalen Trennleiste und einer horizontalen Trennleiste. Sie können, um die Größe einer Zeile und Spalte Bereiche gleichzeitig anpassen ziehen.  
  
## <a name="shared-scroll-bars"></a>Freigegebene Bildlaufleisten  
 Die `CSplitterWnd` -Klasse unterstützt auch die freigegebenen Bildlaufleisten. Diese Bildlaufleisten-Steuerelementen sind untergeordnete Elemente der `CSplitterWnd` und mit den anderen Bereichen in der Splitter freigegeben werden.  
  
 Beispielsweise geben Sie im Spalte 1 Zeile X 2 Sie festlegbaren WS_VSCROLL beim Erstellen der `CSplitterWnd`. Windows erstellt einen speziellen Bildlaufleisten-Steuerelement, das die beiden Bereiche gemeinsam verwendet werden.  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 Wenn der Benutzer die Bildlaufleiste bewegt `WM_VSCROLL` Nachrichten an beide Ansichten gesendet werden. Bei Ansichten der Position der Bildlaufleiste festlegt, wird die freigegebene Bildlaufleiste festgelegt werden.  
  
 Beachten Sie, dass freigegebene Bildlaufleisten mit ähnlichen Sichtobjekte besonders hilfreich sind. Wenn Sie Sichten unterschiedlicher Typen im eines Splitters kombinieren, müssen Sie möglicherweise ihre Bildlaufpositionen koordinieren speziellen Code schreiben. Alle `CView`-abgeleitete Klasse, verwendet die `CWnd` Bildlaufleiste APIs an die freigegebene Bildlaufleiste Delegieren wird, falls vorhanden. Die `CScrollView` Implementierung ist ein Beispiel für eine `CView` Klasse, die unterstützt freigegebene Bildlaufleisten. Die nicht von abgeleiteten Klassen `CView`, Klassen, die auf nicht-Steuerelement Bildlaufleisten basieren oder Klassen, die standard-Windows-Implementierungen verwenden (z. B. `CEditView`) funktioniert nicht mit der freigegebenen Scroll Bar-Funktion von `CSplitterWnd`.  
  
## <a name="minimum-sizes"></a>Minimale Größe  
 Für jede Zeile eine minimale Zeilenhöhe vorhanden ist, und für jede Spalte eine minimale Spaltenbreite vorhanden ist. Dieser Mindestwert garantiert, dass ein Bereich nicht zu klein, um die vollständige detailliert angezeigt ist.  
  
 Für ein statisches Splitterfenster ist die Anfangszeile minimale Zeilenhöhe und Spaltenbreite 0. Für ein dynamisches Splitterfenster, werden die Anfangszeile minimale Zeilenhöhe und Spaltenbreite festgelegt, indem die `sizeMin` Parameter von der `CSplitterWnd::Create` Funktion.  
  
 Sie können diese minimale Größe ändern, indem Sie mit der [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) und [CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) Funktionen.  
  
## <a name="actual-vs-ideal-sizes"></a>Tatsächliche im Vergleich zu Ideale Größe  
 Das Layout der Bereiche in Splitterfensters hängt von der Größe des Frames, die sie enthält. Wenn ein Benutzer den enthaltenden Frame ändert die Größe der `CSplitterWnd` positioniert und ändert die Größe der Bereiche, damit sie möglichst hohe Leistungsfähigkeit passen.  
  
 Der Benutzer kann manuell die Zeile festlegen Zeilenhöhe und Breite Größe oder das Programm kann mit der ideale Größe festgelegt die `CSplitterWnd` Klasse. Die tatsächliche Größe kann kleiner oder größer als das Ideal sein. Die tatsächliche Größe wird angepasst werden, wenn es nicht genügend Platz ist für die optimale Größe anzuzeigen oder zu viel Speicherplatz auf am rechten oder unteren Rand des Splitterfensters vorhanden ist.  
  
## <a name="custom-controls"></a>Benutzerdefinierte Steuerelemente  
 Sie können viele Funktionen, um benutzerdefiniertes Verhalten und eine angepasste Benutzeroberfläche bereitzustellen, überschreiben. Sie können diesen ersten Satz alternative Bilder für die verschiedenen Grafikkomponenten eines unterteilten Fensters zu überschreiben.  
  
- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
- `virtual void OnInvertTracker(const CRect& rect);`  
  
 Rufen Sie diese Funktion, um eine freigegebene Bildlaufleisten-Steuerelement zu erstellen. Sie können es zum Erzeugen von zusätzlichen Steuerelemente neben der Bildlaufleiste überschreiben.  
  
- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 Diese Funktionen implementieren die Logik des Fensters Dynamische Aufteilung. Sie können diese erweiterte Splitter Logik bereitstellen, überschreiben.  
  
- `virtual void DeleteView(int row, int col);`  
  
- `virtual BOOL SplitRow(int cyBefore);`  
  
- `virtual BOOL SplitColumn(int cxBefore);`  
  
- `virtual void DeleteRow(int rowDelete);`  
  
- `virtual void DeleteColumn(int colDelete);`  
  
## <a name="cview-functionality"></a>CView-Funktion  
 Die `CView` Klasse verwendet die folgenden Befehle auf hoher Ebene für die Delegierung an die `CSplitterWnd` Implementierung. Da virtuell ist, sind die folgenden Befehle dem Standard `CView` Implementierung wird nicht die gesamte `CSplitterWnd` Implementierung, die verknüpft werden. Für Anwendungen mit `CView` , aber nicht `CSplitterWnd`die `CSplitterWnd` Implementierung wird nicht mit der Anwendung verknüpft werden.  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 Überprüft, ob ID_NEXT_PANE oder ID_PREV_PANE derzeit möglich ist.  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 Führt den Befehl "Weiter" oder "Vorherigen Bereich".  
  
 `virtual BOOL DoKeyboardSplit();`  
 Führt die Tastatur split-Befehl ein, in der Regel "Fenster teilen".  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

