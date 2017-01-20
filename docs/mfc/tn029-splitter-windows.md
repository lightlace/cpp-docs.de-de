---
title: "TN029: Splitterfenster"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.windows.splitter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Splitterfenster, Informationen über Splitterfenster"
  - "TN029"
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
caps.latest.revision: 18
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# TN029: Splitterfenster
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt das MFC\- [CSplitterWnd Class](../mfc/reference/csplitterwnd-class.md), das Fensterteilungen stellt und Größenänderung anderer Bereichsfenster verwaltet.  
  
## Splitter\-Formate  
 `CSplitterWnd` unterstützt zwei verschiedenen Stilen des Teilens von Fenstern.  
  
 "In statischen Splittern" stellt das Splitterfenster die Bereiche erstellt, wenn dieser erstellt wird.  Die Reihenfolge und die Anzahl der Fensterbereiche nie ändern.  Splitterleisten werden verwendet, um die verschiedenen Bereiche angepasst.  Sie können diesen Stil verwenden, um eine andere Ansichtsklasse in jedem Bereich anzuzeigen.  Der Visual C\+\+\-Grafikeditor und der Windows\-Datei\-Manager sind Beispiele von Programmen, die dieses Splitterformat verwenden.  Dieses Format des Splitterfensters verwendet nicht Splitterfelder.  
  
 "In den dynamischen Splittern" sind zusätzliche Bereiche erstellt und zerstört, während der Benutzer und die neuen Ansichten der UNTeilungen sich teilt.  Dieser Splitter fängt mit einer einzelnen Ansicht an und stellt Splitterfelder bereit, sodass der Benutzer das Teilen initiiert.  Das Splitterfenster erstellt dynamisch ein neues Ansichtsobjekt, wenn die Ansicht in eine Richtung geteilt wird.  Dieses neue Ansichtsobjekt stellt den neuen Bereich dar.  Wenn die Ansicht in zwei Richtungen geteilt wird, indem die Tastaturschnittstelle verwendet, erstellt das Splitterfenster drei Ansichtsobjekte neue für die drei neuen Bereichen.  Während die Teilung aktiv ist, wird das Windows Splitterfeld als Trennleiste zwischen den Bereichen angezeigt.  Windows zerstört zusätzliche Ansichtsobjekte, wenn der Benutzer eine Aufteilung entfernt, doch die ursprüngliche Ansicht verbleibt, bis das Splitterfenster selbst zerstört wurde.  Microsoft Excel und Microsoft Word sind Beispiele für Anwendungen, die eine dynamische Splitterformat verwenden.  
  
 Wenn Sie entweder erstellen, das vom Splitterfenster Art ist, müssen Sie die maximale Anzahl von Zeilen und Spalten angeben, das der Splitter verwaltet.  Ein statischer Splitter stellt Bereiche erstellt, um alle Zeilen und Spalten angepasst.  Ein dynamischer Splitter stellt nur den ersten Bereich erstellt, wenn ein `CSplitterWnd` erstellt wird.  
  
 Die maximale Anzahl der Fensterbereiche, die Sie für statische Splitter angeben können, ist 16 Zeilen von 16 Spalten.  Die empfohlenen Konfigurationen sind:  
  
-   Zeile 1 x 2 Spalten: Regel mit unähnlichen Bereichen  
  
-   Zeilen 2 x 1 Spalte: Regel mit unähnlichen Bereichen  
  
-   Zeilen 2 x 2 Spalten: normalerweise mit ähnlichen Bereichen  
  
 Die maximale Anzahl der Fensterbereiche, die Sie für dynamische Splitter angeben können, ist 2 Zeilen von 2 Spalten.  Die empfohlenen Konfigurationen sind:  
  
-   Zeile 1 x 2 Spalten: für Säulendaten  
  
-   Zeilen 2 x 1 Spalte: für Text oder andere Daten  
  
-   Zeilen 2 x 2 Spalten: für orientierte Daten des Rasters oder der Tabelle  
  
## Splitter\-Beispiele  
 Viele der MFC\-Beispielprogrammverwendungssplitterfenster direkt oder indirekt.  Das allgemeine Beispiel [VIEWEX\-Beispiel](../top/visual-cpp-samples.md) MFC werden einige Verwendung von statischen Splittern, und wie einen Splitter in einen Splitter platziert.  
  
 Sie können die Erstellung auch verwenden, um eine Rahmenfensterklasse \(MDI\) des neuen mehrfachen Dokumentschnittstelle erstellen untergeordnete, die ein Splitterfenster enthält.  Weitere Informationen über Splitterfenster, finden Sie unter [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## Terminologie von Implementierung  
 Im Folgenden eine Liste von Begriffen, die den Splitterfenstern spezifisch sind:  
  
 `CSplitterWnd`:  
 Ein Fenster, das das Bereich\-Teilen von Steuerelementen von Bildlaufleisten und stellt, die zwischen allen Bereichen auf einer Zeile oder Spalte werden freigegeben.  Die Zeilen und Spalten mit Basiszahlen an \(der erste Bereich ist Zeile und Spalte \= 0 \= 0\).  
  
 Bereich:  
 Ein Fenster, anwendungsspezifisches das `CSplitterWnd` verwaltet.  Ein Bereich ist gewöhnlich ein Objekt, die von [CView Class](../mfc/reference/cview-class.md) abgeleitet wird, kann jedoch [CWnd](../mfc/reference/cwnd-class.md) jedes Objekt sein, das die entsprechende ID des untergeordneten Fensters hat  
  
 Um `CWnd`\- abgeleitetes Objekt, übergeben Sie `RUNTIME_CLASS` des Objekts zur `CreateView`\-Funktion, z Sie wurden, wenn Sie `CView` verwenden \- abgeleitete Klasse.  Die Klasse muss `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE` verwenden, da das Framework dynamische Erstellung zur Laufzeit verwendet.  Obwohl es viel Code in `CSplitterWnd` gibt, der der `CView`\-Klasse spezifisch ist, wird die [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) immer verwendet, bevor diese Aktionen ausgeführt werden.  
  
 Splitter\-Leiste:  
 Ein Steuerelement, das zwischen Zeilen und Spalten aus Bereichen platziert wird.  Es wird möglicherweise verwendet, um die Größe von Zeilen oder Spalten aus Bereichen anzupassen.  
  
 Splitter\-Feld:  
 Ein Steuerelement in dynamischen `CSplitterWnd`, das Sie verwenden können, um neue Zeilen oder Spalten aus Bereichen zu erstellen.  Es befindet sich oben der vertikale Bildlaufleisten oder links von der horizontalen Bildlaufleisten.  
  
 Splitter\-Schnittmenge:  
 Die Schnittmenge einer senkrechten Trennleiste und der horizontalen Leiste.  Sie können sie ziehen, um die Größe einer Zeile und Spalte von Bereichen gleichzeitig anzupassen.  
  
## Freigegebene Bildlaufleisten  
 Die freigegebenen Bildlaufleisten `CSplitterWnd`\-Klasse auch unterstützen  Diese ScrollBar\-Steuerelemente sind untergeordnete Elemente `CSplitterWnd` und werden mit den verschiedenen Bereichen im Splitter freigegeben.  
  
 Beispielsweise in einer Zeile 1 x das Fenster mit 2 Spalten, können Sie WS\_VSCROLL angeben, wenn Sie `CSplitterWnd` erstellen.  Windows stellt ein spezielles ScrollBar\-Steuerelement erstellt, das zwischen den beiden Fenstern freigegeben wird.  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 Wenn der Benutzer die Bildlaufleiste bewegt, werden `WM_VSCROLL` Meldungen zu beiden Ansichten gesendet.  Wenn jede Ansicht die Bildlaufleistenposition festlegt, wird die freigegebene Bildlaufleiste festgelegt.  
  
 Beachten Sie, dass freigegebene Bildlaufleisten mit ähnlichen Ansichtsobjekte am nützlichsten sind.  Wenn Sie Ansichten kombinieren von verschiedenen in einen Splitter müssen, dann können Sie speziellen Code schreiben, um ihre Bildlaufpositionen zu koordinieren.  Alle `CView` abgeleitete Klasse, die die Bildlaufleiste `CWnd` verwendeten APIs, delegiert die freigegebene Bildlaufleiste, falls vorhanden.  Die Implementierung `CScrollView` ist ein Beispiel einer `CView`\-Klasse, die freigegebene Bildlaufleisten unterstützt.  Klassen, die nicht von `CView`, Klassen abgeleitet werden, die auf NichtSteuerelementbildlaufleisten erstellen, oder Klassen, die Standard\-Windows\-Implementierungen verwenden \(beispielsweise, `CEditView`\) können nicht mit der freigegebenen Bildlaufleistenfunktion von `CSplitterWnd`.  
  
## Minimale Größen  
 Für jede Zeile gibt es eine minimale Zeilenhöhe, und für jede Spalte gibt es eine minimale Spaltenbreite.  Das Minimum gewährleistet, dass ein Bereich nicht zu klein ist, im vollständigen Details angezeigt werden.  
  
 Ein statisches Splitterfenster ist die ursprüngliche minimale Zeilenhöhe und die Spaltenbreite 0.  Für ein dynamisches Splitterfenster werden die ursprüngliche minimale Zeilenhöhe und die Breite der Spalte von den `sizeMin`\-Parameter der `CSplitterWnd::Create`\-Funktion festgelegt.  
  
 Sie können diese minimalen Größe ändern, indem Sie die [CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) und [CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md)\-Funktionen.  
  
## Tatsächlich für optimale Größe  
 Das Layout der Bereiche im Splitterfenster hängt von der Größe der Rahmen ab, die sie enthält.  Wenn ein Benutzer die enthaltenen Frames Größe ändert, ordnet `CSplitterWnd` neu an und ändert die Größe der Fensterbereiche damit diese sowie möglich anpassen.  
  
 Der Benutzer kann die Spaltenbreitegrößen Darüber und manuell festlegen, oder das Programm kann die ideale Größe festlegen, indem die `CSplitterWnd`\-Klasse verwendet.  Die tatsächliche Größe kann als das Idealerweise kleiner oder größer sein.  Windows passt das tatsächliche Größe, wenn nicht genug Platz gibt, die ideale Größe anzuzeigen, oder wenn es viel Bereich rechts oder unteren Rand des Splitterfensters gibt.  
  
## Benutzerdefinierte Steuerelemente  
 Sie können viele Funktionen überschreiben, um benutzerdefiniertes Verhalten und eine benutzerdefinierte Schnittstelle bereitzustellen.  Sie können dieses überschreiben zuerst festgelegt, um alternative Bilder für die verschiedenen Komponenten grafischen eines Splitterfensters bereitzustellen.  
  
-   `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
-   `virtual void OnInvertTracker(const CRect& rect);`  
  
 Sie rufen diese Funktion auf, um ein freigegebenes ScrollBar\-Steuerelement zu erstellen.  Sie können diesen überschreiben, um zusätzliche Steuerelemente neben die Bildlaufleiste zu erstellen.  
  
-   `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 Diese Funktionen implementieren die Logik des dynamischen Splitterfensters.  Sie können diese überschreiben, um erweiterte Splitterlogik bereitzustellen.  
  
-   `virtual void DeleteView(int row, int col);`  
  
-   `virtual BOOL SplitRow(int cyBefore);`  
  
-   `virtual BOOL SplitColumn(int cxBefore);`  
  
-   `virtual void DeleteRow(int rowDelete);`  
  
-   `virtual void DeleteColumn(int colDelete);`  
  
## CView\-Funktionalität  
 Die `CView`\-Klasse verwendet die folgenden Befehle auf hoher Ebene, `CSplitterWnd` die Implementierung zu delegieren.  Da diese Befehle virtuell sind, erfordert die Standard\- `CView` Implementierung nicht die gesamte `CSplitterWnd` Implementierung, eingebunden werden.  Für Anwendungen, die `CView` oder die `CSplitterWnd` verwenden, wird die `CSplitterWnd` Implementierung nicht mit der Anwendung verknüpft.  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 Überprüft, ob ID\_NEXT\_PANE oder ID\_PREV\_PANE nur möglich ist.  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 Führt den Befehl "des folgenden Bereichs" oder "des vorherigen Bereichs" aus.  
  
 `virtual BOOL DoKeyboardSplit();`  
 Führt den geteilten Befehl der Tastatur aus, normalerweise "das geteilte Fenster".  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)