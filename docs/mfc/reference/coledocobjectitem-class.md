---
title: COleDocObjectItem-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
ms.openlocfilehash: 382960b4dc4dcfa61c836a87044dd14585756174
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769641"
---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem-Klasse

Implementiert "Active Document Containment".

## <a name="syntax"></a>Syntax

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Erstellt eine `COleDocObject` Element.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Gibt die Container-Anwendung-Dokument mit den Standardeinstellungen für den Drucker aus.|
|[COleDocObjectItem::ExecCommand](#execcommand)|Führt den Befehl, der vom Benutzer angegeben wird.|
|[COleDocObjectItem::GetActiveView](#getactiveview)|Ruft die aktive Ansicht des Dokuments ab.|
|[COleDocObjectItem::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten in der containeranwendung Dokument ab.|
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Bereitet die Container-Anwendung-Dokument für den Druck.|
|[COleDocObjectItem::OnPrint](#onprint)|Gibt die Container-Anwendung-Dokument.|
|[COleDocObjectItem::QueryCommand](#querycommand)|Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.|
|[COleDocObjectItem::Release](#release)|Die Verbindung mit einer OLE-Element verknüpfte frei, und geschlossen wird, wenn es geöffnet war. Die Client-Element wird nicht zerstört werden.|

## <a name="remarks"></a>Hinweise

In MFC wird auf ähnliche Weise ein aktiven Dokuments behandelt, für das eine reguläre, direkte bearbeitbaren einbetten, die folgenden Unterschiede:

- Die `COleDocument`-abgeleitete Klasse weiterhin verwaltet eine Liste der derzeit eingebetteten Elemente; allerdings sind diese Elemente möglicherweise `COleDocObjectItem`-abgeleiteten Elemente.

- Wenn ein aktives Dokument aktiv ist, nimmt sie den gesamten Clientbereich der Ansicht, wenn er direkt aktiv ist.

- Active Document-Container verfügt über Vollzugriff auf die **Hilfe** Menü.

- Die **Hilfe** Menü Menüelemente für Active Document-Container und Server enthält.

Da die Active Document-Container besitzt die **Hilfe** im Menü der Container ist dafür verantwortlich, Server **helfen** Menü Nachrichten an den Server. Diese Integration erfolgt durch `COleDocObjectItem`.

Weitere Informationen für das Zusammenführen von Menüs und Aktivierung des aktiven Dokuments finden Sie unter Übersicht über die [Active Document-Container](../../mfc/active-document-containment.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="coledocobjectitem"></a>  COleDocObjectItem::COleDocObjectItem

Rufen Sie diese Memberfunktion zum Initialisieren der `COleDocObjectItem` Objekt.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Parameter

*pContainerDoc*<br/>
Ein Zeiger auf die `COleDocument` Objekt fungiert als active Document-Container. Dieser Parameter muss NULL, um IMPLEMENT_SERIALIZE zuzulassen. Normalerweise werden OLE-Elementen mit einem Dokument für nicht-NULL-Zeiger erstellt.

##  <a name="dodefaultprinting"></a>  DoDefaultPrinting

Wird aufgerufen, durch das Framework in ein Dokument mit den Standardeinstellungen.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*pCaller*<br/>
Ein Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, das den Druckbefehl gesendet werden.

*pInfo*<br/>
Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das beschreibt, den Auftrag gedruckt werden sollen.

##  <a name="execcommand"></a>  COleDocObjectItem::ExecCommand

Rufen Sie diese Memberfunktion zum Ausführen des Befehls, der vom Benutzer angegeben wird.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Parameter

*nCmdID*<br/>
Der Bezeichner des auszuführenden Befehls. Muss in der Gruppe identifizierte *PguidCmdGroup*.

*nCmdExecOpt*<br/>
Gibt Optionen für die Ausführung des Befehls an. Standardmäßig wird beim Ausführen des Befehls ohne Aufforderung des Benutzers festgelegt. Finden Sie unter [OLECMDEXECOPT](/windows/desktop/api/docobj/ne-docobj-olecmdexecopt) für eine Liste von Werten.

*pguidCmdGroup*<br/>
Eindeutiger Bezeichner der Befehlsgruppe. Standardmäßig ist NULL, dies gibt an, die Standardgruppe. Der Befehl übergeben *nCmdID* müssen der Gruppe angehören.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn erfolgreich; Andernfalls können Sie eine der folgenden Fehlercodes zurückgegeben.

|Wert|Beschreibung|
|-----------|-----------------|
|E_UNEXPECTED|Unerwarteter Fehler aufgetreten.|
|E_FAIL|Es ist ein Fehler aufgetreten.|
|E_NOTIMPL|Gibt an MFC selbst sollten versuchen, übersetzt und den Befehl zu senden.|
|OLECMDERR_E_UNKNOWNGROUP|*PguidCmdGroup* ungleich NULL ist, aber gibt keine bekannte Befehlsgruppe an.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* wird nicht als gültiger Befehl in der Gruppe pGroup erkannt.|
|OLECMDERR_DISABLED|Der Befehl identifizierte *nCmdID* ist deaktiviert und kann nicht ausgeführt werden.|
|OLECMDERR_NOHELP|Aufrufer aufgefordert Hilfe zum Befehl "identifizierte" *nCmdID* , aber es ist keine Hilfe verfügbar.|
|OLECMDERR_CANCELLED|Die Ausführung wurde vom Benutzer abgebrochen.|

### <a name="remarks"></a>Hinweise

Die *PguidCmdGroup* und *nCmdID* Parameter zusammen den aufzurufende Befehl eindeutig zu identifizieren. Die *nCmdExecOpt* Parameter gibt an, die genaue auszuführende Aktion.

##  <a name="getactiveview"></a>  COleDocObjectItem::GetActiveView

Rufen Sie diese Memberfunktion, um einen Zeiger auf die `IOleDocumentView` Schnittstelle, die derzeit aktive Ansicht.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [IOleDocumentView](/windows/desktop/api/docobj/nn-docobj-ioledocumentview) Schnittstelle, die derzeit aktive Ansicht. Wenn keine aktuelle Ansicht vorhanden ist, wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Anzahl der Verweise auf das zurückgegebene `IOleDocumentView` Zeiger wird nicht inkrementiert, bevor sie von dieser Funktion zurückgegeben wird.

##  <a name="getpagecount"></a>  COleDocObjectItem::GetPageCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Seiten im Dokument.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Parameter

*pnFirstPage*<br/>
Ein Zeiger auf die Anzahl der ersten Seite des Dokuments ab. NULL kann sein; gibt an, dass der Aufrufer diese Zahl nicht benötigt.

*pcPages*<br/>
Ein Zeiger auf die Gesamtzahl der Seiten im Dokument. NULL kann sein; gibt an, dass der Aufrufer diese Zahl nicht benötigt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="onprepareprinting"></a>  COleDocObjectItem:: OnPreparePrinting

Diese Memberfunktion wird durch das Framework zur Vorbereitung der Drucken eines Dokuments aufgerufen.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parameter

*pCaller*<br/>
Ein Zeiger auf eine [CView](../../mfc/reference/cview-class.md) -Objekt, das den Druckbefehl gesendet werden.

*pInfo*<br/>
Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das beschreibt, den Auftrag gedruckt werden sollen.

*bPrintAll*<br/>
Gibt an, ob das gesamte Dokument gedruckt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="onprint"></a>  COleDocObjectItem

Diese Memberfunktion wird von dem Framework, ein Dokument gedruckt aufgerufen.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parameter

*pCaller*<br/>
Ein Zeiger auf ein CView-Objekt, das den Druckbefehl gesendet werden.

*pInfo*<br/>
Ein Zeiger auf eine [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das beschreibt, den Auftrag gedruckt werden sollen.

*bPrintAll*<br/>
Gibt an, ob das gesamte Dokument gedruckt werden.

##  <a name="querycommand"></a>  COleDocObjectItem::QueryCommand

Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Parameter

*nCmdID*<br/>
Der Bezeichner des Befehls, die abgefragt wird.

*pdwStatus*<br/>
Ein Zeiger auf die Flags, die als Ergebnis der Abfrage zurückgegeben wurden. Eine Liste der möglichen Werte, finden Sie unter [OLECMDF](/windows/desktop/api/docobj/ne-docobj-olecmdf).

*pCmdText*<br/>
Zeiger auf ein [OLECMDTEXT](/windows/desktop/api/docobj/ns-docobj-_tagolecmdtext) Struktur, in der Namen und-Status Informationen eines einzelnen Befehls zurückgegeben werden sollen. NULL kann sein, um anzugeben, dass der Aufrufer diese Informationen nicht benötigt.

*pguidCmdGroup*<br/>
Eindeutiger Bezeichner der Befehlsgruppe; möglich NULL, um die Standardgruppe anzugeben.

### <a name="return-value"></a>Rückgabewert

Eine vollständige Liste von Werten, finden Sie unter [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) im Windows SDK.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion emuliert die Funktionen des die [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) -Methode, wie im Windows SDK beschrieben.

##  <a name="release"></a>  COleDocObjectItem::Release

Die Verbindung mit einer OLE-Element verknüpfte frei, und geschlossen wird, wenn es geöffnet war. Die Client-Element wird nicht zerstört werden.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Parameter

*dwCloseOption*<br/>
Flag, das angibt, unter welchen Umständen das OLE-Element gespeichert wird, wenn in den geladenen Zustand zurückgegeben. Eine Liste der möglichen Werte, finden Sie unter [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Hinweise

Die Client-Element wird nicht zerstört werden.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)
