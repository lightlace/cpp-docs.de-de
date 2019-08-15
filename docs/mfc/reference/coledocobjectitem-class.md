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
ms.openlocfilehash: c6e00bf42cf20b46c949c218efe1820cc7ce0f9b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504010"
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
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Erstellt ein `COleDocObject` Element.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Druckt das Dokument der Containeranwendung mithilfe der Standarddrucker Einstellungen.|
|[COleDocObjectItem::ExecCommand](#execcommand)|Führt den vom Benutzer angegebenen Befehl aus.|
|[COleDocObjectItem::GetActiveView](#getactiveview)|Ruft die aktive Ansicht des Dokuments ab.|
|[COleDocObjectItem::GetPageCount](#getpagecount)|Ruft die Anzahl der Seiten im Dokument der Containeranwendung ab.|
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Bereitet das Dokument der Containeranwendung zum Drucken vor.|
|[COleDocObjectItem::OnPrint](#onprint)|Druckt das Dokument der Containeranwendung.|
|[COleDocObjectItem::QueryCommand](#querycommand)|Fragt den Status von Befehlen ab, die von Ereignissen auf der Benutzeroberfläche generiert wurden.|
|[COleDocObjectItem::Release](#release)|Gibt die Verbindung zu einem mit OLE verknüpften Element frei und schließt es, wenn es geöffnet war. Das Client Element wird nicht zerstört.|

## <a name="remarks"></a>Hinweise

In MFC wird ein aktives Dokument ähnlich wie eine reguläre, bearbeitbare bearbeitbare Einbettung mit den folgenden Unterschieden behandelt:

- Die `COleDocument`von abgeleitete Klasse behält immer noch eine Liste der aktuell eingebetteten Elemente bei. diese Elemente können jedoch `COleDocObjectItem`von abgeleitete Elemente sein.

- Wenn ein aktives Dokument aktiv ist, nimmt es den gesamten Client Bereich der Ansicht an, wenn es aktiv ist.

- Ein aktiver Dokument Container hat die vollständige Kontrolle über das Menü **Hilfe** .

- Das Menü **Hilfe** enthält Menü Elemente für den aktiven Dokument Container und den Server.

Da der aktive Dokument Container das Menü **Hilfe** besitzt, ist der Container für die Weiterleitung von Server **Hilfe** -Menü Meldungen an den Server zuständig. Diese Integration wird von `COleDocObjectItem`behandelt.

Weitere Informationen zum Zusammenführen von Menüs und zum Aktivieren von aktiven Dokumenten finden Sie unter Übersicht über die [aktive Dokument](../../mfc/active-document-containment.md)Kapselung.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Anforderungen

**Header:** Afxole. h

##  <a name="coledocobjectitem"></a>COleDocObjectItem:: COleDocObjectItem

Diese Member-Funktion zum Initialisieren des `COleDocObjectItem` -Objekts aufzurufen.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Parameter

*pContainerDoc*<br/>
Ein Zeiger auf das `COleDocument` Objekt, das als aktiver Dokument Container fungiert. Dieser Parameter muss NULL sein, um IMPLEMENT_SERIALIZE zu aktivieren. Normalerweise werden OLE-Elemente mit einem Dokument Zeiger ungleich NULL erstellt.

##  <a name="dodefaultprinting"></a>COleDocObjectItem::D odefaultprinting

Wird vom Framework in einem Dokument mithilfe der Standardeinstellungen aufgerufen.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Parameter

*pCaller*<br/>
Ein Zeiger auf ein [CView](../../mfc/reference/cview-class.md) -Objekt, das den Print-Befehl sendet.

*pInfo*<br/>
Ein Zeiger auf ein [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das den zu druckenden Auftrag beschreibt.

##  <a name="execcommand"></a>COleDocObjectItem:: execCommand

Mit dieser Member-Funktion können Sie den vom Benutzer angegebenen Befehl ausführen.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Parameter

*nCmdID*<br/>
Der Bezeichner des auszuführenden Befehls. Muss in der durch *pguidcmdgroup*identifizierten Gruppe sein.

*nCmdExecOpt*<br/>
Gibt Befehls Ausführungs Optionen an. Standardmäßig legen Sie fest, um den Befehl auszuführen, ohne den Benutzer aufzufordern. Eine Liste der Werte finden Sie unter [olecmdexecopt](/windows/win32/api/docobj/ne-docobj-olecmdexecopt) .

*pguidCmdGroup*<br/>
Eindeutiger Bezeichner der Befehlsgruppe. Standardmäßig ist der Wert NULL, der die Standardgruppe angibt. Der in *nCmdId* über gegebene Befehl muss zur Gruppe gehören.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn erfolgreich; Andernfalls wird einer der folgenden Fehlercodes zurückgegeben.

|Wert|Beschreibung|
|-----------|-----------------|
|E_UNEXPECTED|Unerwarteter Fehler.|
|E_FAIL|Fehler aufgetreten.|
|E_NOTIMPL|Gibt an, dass MFC selbst versuchen soll, den Befehl zu übersetzen und zu verteilen.|
|OLECMDERR_E_UNKNOWNGROUP|*pguidcmdgroup* ist nicht NULL, gibt jedoch keine erkannte Befehlsgruppe an.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdId* wird nicht als gültiger Befehl in der Gruppe "pgroup" erkannt.|
|OLECMDERR_DISABLED|Der von *nCmdId* identifizierte Befehl ist deaktiviert und kann nicht ausgeführt werden.|
|OLECMDERR_NOHELP|Der Aufrufer hat Hilfe zu dem Befehl angefordert, der von *nCmdId identifiziert wurde* , aber es ist keine Hilfe verfügbar|
|OLECMDERR_CANCELLED|Der Benutzer hat die Ausführung abgebrochen.|

### <a name="remarks"></a>Hinweise

Mit den Parametern *pguidcmdgroup* und *nCmdId* wird der aufzurufende Befehl eindeutig identifiziert. Der *nCmdexecopt* -Parameter gibt die genaue Aktion an, die ausgeführt werden soll.

##  <a name="getactiveview"></a>COleDocObjectItem:: GetActiveView

Mit dieser Member-Funktion können Sie einen Zeiger auf `IOleDocumentView` die-Schnittstelle der derzeit aktiven Ansicht abrufen.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [IOleDocumentView](/windows/win32/api/docobj/nn-docobj-ioledocumentview) -Schnittstelle der derzeit aktiven Ansicht. Wenn keine aktuelle Ansicht vorhanden ist, wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Der Verweis Zähler für den zurück `IOleDocumentView` gegebenen Zeiger wird nicht inkrementiert, bevor er von dieser Funktion zurückgegeben wird.

##  <a name="getpagecount"></a>COleDocObjectItem:: getPageCount

Rufen Sie diese Member-Funktion auf, um die Anzahl der Seiten im Dokument abzurufen.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Parameter

*pnFirstPage*<br/>
Ein Zeiger auf die Nummer der ersten Seite des Dokuments. Kann NULL sein, was bedeutet, dass der Aufrufer diese Zahl nicht benötigt.

*pcpages*<br/>
Ein Zeiger auf die Gesamtzahl der Seiten im Dokument. Kann NULL sein, was bedeutet, dass der Aufrufer diese Zahl nicht benötigt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="onprepareprinting"></a>COleDocObjectItem:: OnPreparePrinting

Diese Member-Funktion wird vom Framework aufgerufen, um ein Dokument für das Drucken vorzubereiten.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parameter

*pCaller*<br/>
Ein Zeiger auf ein [CView](../../mfc/reference/cview-class.md) -Objekt, das den Print-Befehl sendet.

*pInfo*<br/>
Ein Zeiger auf ein [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das den zu druckenden Auftrag beschreibt.

*bPrintAll*<br/>
Gibt an, ob das gesamte Dokument gedruckt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="onprint"></a>COleDocObjectItem:: OnPrint

Diese Member-Funktion wird vom Framework aufgerufen, um ein Dokument zu drucken.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Parameter

*pCaller*<br/>
Ein Zeiger auf ein CView-Objekt, das den Print-Befehl sendet.

*pInfo*<br/>
Ein Zeiger auf ein [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) -Objekt, das den zu druckenden Auftrag beschreibt.

*bPrintAll*<br/>
Gibt an, ob das gesamte Dokument gedruckt werden soll.

##  <a name="querycommand"></a>COleDocObjectItem:: querycommand

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
der Bezeichner des Befehls, der abgefragt wird.

*pdwStatus*<br/>
Ein Zeiger auf die Flags, die als Ergebnis der Abfrage zurückgegeben werden. Eine Liste möglicher Werte finden Sie unter [OLECMDF](/windows/win32/api/docobj/ne-docobj-olecmdf).

*pCmdText*<br/>
Ein Zeiger auf eine [olecmdtext](/windows/win32/api/docobj/ns-docobj-olecmdtext) -Struktur, in der die Namen-und Statusinformationen für einen einzelnen Befehl zurückgegeben werden sollen. Kann NULL sein, um anzugeben, dass der Aufrufer diese Informationen nicht benötigt.

*pguidCmdGroup*<br/>
Eindeutiger Bezeichner der Befehlsgruppe; kann NULL sein, um die Standardgruppe anzugeben.

### <a name="return-value"></a>Rückgabewert

Eine umfassende Liste der Rückgabewerte finden Sie unter [IOleCommandTarget:: QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) in der Windows SDK.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion emuliert die Funktionalität der [IOleCommandTarget:: QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) -Methode, wie im Windows SDK beschrieben.

##  <a name="release"></a>COleDocObjectItem:: Release

Gibt die Verbindung zu einem mit OLE verknüpften Element frei und schließt es, wenn es geöffnet war. Das Client Element wird nicht zerstört.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Parameter

*dwCloseOption*<br/>
Flag, das angibt, unter welchen Umständen das OLE-Element beim zurückkehren in den geladenen Zustand gespeichert wird. Eine Liste möglicher Werte finden Sie unter [COleClientItem:: Close](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Hinweise

Das Client Element wird nicht zerstört.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)
