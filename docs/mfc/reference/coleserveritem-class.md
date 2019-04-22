---
title: COleServerItem-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
ms.openlocfilehash: c4c026975e9884ac2a0e6aaef31e799c2b5b09bf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777375"
---
# <a name="coleserveritem-class"></a>COleServerItem-Klasse

Stellt die Serverschnittstelle zu OLE-Elementen bereit.

## <a name="syntax"></a>Syntax

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleServerItem::COleServerItem](#coleserveritem)|Erstellt ein `COleServerItem`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Platziert die Präsentation und Konvertierung von Formaten in ein `COleDataSource` Objekt.|
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Kopiert das Element in die Zwischenablage.|
|[COleServerItem::DoDragDrop](#dodragdrop)|Führt einen Drag & Drop-Vorgang.|
|[COleServerItem::GetClipboardData](#getclipboarddata)|Ruft die Datenquelle für die Verwendung bei der Datenübertragung (Drag & Drop oder Zwischenablage) ab.|
|[COleServerItem::GetDocument](#getdocument)|Gibt zurück, das Serverdokument, das das Element enthält.|
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Ruft die CF_EMBEDSOURCE Daten für ein OLE-Element ab.|
|[COleServerItem::GetItemName](#getitemname)|Gibt den Namen des Elements zurück. Für verknüpfte Elemente nur verwendet werden.|
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Ruft die CF_LINKSOURCE Daten für ein OLE-Element ab.|
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Ruft die CF_OBJECTDESCRIPTOR Daten für ein OLE-Element ab.|
|[COleServerItem::IsConnected](#isconnected)|Gibt an, ob das Element derzeit einen aktiven Container angefügt ist.|
|[COleServerItem::IsLinkedItem](#islinkeditem)|Gibt an, ob das Element ein verknüpftes OLE-Element darstellt.|
|[COleServerItem::NotifyChanged](#notifychanged)|Aktualisiert alle Container mit automatische Verknüpfung Update an.|
|[COleServerItem::OnDoVerb](#ondoverb)|Wird aufgerufen, um ein Verb auszuführen.|
|[COleServerItem::OnDraw](#ondraw)|Aufgerufen, wenn der Container-zum Zeichnen des Elements Anforderungen. die Implementierung erforderlich sind.|
|[COleServerItem::OnDrawEx](#ondrawex)|Wird aufgerufen, für das spezielle Element zeichnen.|
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Wird aufgerufen, durch das Framework zum Abrufen der Daten, die in die Zwischenablage kopiert werden sollen.|
|[COleServerItem::OnGetExtent](#ongetextent)|Wird aufgerufen, durch das Framework, um die Größe des OLE-Elements abzurufen.|
|[COleServerItem::OnInitFromData](#oninitfromdata)|Wird aufgerufen, durch das Framework um ein OLE-Element, das mit dem Inhalt des angegebenen Objekts Übertragung zu initialisieren.|
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Wird aufgerufen, um festzustellen, ob alle verknüpften Elemente aktualisiert werden müssen.|
|[COleServerItem::OnRenderData](#onrenderdata)|Ruft die Daten im Rahmen der verzögerte Rendering ab.|
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Abrufen von Daten in einem `CFile` Objekt als Bestandteil von verzögertem Rendering.|
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Ruft die Daten in HGLOBAL als Teil des verzögerte Rendering ab.|
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Wird aufgerufen, um das Farbschema des Elements festgelegt.|
|[COleServerItem::OnSetData](#onsetdata)|Wird aufgerufen, um die Daten des festzulegen.|
|[COleServerItem::OnSetExtent](#onsetextent)|Wird aufgerufen, durch das Framework die Größe des OLE-Elements festgelegt.|
|[COleServerItem::OnUpdate](#onupdate)|Wird aufgerufen, wird Wenn ein Teil des Dokuments das Element gehört geändert.|
|[COleServerItem::OnUpdateItems](#onupdateitems)|Wird aufgerufen, um den Cache Darstellung aller Elemente im Serverdokument zu aktualisieren.|
|[COleServerItem::SetItemName](#setitemname)|Legt den Namen des Elements. Für verknüpfte Elemente nur verwendet werden.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleServerItem::GetDataSource](#getdatasource)|Ruft das Objekt, das zum Speichern von konvertierungsformate verwendet.|
|[COleServerItem::OnHide](#onhide)|Wird aufgerufen, durch das Framework das OLE-Element ausgeblendet wird.|
|[COleServerItem::OnOpen](#onopen)|Wird aufgerufen, durch das Framework das OLE-Element in einem eigenen Fenster der obersten Ebene angezeigt.|
|[COleServerItem::OnShow](#onshow)|Wird aufgerufen, wenn der Container anfordert, um das Element anzuzeigen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Informiert Sie den Server, über wie viel von der OLE-Element sichtbar ist.|

## <a name="remarks"></a>Hinweise

Ein verknüpftes Element kann es sich um einige oder alle der Serverdokument darstellen. Ein eingebettetes Element stellt immer einen ganzen Server-Dokument dar.

Die `COleServerItem` Klasse definiert mehrere überschreibbare Memberfunktionen, die von der OLE-System Dynamic Link Libraries (DLLs), aufgerufen werden, in der Regel als Antwort auf Anforderungen von der Container-Anwendung. Diese Memberfunktionen können die Container-Anwendung zum Bearbeiten von Elements indirekt auf verschiedene Weise, wie z. B. durch Anzeige, die Verben ausführen oder Abrufen von Daten in verschiedenen Formaten.

Verwendung von `COleServerItem`, eine Klasse ableiten und Implementieren der [OnDraw](#ondraw) und [Serialize](../../mfc/reference/cobject-class.md#serialize) Memberfunktionen. Die `OnDraw` -Funktion bietet die Metadateidarstellung des ein Element, sodass er angezeigt wird, wenn eine Container-Anwendung mit einem Verbunddokument geöffnet wird. Die `Serialize` Funktion `CObject` bietet die native Darstellung eines Elements, sodass ein eingebettetes Element zwischen Server und-Container Anwendungen übertragen werden. [OnGetExtent](#ongetextent) Größe des Elements, das den Container, aktivieren den Container, die Größe des Elements enthält.

Weitere Informationen zu Server und verwandten Themen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md) und "Erstellen einer Container/Server-Dienstanwendung" in diesem Artikel [Container: Erweiterte Features](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="addotherclipboarddata"></a>  COleServerItem::AddOtherClipboardData

Mit dieser Funktion können Sie die Präsentation und Konvertierung Formate für das OLE-Element in der angegebenen platzieren `COleDataSource` Objekt.

```
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Parameter

*pDataSource*<br/>
Zeiger auf die `COleDataSource` -Objekt in der die Daten eingefügt werden soll.

### <a name="remarks"></a>Hinweise

Sie implementiert haben müssen die [OnDraw](#ondraw) Memberfunktion versucht, das Presentation-Format (ein Metadateibild) für das Element bereitzustellen. Um andere konvertierungsformate zu unterstützen, registrieren sie mit der [COleDataSource](../../mfc/reference/coledatasource-class.md) zurückgegebenes Objekt [GetDataSource](#getdatasource) und überschreiben die [OnRenderData](#onrenderdata) Memberfunktion Geben Sie die Daten in den Formaten, die Sie unterstützen möchten.

##  <a name="coleserveritem"></a>  COleServerItem::COleServerItem

Erstellt eine `COleServerItem` -Objekt und fügt es der Serverdokument Auflistung der Dokumentelemente hinzu.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Parameter

*pServerDoc*<br/>
Zeiger auf das Dokument, das das neue Element enthalten soll.

*bAutoDelete*<br/>
Flag, der angibt, ob das Objekt gelöscht werden kann, wenn ein Link zu ihr freigegeben wird. Legen Sie diese Einstellung auf "false" fest, wenn die `COleServerItem` Objekt ist ein wesentlicher Bestandteil des Dokuments-Daten, die Sie löschen müssen. Legen Sie diese Einstellung auf "true" fest, wenn das Objekt ist eine sekundäre Struktur verwendet, um einen Bereich in die Daten des Dokuments zu identifizieren, die vom Framework gelöscht werden kann.

##  <a name="copytoclipboard"></a>  COleServerItem::CopyToClipboard

Rufen Sie diese Funktion, um das OLE-Element in die Zwischenablage zu kopieren.

```
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Parameter

*bIncludeLink*<br/>
Legen Sie diese Einstellung auf "true" Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie diese Einstellung auf "false" fest, wenn Ihr Server Links der Anwendung nicht unterstützt.

### <a name="remarks"></a>Hinweise

Verwendet die Funktion der [OnGetClipboardData](#ongetclipboarddata) Member-Funktion zum Erstellen einer [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt mit der OLE-Element-Daten in den Formaten unterstützt. Die Funktion platziert dann das `COleDataSource` Objekt in der Zwischenablage mit der [COleDataSource](../../mfc/reference/coledatasource-class.md#setclipboard) Funktion. Die `COleDataSource` Objekt enthält die systemeigenen Daten des Elements und dessen Darstellung CF_METAFILEPICT Format sowie Daten in jeder konvertierungsformate, die Sie unterstützen möchten. Sie implementiert haben müssen [Serialize](../../mfc/reference/cobject-class.md#serialize) und [OnDraw](#ondraw) für diese Memberfunktion funktioniert.

##  <a name="dodragdrop"></a>  COleServerItem:: DoDragDrop

Rufen Sie die `DoDragDrop` Memberfunktion versucht, einen Drag & Drop-Vorgang auszuführen.

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>Parameter

*lpRectItem*<br/>
Rechteck des Elements, auf dem Bildschirm in Pixel relativ zum Clientbereich.

*ptOffset*<br/>
Der Offset vom *LpItemRect* , bei denen die Position des Mauszeigers war zum Zeitpunkt des Ziehvorgangs.

*bIncludeLink*<br/>
Legen Sie diese Einstellung auf "true" Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie sie auf "false", wenn Ihre Anwendung Links nicht unterstützt.

*dwEffects*<br/>
Bestimmt, die Auswirkungen, die die Quelle des Ziehvorgangs in den Ziehvorgang entsteht (eine Kombination aus kopieren, verschieben und Link) ermöglichen.

*lpRectStartDrag*<br/>
Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang tatsächlich gestartet. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".

### <a name="return-value"></a>Rückgabewert

Ein Wert aus der-DropEffect-Enumeration. Wenn es sich um DROPEFFECT_MOVE handelt, sollte die ursprünglichen Daten entfernt werden.

### <a name="remarks"></a>Hinweise

Der Drag & Drop-Vorgang wird nicht sofort gestartet. Er wartet, bis der Mauszeiger das durch angegebene Rechteck verlässt *LpRectStartDrag* oder eine angegebene Anzahl von Millisekunden verstrichen sind. Wenn *LpRectStartDrag* NULL ist, ein Standardrechteck wird verwendet, sodass für der Ziehvorgang beginnt, wenn der Mauszeiger bewegt, ein Pixel wird.

Die Verzögerungszeit wird durch eine registrierungsschlüsseleinstellung angegeben. Sie können die Verzögerungszeit ändern, durch den Aufruf [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie die Verzögerung nicht angeben, wird ein Standardwert 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit wird wie folgt gespeichert:

- Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.

- Windows 3.x Drag-Verzögerungszeit wird in der Windows-Taste gespeichert. INI-Datei unter dem [Windows}-Abschnitt.

- Ziehen Sie die Windows 95-und Windows 98-Verzögerungszeit wird in eine zwischengespeicherte Version des Windows-Taste gespeichert. INI.

Für Weitere Informationen ziehen wird der Informationen in der Registrierung gespeichert oder. INI-Datei finden Sie unter [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) im Windows SDK.

##  <a name="getclipboarddata"></a>  COleServerItem::GetClipboardData

Mit dieser Funktion können Sie den angegebenen füllen [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt mit allen Daten, die in die Zwischenablage kopiert werden sollen, wenn Sie aufgerufen [CopyToClipboard](#copytoclipboard) (die gleichen Daten würden auch übertragen werden, wenn Sie wird aufgerufen, [DoDragDrop](#dodragdrop)).

```
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Parameter

*pDataSource*<br/>
Zeiger auf die `COleDataSource` -Objekt, das das OLE-Element-Daten in allen unterstützten Formaten empfangen wird.

*bIncludeLink*<br/>
TRUE, wenn das Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. "False", wenn die Serveranwendung Links nicht unterstützt.

*lpOffset*<br/>
Der Offset, der den Cursor auf den Ursprung des Objekts in Pixel.

*lpSize*<br/>
Die Größe des Objekts in Pixel.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft die [GetEmbedSourceData](#getembedsourcedata) Member-Funktion zum Abrufen der systemeigenen Daten für die OLE-Element und ruft die [AddOtherClipboardData](#addotherclipboarddata) abzurufenden Präsentationsformat und alle Member-Funktion konvertierungsformate wird unterstützt. Wenn *bIncludeLink* ist "true", die Funktion auch Aufrufe [GetLinkSourceData](#getlinksourcedata) um die Daten des Quelllinks für das Element zu erhalten.

Diese Funktion zu überschreiben, wenn Sie möchte Formate eine `COleDataSource` Objekt vor oder nach diesen Formaten, die vom `CopyToClipboard`.

##  <a name="getdatasource"></a>  COleServerItem::GetDataSource

Mit dieser Funktion wird zum Abrufen der [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt verwendet, um die konvertierungsformate zu speichern, die die Server-Anwendung unterstützt.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `COleDataSource` Objekt verwendet, um die konvertierungsformate zu speichern.

### <a name="remarks"></a>Hinweise

Wenn Sie die Server-Anwendung Daten in einer Vielzahl von Formaten während der Datenübertragung Vorgänge bieten möchten, registrieren Sie diesen Formaten mit der `COleDataSource` Objekt, das von dieser Funktion zurückgegeben. Z. B. Wenn Sie eine HIERSVR-Darstellung des OLE-Elements für die Zwischenablage oder Drag & Drop-Vorgänge angeben möchten, Sie würden Registrieren des Formats mit der `COleDataSource` Objekt, die diese Funktion gibt zurück, und überschreiben die `OnRenderXxxData` Memberfunktion Geben Sie die Daten an.

##  <a name="getdocument"></a>  COleServerItem::GetDocument

Rufen Sie diese Funktion, um einen Zeiger auf das Dokument zu erhalten, die das Element enthält.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Dokument, das das Element enthält; NULL, wenn das Element nicht Teil eines Dokuments ist.

### <a name="remarks"></a>Hinweise

Dies ermöglicht den Zugriff auf das Serverdokument, das Sie als Argument übergeben die `COleServerItem` Konstruktor.

##  <a name="getembedsourcedata"></a>  COleServerItem::GetEmbedSourceData

Rufen Sie diese Funktion zum Abrufen der CF_EMBEDSOURCE-Daten für ein OLE-Element.

```
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parameter

*lpStgMedium*<br/>
Zeiger auf die [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) -Struktur, die die CF_EMBEDSOURCE-Daten für das OLE-Element erhält.

### <a name="remarks"></a>Hinweise

Dieses Format schließt die systemeigenen Daten des Elements. Sie implementiert haben müssen die `Serialize` Member-Funktion für diese Funktion ordnungsgemäß funktioniert.

Das Ergebnis kann anschließend an eine Datenquelle hinzugefügt werden, mithilfe von [CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Diese Funktion aufgerufen wird, automatisch vom [COleServerItem::OnGetClipboardData](#ongetclipboarddata).

Weitere Informationen finden Sie unter [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) im Windows SDK.

##  <a name="getitemname"></a>  COleServerItem::GetItemName

Rufen Sie diese Funktion zum Abrufen des Namens des Elements.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Rückgabewert

Name des Elements.

### <a name="remarks"></a>Hinweise

In der Regel rufen Sie diese Funktion nur für verknüpfte Elemente.

##  <a name="getlinksourcedata"></a>  COleServerItem::GetLinkSourceData

Rufen Sie diese Funktion zum Abrufen der CF_LINKSOURCE-Daten für ein OLE-Element.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parameter

*lpStgMedium*<br/>
Zeiger auf die [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) -Struktur, die die CF_LINKSOURCE-Daten für das OLE-Element erhält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Dieses Format schließt die CLSID, der den Typ des OLE-Elements und die erforderlichen Informationen zum Suchen Sie des Dokuments mit dem OLE-Element beschreibt.

Das Ergebnis kann anschließend hinzugefügt werden, um eine Datenquelle mit [CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Diese Funktion aufgerufen wird, automatisch vom [OnGetClipboardData](#ongetclipboarddata).

Weitere Informationen finden Sie unter [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) im Windows SDK.

##  <a name="getobjectdescriptordata"></a>  COleServerItem::GetObjectDescriptorData

Rufen Sie diese Funktion zum Abrufen der CF_OBJECTDESCRIPTOR-Daten für ein OLE-Element.

```
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parameter

*lpOffset*<br/>
Offset des Mausklicks klicken Sie auf der linken oberen Ecke des OLE-Elements. NULL kann sein.

*lpSize*<br/>
Die Größe des OLE-Elements. NULL kann sein.

*lpStgMedium*<br/>
Zeiger auf die [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) -Struktur, die die CF_OBJECTDESCRIPTOR-Daten für das OLE-Element erhält.

### <a name="remarks"></a>Hinweise

Kopiert die Informationen in den `STGMEDIUM` Struktur verweist *LpStgMedium*. Dieses Format schließt die Informationen, die für das Dialogfeld "Inhalte einfügen" erforderlich sind.

Weitere Informationen finden Sie unter [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) im Windows SDK.

##  <a name="isconnected"></a>  COleServerItem::IsConnected

Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element verbunden ist.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Element besteht; andernfalls 0.

### <a name="remarks"></a>Hinweise

Verbunden werden, wenn ein oder mehrere Container Verweise auf das Element ist ein OLE-Element gilt. Ein Element verbunden ist, wenn dessen Verweiszähler größer als 0 ist, oder wenn es sich um ein eingebettetes Element ist.

##  <a name="islinkeditem"></a>  COleServerItem::IsLinkedItem

Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element ein verknüpftes Element ist.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Element ein verknüpftes Element ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein Element verknüpft ist, wenn das Element gültig ist und nicht in das Dokument der Liste der eingebetteten Elemente zurückgegeben. Ein verknüpftes Element möglicherweise oder ist nicht in einem Container verbunden.

Es ist üblich, die für verknüpfte und eingebettete Elemente derselben Klasse zu verwenden. `IsLinkedItem` können Sie verknüpfte Elemente, die Verhalten sich anders als eingebettete Elemente stellen zwar oft der Code gemeinsam ist.

##  <a name="m_sizeextent"></a>  COleServerItem::m_sizeExtent

Dieses Element weist den Server, wie viel des Objekts im Containerdokument sichtbar ist.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung des [OnSetExtent](#onsetextent) dieses Element legt sie fest.

##  <a name="notifychanged"></a>  COleServerItem::NotifyChanged

Rufen Sie diese Funktion, nachdem das verknüpfte Element geändert wurde.

```
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Parameter

*nDrawAspect*<br/>
Ein Wert aus der DVASPECT-Enumeration, die angibt, welcher Aspekt des OLE-Elements geändert wurde. Dieser Parameter kann einen der folgenden Werte aufweisen:

- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.

- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.

- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.

- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.

### <a name="remarks"></a>Hinweise

Wenn ein Containerelement mit eine automatische Verknüpfung zum Dokument verknüpft ist, wird das Element aktualisiert, um die Änderungen widerzuspiegeln. In Anwendungen mit Containern unter Verwendung der Microsoft Foundation Class-Bibliothek geschrieben [COleClientItem:: OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Reaktion aufgerufen wird.

##  <a name="ondoverb"></a>  COleServerItem::OnDoVerb

Vom Framework aufgerufen, die das angegebene Verb aufzurufen.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Gibt das Verb ausgeführt. Sie können eine der folgenden sein:

|Wert|Bedeutung|Symbol|
|-----------|-------------|------------|
|0|Primäres Verb|OLEIVERB_PRIMARY|
|1|Sekundäre verb|(Keine)|
|- 1|Display-Element für die Bearbeitung|OLEIVERB_SHOW|
|- 2|Element in separaten Fenster bearbeiten|OLEIVERB_OPEN|
|- 3|Element ausblenden|OLEIVERB_HIDE|

Der Wert-1 wird in der Regel einen Alias für ein anderes Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat-2 dieselbe Wirkung wie das-1 auf. Weitere Werte finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) im Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) -Memberfunktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die Standardimplementierung Ruft die [OnShow](#onshow) Member-Funktion, wenn der primäre Verb oder OLEIVERB_SHOW angegeben wird, [OnOpen](#onopen) , wenn der sekundäre Verb oder OLEIVERB_OPEN angegeben ist, und [OnHide ](#onhide) OLEIVERB_HIDE angegeben ist. Die Standardimplementierung ruft `OnShow` Wenn *iVerb* ist keiner der oben aufgeführten Verben.

Überschreiben Sie diese Funktion, wenn das Element nicht in Ihr primäre Verb angezeigt wird. Z. B. wenn das Element einer Tonaufnahme und seine primäre Verb Play ist, müssten nicht Sie die Serveranwendung die Wiedergabe des Elements angezeigt.

Weitere Informationen finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) im Windows SDK.

##  <a name="ondraw"></a>  COleServerItem:: OnDraw

Wird aufgerufen, durch das Framework das OLE-Element in einer Metadatei zu rendern.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, für das zum Zeichnen des Elements. Der Anzeigekontext wird automatisch dann für den Anzeigekontext Attribut verbunden, daher können Sie die Attribut-Funktionen aufrufen, obwohl dies also die Metadatei gerätespezifischen machen würden.

*rSize*<br/>
Größe in HIMETRIC-Einheiten, in dem die Metadatei gezeichnet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Element wurde erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Metadateidarstellung des OLE-Elements wird verwendet, um das Element in der containeranwendung anzuzeigen. Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird von die Metadatei verwendet die [zeichnen](../../mfc/reference/coleclientitem-class.md#draw) -Memberfunktion des entsprechenden [COleClientItem](../../mfc/reference/coleclientitem-class.md) Objekt. Es ist keine Standardimplementierung vorhanden. Sie müssen diese Funktion zum Zeichnen des Elements in den angegebenen Gerätekontext überschreiben.

##  <a name="ondrawex"></a>  COleServerItem::OnDrawEx

Wird aufgerufen, durch das Framework für alle zeichnen.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, für das zum Zeichnen des Elements. Der DC ist automatisch verbunden, das DC-Attribut daher können Sie die Attribut-Funktionen aufrufen, obwohl dies also die Metadatei gerätespezifischen machen würden.

*nDrawAspect*<br/>
Ein Wert aus der DVASPECT-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:

- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.

- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.

- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.

- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.

*rSize*<br/>
Die Größe des Elements im HIMETRIC-Einheiten.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Element wurde erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ruft `OnDraw` Wenn DVASPECT DVASPECT_CONTENT entspricht; andernfalls ein Fehler auftritt.

Überschreiben Sie diese Funktion, um Aspekte als DVASPECT_CONTENT, z. B. DVASPECT_ICON oder DVASPECT_THUMBNAIL Präsentationsdaten bereit.

##  <a name="ongetclipboarddata"></a>  COleServerItem::OnGetClipboardData

Wird aufgerufen, durch das Framework zum Abrufen einer `COleDataSource` -Objekt, enthält alle Daten, die durch einen Aufruf in der Zwischenablage abgelegt werden die [CopyToClipboard](#copytoclipboard) Member-Funktion.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Parameter

*bIncludeLink*<br/>
Legen Sie diese Einstellung auf "true" Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie diese Einstellung auf "false" fest, wenn Ihr Server Links der Anwendung nicht unterstützt.

*lpOffset*<br/>
Der Offset des Mauszeigers über den Ursprung des Objekts in Pixel.

*lpSize*<br/>
Die Größe des Objekts in Pixel.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) -Objekt, das Daten in der Zwischenablage enthält.

### <a name="remarks"></a>Hinweise

Ruft die standardmäßige Implementierung dieser Funktion [GetClipboardData](#getclipboarddata).

##  <a name="ongetextent"></a>  COleServerItem::OnGetExtent

Wird aufgerufen, durch das Framework, um die Größe in HIMETRIC-Einheiten, des OLE-Elements abzurufen.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Parameter

*nDrawAspect*<br/>
Gibt den Aspekt des OLE-Elements, dessen Grenzen sind, abgerufen werden sollen. Dieser Parameter kann einen der folgenden Werte aufweisen:

- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.

- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.

- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.

- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.

*rSize*<br/>
Ein Verweis auf eine `CSize` -Objekt, das die Größe des OLE-Elements erhalten.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) -Memberfunktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen es selbst implementieren. Überschreiben Sie diese Funktion, wenn spezielle Verarbeitung ausführen, wenn eine Anforderung für die Größe des OLE-Elements verarbeitet werden sollen.

##  <a name="onhide"></a>  COleServerItem::OnHide

Wird aufgerufen, durch das Framework das OLE-Element ausgeblendet wird.

```
virtual void OnHide();
```

### <a name="remarks"></a>Hinweise

Die Standard-Aufrufe `COleServerDoc::OnShowDocument( FALSE )`. Die Funktion benachrichtigt zudem den Container, dass das OLE-Element ausgeblendet wurde. Überschreiben Sie diese Funktion, wenn spezielle Verarbeitung ausführen, wenn ein OLE-Element ausgeblendet werden sollen.

##  <a name="oninitfromdata"></a>  COleServerItem::OnInitFromData

Wird aufgerufen, durch das Framework zum Initialisieren von einem OLE-Element, das mit dem Inhalt des *pDataObject*.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Parameter

*pDataObject*<br/>
Zeiger auf ein OLE-Objekt, Daten, die Daten in verschiedenen Formaten, die zum Initialisieren der OLE-Element enthält.

*bCreation*<br/>
TRUE, wenn die Funktion aufgerufen wird, um ein OLE-Element neu erstellt wird, von einer containeranwendung zu initialisieren. FALSE, wenn die Funktion aufgerufen wird, um den Inhalt eines bereits vorhandenen OLE-Elements ersetzen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Wenn *bCreation* ist "true", diese Funktion wird aufgerufen, wenn ein Container neues Objekt einfügen basierend auf der aktuellen Auswahl implementiert. Die ausgewählten Daten werden verwendet, beim Erstellen des neuen OLE-Elements. Z. B. Wenn Sie einen Bereich von Zellen in einem Tabellenkalkulationsprogramm auswählen und dann das neue Objekt einfügen zum Erstellen eines Diagramms der Werte im ausgewählten Bereich anhand. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben von dieser Funktion können Sie wählen ein akzeptables Format von den *pDataObject* und initialisieren Sie das OLE-Element, das auf Basis der Daten bereitgestellt. Dies ist ein fortschrittlicher überschreibbar.

Weitere Informationen finden Sie unter [InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) im Windows SDK.

##  <a name="onopen"></a>  COleServerItem::OnOpen

Wird aufgerufen, durch das Framework, um das OLE-Element in einer separaten Instanz der Server-Anwendung und nicht an Ort anzuzeigen.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Hinweise

Die Standardimplementierung aktiviert den ersten Frame Fenster das Dokument, das OLE-Element enthält. Wenn die Anwendung eines Mini-Servers ist, zeigt die standardmäßige Implementierung das Hauptfenster. Die Funktion benachrichtigt zudem dem Container, dass das OLE-Element geöffnet wurde.

Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung ausführen, wenn Sie ein OLE-Element öffnen möchten. Dies ist besonders häufig mit verknüpften Elementen, in dem Sie die Auswahl auf den Link festgelegt wird, beim öffnen möchten.

Weitere Informationen finden Sie unter [IOleClientSite::OnShowWindow](/windows/desktop/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) im Windows SDK.

##  <a name="onqueryupdateitems"></a>  COleServerItem::OnQueryUpdateItems

Wird aufgerufen, durch das Framework, um festzustellen, ob alle verknüpften Elemente im aktuellen Serverdokument veraltet sind.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Dokument über Elemente, die Updates erfordern verfügt; 0, wenn alle Elemente auf dem neuesten Stand sind.

### <a name="remarks"></a>Hinweise

Ein Element ist veraltet, wenn die Quell-Dokument geändert wurde, aber das verknüpfte Element nicht aktualisiert wurde, wurde damit die Änderungen im Dokument.

##  <a name="onrenderdata"></a>  COleServerItem::OnRenderData

Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Parameter

*lpFormatEtc*<br/>
Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format, in dem Informationen angefordert, angibt.

*lpStgMedium*<br/>
Verweist auf eine [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur, in dem die Daten zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das angegebene Format ist eines der zuvor in platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) oder [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) Member-Funktion für das verzögerte Rendering. Ruft die standardmäßige Implementierung dieser Funktion [OnRenderFileData](#onrenderfiledata) oder [OnRenderGlobalData](#onrenderglobaldata), wenn das angegebene Speichermedium eine Datei oder einen Speicher ist. Wenn keines der folgenden Formate angegeben wird, wird die Standardimplementierung gibt 0 zurück und führt keine Aktion aus.

Wenn *LpStgMedium*-> *Tymed* TYMED_NULL, ist der STGMEDIUM sollten zugeordnet und ausgefüllt, die laut *LpFormatEtc -> Tymed*. Wenn dies nicht der TYMED_NULL, der STGMEDIUM mit Daten gefüllt werden.

Dies ist ein fortschrittlicher überschreibbar. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihren Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Ihre Daten kleine und fester Größe ist, überschreiben `OnRenderGlobalData`. Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben `OnRenderFileData`.

Weitere Informationen finden Sie unter [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc), und [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) im Windows SDK.

##  <a name="onrenderfiledata"></a>  COleServerItem::OnRenderFileData

Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das Speichermedium eine Datei ist.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Parameter

*lpFormatEtc*<br/>
Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format, in dem Informationen angefordert, angibt.

*pFile*<br/>
Verweist auf eine `CFile` Objekt, in dem die Daten gerendert werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das angegebene Format ist eines der zuvor in platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die Standardimplementierung dieser Funktion gibt einfach "false" zurück.

Dies ist ein fortschrittlicher überschreibbar. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihren Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata).

Weitere Informationen finden Sie unter [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.

##  <a name="onrenderglobaldata"></a>  COleServerItem::OnRenderGlobalData

Wird aufgerufen, durch das Framework zum Abrufen von Daten im angegebenen Format, wenn das angegebene Speichermedium globaler Speicher ist.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Parameter

*lpFormatEtc*<br/>
Verweist auf die [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format, in dem Informationen angefordert, angibt.

*phGlobal*<br/>
Verweist auf ein Handle für den globalen Arbeitsspeicher, die in der die Daten sind, zurückgegeben werden. Wenn kein Arbeitsspeicher zugewiesen wurde, kann dieser Parameter NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das angegebene Format ist eines der zuvor in platziert die `COleDataSource` -Objekt unter Verwendung der [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) Member-Funktion für das verzögerte Rendering. Die Standardimplementierung dieser Funktion gibt einfach "false" zurück.

Wenn *PhGlobal* NULL ist, und klicken Sie dann eine neue HGLOBAL zugeordnet und in zurückgegeben werden soll *PhGlobal*. Andernfalls anhand der HGLOBAL *PhGlobal* mit Daten gefüllt werden soll. Die Menge der Daten, die in der HGLOBAL platziert darf die aktuelle Größe des Speicherblocks nicht überschreiten. Darüber hinaus kann nicht der Block auf einen größeren verschoben werden.

Dies ist ein fortschrittlicher überschreibbar. Überschreiben Sie diese Funktion, um Ihre Daten in das angeforderte Format und das Medium angeben. Abhängig von Ihren Daten empfiehlt es sich um eine der anderen Versionen dieser Funktion stattdessen zu überschreiben. Wenn Sie mehrere Speichermedien behandeln möchten, überschreiben [OnRenderData](#onrenderdata). Wenn Ihre Daten in einer Datei oder variabler Größe ist, überschreiben [OnRenderFileData](#onrenderfiledata).

Weitere Informationen finden Sie unter [IDataObject:: GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.

##  <a name="onsetcolorscheme"></a>  COleServerItem::OnSetColorScheme

Wird aufgerufen, durch das Framework an ein Farben-Palette verwendet werden, wenn das OLE-Element zu bearbeiten.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Parameter

*lpLogPalette*<br/>
Zeiger auf ein Windows [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Farben-Palette verwendet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn die Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) Funktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die Standardimplementierung gibt "false" zurück. Überschreiben Sie diese Funktion, wenn Sie die empfohlene Palette verwenden möchten. Die Serveranwendung ist nicht erforderlich, die empfohlene Palette verwendet.

Weitere Informationen finden Sie unter [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) im Windows SDK.

##  <a name="onsetdata"></a>  COleServerItem::OnSetData

Wird aufgerufen, durch das Framework das OLE-Element-Daten mit den angegebenen Daten zu ersetzen.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Parameter

*lpFormatEtc*<br/>
Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur, die das Format der Daten angibt.

*lpStgMedium*<br/>
Zeiger auf eine [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) Struktur, in dem sich die Daten befindet.

*bRelease*<br/>
Gibt an, die das Speichermedium nach Abschluss des Funktionsaufrufs ist. Der Aufrufer entscheidet, die verantwortlich für die Freigabe der Ressourcen, die für das Speichermedium zugeordnet ist. Der Aufrufer wird durch Festlegen von *bRelease*. Wenn *bRelease* ist ungleich NULL ist, das Serverelement übernimmt die Besitzrechte, das Freigeben des Mediums, wenn es abgeschlossen ist, verwenden. Wenn *bRelease* ist 0, der Aufrufer und das Serverelement kann das Speichermedium nur für die Dauer des Aufrufs.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Das Serverelement wird nicht den Besitz der Daten, bis er erfolgreich abgerufen hat. Es ist, also nicht den Besitz übernehmen, wenn 0 zurückgegeben. Wenn die Datenquelle den Besitz übernimmt, werden durch Aufrufen von das Speichermedium freigibt der [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Funktion.

Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um Daten für das OLE-Element mit den angegebenen Daten zu ersetzen. Dies ist ein fortschrittlicher überschreibbar.

Weitere Informationen finden Sie unter [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc), und [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) im Windows SDK.

##  <a name="onsetextent"></a>  COleServerItem::OnSetExtent

Wird aufgerufen, durch das Framework, um dem OLE-Element mitzuteilen, wie viel Speicherplatz im Containerdokument verfügbar ist.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Parameter

*nDrawAspect*<br/>
Gibt den Aspekt des OLE-Elements, dessen Grenzen angegeben werden. Dieser Parameter kann einen der folgenden Werte aufweisen:

- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.

- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.

- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.

- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.

*size*<br/>
Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Struktur, die die neue Größe des OLE-Elements angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion wird aufgerufen, wenn die [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) -Memberfunktion des entsprechenden `COleClientItem` -Objekts aufgerufen wird. Die standardmäßige Implementierung legt den [M_sizeExtent](#m_sizeextent) Member der angegebenen Größe Wenn *nDrawAspect* ist DVASPECT_CONTENT; andernfalls wird 0 zurückgegeben. Überschreiben Sie diese Funktion zum durchführen, besondere Bearbeitung, wenn Sie die Größe des Elements ändern.

##  <a name="onshow"></a>  COleServerItem::OnShow

Wird aufgerufen, durch das Framework angewiesen, die Server-Anwendung zum Anzeigen des OLE-Elements vorhanden.

```
virtual void OnShow();
```

### <a name="remarks"></a>Hinweise

Diese Funktion in der Regel aufgerufen wird, wenn der Benutzer der Container-Anwendung ein Element erstellt, oder führt ein Verb, z. B. bearbeiten "", erfordert, dass das Element, das angezeigt werden. Die Standardimplementierung versucht, direkte Aktivierung. Wenn dies fehlschlägt, ruft die Funktion der `OnOpen` Memberfunktion versucht, die OLE-Element in einem separaten Fenster anzuzeigen.

Überschreiben Sie diese Funktion, sollten Sie durchführen, besondere Bearbeitung, wenn ein OLE-Element angezeigt wird.

##  <a name="onupdate"></a>  COleServerItem::OnUpdate

Wird vom Framework aufgerufen, wenn Sie ein Element geändert wurde.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Parameter

*pSender*<br/>
Zeiger auf das Element, das das Dokument geändert. NULL kann sein.

*lHint*<br/>
Enthält Informationen über die Änderung.

*pHint*<br/>
Zeiger auf ein Objekt, das Informationen über die Änderung zu speichern.

*nDrawAspect*<br/>
Ein Wert aus der DVASPECT-Enumeration. Dieser Parameter kann eine der folgenden Werte aufweisen:

- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.

- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.

- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.

- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ruft [NotifyChanged](#notifychanged), unabhängig von den oder die Sender.

##  <a name="onupdateitems"></a>  COleServerItem::OnUpdateItems

Wird aufgerufen, durch das Framework alle Elemente im Serverdokument zu aktualisieren.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ruft [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) für alle `COleClientItem` -Objekte im Dokument.

##  <a name="setitemname"></a>  COleServerItem::SetItemName

Rufen Sie diese Funktion bei der Erstellung eines verknüpften Elements, dessen Namen festzulegen.

```
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parameter

*lpszItemName*<br/>
Zeiger auf den neuen Namen des Elements.

### <a name="remarks"></a>Hinweise

Der Name muss innerhalb des Dokuments eindeutig sein. Wenn eine Serveranwendung so bearbeiten Sie ein verknüpftes Element aufgerufen wird, verwendet die Anwendung dieser Name auf um das Element zu suchen. Sie müssen sich nicht zum Aufrufen dieser Funktion für eingebettete Elemente.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CDocItem-Klasse](../../mfc/reference/cdocitem-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)
