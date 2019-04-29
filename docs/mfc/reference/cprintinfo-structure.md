---
title: CPrintInfo-Struktur
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 96b6204fe46cb624d22506b2d3e5c1d7621b1865
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372477"
---
# <a name="cprintinfo-structure"></a>CPrintInfo-Struktur

Speichert Informationen zu einem Auftrag drucken oder die Seitenansicht.

## <a name="syntax"></a>Syntax

```
struct CPrintInfo
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|Gibt die Anzahl der ersten Seite gedruckt wird.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|Gibt die Anzahl der letzten Seite des Dokuments.|
|[CPrintInfo::GetMinPage](#getminpage)|Gibt die Anzahl der ersten Seite des Dokuments.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Gibt die Anzahl der Seiten, die vor der ersten Seite eines DocObject-Elements in einem kombinierten DocObject-Druckauftrag gedruckt wird.|
|[CPrintInfo::GetToPage](#gettopage)|Gibt die Anzahl der letzten Seite gedruckt wird.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|Legt die Anzahl der letzten Seite des Dokuments.|
|[CPrintInfo::SetMinPage](#setminpage)|Legt die Anzahl der ersten Seite des Dokuments.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Enthält ein Flag, der angibt, ob das Framework die print-Schleife fortgesetzt werden soll.|
|[CPrintInfo::m_bDirect](#m_bdirect)|Enthält ein Flag, der angibt, ob das Dokument gedruckt wird direkt (ohne Anzeige des Dialogfelds drucken).|
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Enthält ein Flag, der angibt, ob das gedruckte Dokument DocObject ist.|
|[CPrintInfo::m_bPreview](#m_bpreview)|Enthält ein Flag, der angibt, ob das Dokument wird in der Vorschau angezeigt wird.|
|[CPrintInfo::m_dwFlags](#m_dwflags)|Gibt Vorgänge an DocObject drucken.|
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Enthält einen Zeiger auf eine Struktur Benutzer erstellt.|
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Gibt die Anzahl der gegenwärtig gedruckte Seite.|
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Gibt an, die Projektnummer, die vom Betriebssystem für den aktuellen Druckauftrag zugewiesen|
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Identifiziert die Anzahl der Seiten, die im Vorschaufenster angezeigt. 1 oder 2.|
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Gibt den Offset der ersten Seite des bestimmten DocObject in einem kombinierten DocObject-Druckauftrag an.|
|[CPrintInfo::m_pPD](#m_ppd)|Enthält einen Zeiger auf die `CPrintDialog` für das Dialogfeld "Drucken" verwendete Objekt.|
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Gibt ein Rechteck die aktuelle nutzbaren Seitenbereich an.|
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Enthält eine Formatzeichenfolge für die Seitenzahl Anzeige.|

## <a name="remarks"></a>Hinweise

`CPrintInfo` ist eine Struktur, und verfügt nicht über eine Basisklasse.

Das Framework erstellt ein Objekt des `CPrintInfo` jedes Mal, wenn der Druck oder Befehl "Seitenansicht" wird ausgewählt, und es zerstört, wenn der Befehl abgeschlossen ist.

`CPrintInfo` enthält Informationen zu den Druckauftrag als Ganzes, z. B. den Bereich der Seiten gedruckt werden, und den aktuellen Status des Druckauftrags, wie z. B. das gegenwärtig gedruckte Seite. Einige Informationen befindet sich in einem zugeordneten [CPrintDialog](../../mfc/reference/cprintdialog-class.md) -Objekt dieses Objekt enthält die Werte, die vom Benutzer im Dialogfeld "Drucken" eingegeben.

Ein `CPrintInfo` Objekt zwischen dem Framework und Ihrer Ansichtsklasse übergeben wird, die während des Druckvorgangs und wird verwendet, um den Informationsaustausch zwischen den beiden. Beispielsweise das Framework informiert der Ansichtsklasse der Seite des Dokuments durch Zuweisen eines Werts zum Drucken der `m_nCurPage` Mitglied `CPrintInfo`; die Ansicht Klasse ruft den Wert ab, und führt das eigentliche Drucken der angegebenen Seite.

Ein weiteres Beispiel ist der Fall, bei dem die Länge des Dokuments nicht bekannt ist, bis es gedruckt wird. In diesem Fall überprüft die View-Klasse für das Ende des Dokuments jedes Mal, wenn eine Seite gedruckt wird. Wenn das Ende erreicht ist, legt die Ansichtsklasse der `m_bContinuePrinting` Mitglied `CPrintInfo` auf "false"; Dadurch wird darüber informiert das Framework die print-Schleife zu beenden.

`CPrintInfo` wird verwendet, indem die Memberfunktionen der `CView` aufgelistet unter "Siehe auch". Weitere Informationen zu der von der Microsoft Foundation Class-Bibliothek bereitgestellten Druckarchitektur, finden Sie unter [Frame Windows](../../mfc/frame-windows.md) und [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und in den Artikeln [ Drucken von](../../mfc/printing.md) und [drucken: Mehrseitige Dokumente](../../mfc/multipage-documents.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CPrintInfo`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage

Rufen Sie diese Funktion zum Abrufen der Anzahl der ersten Seite gedruckt werden sollen.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der ersten Seite gedruckt werden sollen.

### <a name="remarks"></a>Hinweise

Dies ist der Wert, der vom Benutzer im Dialogfeld "Drucken" angegeben wird, und es befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member. Wenn der Benutzer einen Wert nicht angegeben, ist der Standardwert der ersten Seite des Dokuments.

##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage

Rufen Sie diese Funktion zum Abrufen der Anzahl der letzten Seite des Dokuments.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der letzten Seite des Dokuments.

### <a name="remarks"></a>Hinweise

Dieser Wert befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member.

##  <a name="getminpage"></a>  CPrintInfo::GetMinPage

Rufen Sie diese Funktion zum Abrufen der Anzahl der ersten Seite des Dokuments.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der ersten Seite des Dokuments.

### <a name="remarks"></a>Hinweise

Dieser Wert befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member.

##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage

Rufen Sie diese Funktion zum Abrufen des Offsets beim Drucken mehrerer DocObject-Elemente von einem DocObject-Client.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Seiten, die vor der ersten Seite eines DocObject-Elements in einem kombinierten DocObject-Druckauftrag gedruckt wird.

### <a name="remarks"></a>Hinweise

Dieser Wert verweist auf die `m_nOffsetPage` Member. Die erste Seite des Dokuments werden fortlaufend die `m_nOffsetPage` Wert + 1, wenn die DocObject mit anderen aktive Dokumente zu drucken. Die `m_nOffsetPage` Element gilt nur, wenn die `m_bDocObject` Wert ist "true".

##  <a name="gettopage"></a>  CPrintInfo::GetToPage

Rufen Sie diese Funktion zum Abrufen der Anzahl der letzten Seite gedruckt werden sollen.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der letzten Seite gedruckt werden sollen.

### <a name="remarks"></a>Hinweise

Dies ist der Wert, der vom Benutzer im Dialogfeld "Drucken" angegeben wird, und es befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member. Wenn der Benutzer einen Wert nicht angegeben, ist der Standardwert der letzten Seite des Dokuments.

##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting

Enthält ein Flag, der angibt, ob das Framework die print-Schleife fortgesetzt werden soll.

### <a name="remarks"></a>Hinweise

Wenn Sie das Drucken-Time-Paginierung durchführen, können Sie dieses Element festlegen, auf "false" in der Überschreibung der `CView::OnPrepareDC` nach das Ende des Dokuments erreicht wurde. Sie müssen keine dieser Variablen zu ändern, wenn Sie die Länge des Dokuments zu Beginn des Druckauftrags mit angegeben haben die `SetMaxPage` Member-Funktion. Die `m_bContinuePrinting` Member ist eine öffentliche Variable des Typs "bool".

##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect

Das Framework legt dieser Member auf "true", wenn das Dialogfeld Drucken für direct-Druck umgangen werden, wird; "False" andernfalls.

### <a name="remarks"></a>Hinweise

Das Dialogfeld "Drucken" wird normalerweise umgangen werden, beim Drucken aus der Shell oder beim Drucken erfolgt mithilfe des Befehls-ID ID_FILE_PRINT_DIRECT.

Sie normalerweise nicht dieses Members ändern, aber wenn Sie ändern, ändern Sie ihn vor dem Aufruf [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) in der Überschreibung der [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject

Enthält ein Flag, der angibt, ob das gedruckte Dokument DocObject ist.

### <a name="remarks"></a>Hinweise

Datenmember `m_dwFlags` und `m_nOffsetPage` sind ungültig, es sei denn, dieses Flag "true" festgelegt ist.

##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview

Enthält ein Flag, der angibt, ob das Dokument wird in der Vorschau angezeigt wird.

### <a name="remarks"></a>Hinweise

Dies wird durch das Framework festgelegt, je nachdem, welcher Befehl des Benutzers ausgeführt. Das Dialogfeld "Drucken" wird nicht für einen Auftrag für die Seitenansicht angezeigt. Die `m_bPreview` Member ist eine öffentliche Variable des Typs "bool".

##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags

Enthält eine Kombination von Flags, die DocObject-Druck-Vorgänge angeben.

### <a name="remarks"></a>Hinweise

Nur gültig, wenn Datenmember `m_bDocObject` ist "true".

Die Flags können es sich um eine oder mehrere der folgenden Werte sein:

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData

Enthält einen Zeiger auf eine Struktur Benutzer erstellt.

### <a name="remarks"></a>Hinweise

Sie können dies verwenden, zum Drucken-spezifische Daten speichern, die Sie nicht in der Ansichtsklasse speichern möchten. Die `m_lpUserData` Member ist eine öffentliche Variable des Typs LPVOID.

##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage

Enthält die Anzahl der aktuellen Seite.

### <a name="remarks"></a>Hinweise

Das Framework ruft `CView::OnPrepareDC` und `CView::OnPrint` einmal für jede Seite des Dokuments und geben Sie einen anderen Wert für diesen Member jedes Mal; die Werte reichen von den Rückgabewert von `GetFromPage` vom zurückgegebenen `GetToPage`. Verwenden Sie dieses Element in Ihrer überschreibungen von `CView::OnPrepareDC` und `CView::OnPrint` die angegebene Seite des Dokuments gedruckt.

Wenn Sie den Vorschaumodus zuerst aufgerufen wird, liest das Framework den Wert des Elements zu bestimmen, welche Seite des Dokuments zunächst in der Vorschau angezeigt werden soll. Sie können den Wert des Elements festlegen, in der Überschreibung der `CView::OnPreparePrinting` aktuelle Position im Dokument des Benutzers zu verwalten, bei der Eingabe im Vorschaumodus. Die `m_nCurPage` Member ist eine öffentliche Variable vom Typ "uint".

##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber

Gibt an, die Projektnummer, die vom Betriebssystem für den aktuellen Druckauftrag zugewiesen.

### <a name="remarks"></a>Hinweise

Dieser Wert kann SP_ERROR sein, wenn der Auftrag noch ausgedruckt noch nicht (d. h., wenn die `CPrintInfo` Objekt neu erstellt wird und noch nicht zum Drucken verwendet wurde), oder wenn beim Starten des Auftrags ein Fehler aufgetreten.

##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages

Enthält die Anzahl der Seiten, die im Vorschaumodus angezeigt. Sie können entweder 1 oder 2 sein.

### <a name="remarks"></a>Hinweise

Die `m_nNumPreviewPages` Member ist eine öffentliche Variable vom Typ "uint".

##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage

Enthält die Anzahl der Seiten, die vor der ersten Seite des bestimmten DocObject in einem kombinierten DocObject-Druckauftrag.

##  <a name="m_ppd"></a>  CPrintInfo::m_pPD

Enthält einen Zeiger auf die `CPrintDialog` Objekt verwendet, um das Dialogfeld "Drucken" für den Auftrag anzuzeigen.

### <a name="remarks"></a>Hinweise

Die `m_pPD` Member ist eine öffentliche Variable deklariert, die als Zeiger auf `CPrintDialog`.

##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw

Gibt den verwendbaren Zeichnungsbereich Seitenrand in logischen Koordinaten an.

### <a name="remarks"></a>Hinweise

Möglicherweise möchten Sie dies in der Überschreibung der verweisen `CView::OnPrint`. Sie können diesen Member verwenden, zum Nachverfolgen welcher Bereich nutzbar bleibt, nachdem Sie Kopfzeilen, Fußzeilen und So weiter drucken. Die `m_rectDraw` Member ist eine öffentliche Variable des Typs `CRect`.

##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc

Enthält eine Formatzeichenfolge, die die Seitenzahlen der Seitenansicht angezeigt. Diese Zeichenfolge besteht aus zwei Teilzeichenfolgen, für Einzelseiten-Anzeige und für Double-Wert-Seite-Anzeige, jeweils durch ein Zeichen "\n" beendet.

### <a name="remarks"></a>Hinweise

Das Framework verwendet "Seite %u\nPages % u-%u\n" als Standardwert an. Wenn Sie ein anderes Format für die Seitenzahlen können eine Formatzeichenfolge angeben, in der Überschreibung der `CView::OnPreparePrinting`. Die `m_strPageDesc` Member ist eine öffentliche Variable des Typs `CString`.

##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage

Rufen Sie diese Funktion zum Angeben der Anzahl der letzten Seite des Dokuments.

```
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>Parameter

*nMaxPage*<br/>
Die Anzahl der letzten Seite des Dokuments.

### <a name="remarks"></a>Hinweise

Dieser Wert befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member. Wenn die Länge des Dokuments bekannt ist, bevor es gedruckt wird, rufen Sie diese Funktion aus der Überschreibung der `CView::OnPreparePrinting`. Wenn die Länge des Dokuments eine Einstellung, die vom Benutzer im Dialogfeld "Drucken" angegebenen abhängig ist, rufen Sie diese Funktion aus der Überschreibung der `CView::OnBeginPrinting`. Wenn die Länge des Dokuments nicht bekannt ist, bevor es gedruckt wird, verwenden Sie die `m_bContinuePrinting` Member zur Steuerung der print-Schleife.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).

##  <a name="setminpage"></a>  CPrintInfo::SetMinPage

Rufen Sie diese Funktion zum Angeben der Anzahl der ersten Seite des Dokuments.

```
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>Parameter

*nMinPage*<br/>
Die Anzahl der ersten Seite des Dokuments.

### <a name="remarks"></a>Hinweise

Seitenzahlen beginnen normalerweise bei 1. Dieser Wert befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView::OnPrint](../../mfc/reference/cview-class.md#onprint)
