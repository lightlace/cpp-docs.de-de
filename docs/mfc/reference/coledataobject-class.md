---
title: COleDataObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
ms.openlocfilehash: c25fd7e91c59d7bea06325fbb27471d8f90f589d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504246"
---
# <a name="coledataobject-class"></a>COleDataObject-Klasse

Wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element verwendet.

## <a name="syntax"></a>Syntax

```
class COleDataObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDataObject::COleDataObject](#coledataobject)|Erstellt ein `COleDataObject`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDataObject::Attach](#attach)|Fügt das angegebene OLE-Datenobjekt an `COleDataObject`das-Objekt an.|
|[COleDataObject::AttachClipboard](#attachclipboard)|Fügt das Datenobjekt an, das sich in der Zwischenablage befindet.|
|[COleDataObject::BeginEnumFormats](#beginenumformats)|Bereitet mindestens einen nachfolgenden `GetNextFormat` Aufruf vor.|
|[COleDataObject::Detach](#detach)|Trennt das `IDataObject` zugeordnete-Objekt.|
|[COleDataObject::GetData](#getdata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt in einem angegebenen Format.|
|[COleDataObject::GetFileData](#getfiledata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt `CFile` in einen Zeiger im angegebenen Format.|
|[COleDataObject::GetGlobalData](#getglobaldata)|Kopiert Daten aus dem angefügten OLE-Datenobjekt `HGLOBAL` in ein-Objekt im angegebenen Format.|
|[COleDataObject::GetNextFormat](#getnextformat)|Gibt das nächste verfügbare Datenformat zurück.|
|[COleDataObject::IsDataAvailable](#isdataavailable)|Überprüft, ob Daten in einem angegebenen Format verfügbar sind.|
|[COleDataObject::Release](#release)|Trennt das `IDataObject` zugeordnete-Objekt und gibt es frei.|

## <a name="remarks"></a>Hinweise

`COleDataObject`weist keine Basisklasse auf.

Diese Arten von Datenübertragungen umfassen eine Quelle und ein Ziel. Die Datenquelle wird als Objekt der [COleDataSource](../../mfc/reference/coledatasource-class.md) -Klasse implementiert. Wenn in einer Zielanwendung Daten abgelegt werden oder Sie zur Ausführung eines Einfügevorgangs aus der Zwischenablage aufgefordert werden, muss `COleDataObject` ein Objekt der Klasse erstellt werden.

Mit dieser Klasse können Sie ermitteln, ob die Daten in einem angegebenen Format vorhanden sind. Sie können auch die verfügbaren Datenformate auflisten oder überprüfen, ob ein bestimmtes Format verfügbar ist, und dann die Daten im bevorzugten Format abrufen. Das Abrufen von Objekten kann auf verschiedene Weise durchgeführt werden, einschließlich der Verwendung einer [CFile](../../mfc/reference/cfile-class.md)-, einer HGLOBAL- `STGMEDIUM` oder einer-Struktur.

Weitere Informationen finden Sie unter der [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-stgmedium) -Struktur in der Windows SDK.

Weitere Informationen zum Verwenden von Datenobjekten in der Anwendung finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`COleDataObject`

## <a name="requirements"></a>Anforderungen

**Header:** Afxole. h

##  <a name="attach"></a>COleDataObject:: Attach

Diese Funktion wird aufgerufen, um `COleDataObject` das Objekt einem OLE-Datenobjekt zuzuordnen.

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Parameter

*lpDataObject*<br/>
Verweist auf ein OLE-Datenobjekt.

*bAutoRelease*<br/>
TRUE, wenn das OLE-Datenobjekt freigegeben werden `COleDataObject` soll, wenn das Objekt zerstört wird; andernfalls false.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) in der Windows SDK.

##  <a name="attachclipboard"></a>COleDataObject:: AttachClipboard

Mit dieser Funktion wird das Datenobjekt, das sich derzeit in der Zwischenablage befindet `COleDataObject` , an das-Objekt angefügt.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Durch Aufrufen dieser Funktion wird die Zwischenablage gesperrt, bis dieses Datenobjekt freigegeben wird. Das Datenobjekt wird im Dekonstruktor für den `COleDataObject`freigegeben. Weitere Informationen finden Sie unter [OpenClipboard](/windows/win32/api/winuser/nf-winuser-openclipboard) und [CloseClipboard](/windows/win32/api/winuser/nf-winuser-closeclipboard) in der Win32-Dokumentation.

##  <a name="beginenumformats"></a>COleDataObject:: BeginEnumFormats

Rufen Sie diese Funktion auf, um nachfolgende `GetNextFormat` Aufrufe von für das Abrufen einer Liste von Datenformaten aus dem Element vorzubereiten.

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Hinweise

Nach einem-Rückruf `BeginEnumFormats`wird die Position des ersten von diesem Datenobjekt unterstützten Formats gespeichert. Bei aufeinander folgenden `GetNextFormat` Aufrufen von wird die Liste der verfügbaren Formate im Datenobjekt aufgelistet.

Um die Verfügbarkeit von Daten in einem bestimmten Format zu überprüfen, verwenden Sie [COleDataObject:: IsDataAvailable](#isdataavailable).

Weitere Informationen finden Sie unter [IDataObject:: EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) in der Windows SDK.

##  <a name="coledataobject"></a>COleDataObject:: COleDataObject

Erstellt ein `COleDataObject`-Objekt.

```
COleDataObject();
```

### <a name="remarks"></a>Hinweise

Ein Aufruf von [COleDataObject:: Attach](#attach) oder [COleDataObject:: AttachClipboard](#attachclipboard) muss erfolgen, bevor andere `COleDataObject` Funktionen aufgerufen werden.

> [!NOTE]
>  Da einer der Parameter für die Drag & Drop-Handler ein Zeiger auf eine `COleDataObject`ist, ist es nicht erforderlich, diesen Konstruktor aufzurufen, um Drag & Drop zu unterstützen.

##  <a name="detach"></a>COleDataObject::D Etach

Diese Funktion wird aufgerufen, um das `COleDataObject` Objekt vom zugeordneten OLE-Datenobjekt zu trennen, ohne das Datenobjekt freizugeben.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das OLE-Datenobjekt, das getrennt wurde.

### <a name="remarks"></a>Hinweise

##  <a name="getdata"></a>COleDataObject:: GetData

Rufen Sie diese Funktion auf, um Daten aus dem Element im angegebenen Format abzurufen.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parameter

*cfFormat*<br/>
Das Format, in dem Daten zurückgegeben werden sollen. Dieser Parameter kann eines der vordefinierten Zwischenablage Formate oder der Wert sein, der von der systemeigenen Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) -Funktion zurückgegeben wird.

*lpStgMedium*<br/>
Verweist auf eine [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-stgmedium) -Struktur, die Daten empfängt.

*lpFormatEtc*<br/>
Verweist auf eine [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) -Struktur, die das Format beschreibt, in dem die Daten zurückgegeben werden sollen. Geben Sie einen Wert für diesen Parameter an, wenn Sie zusätzliche Formatierungsinformationen angeben möchten, die über das in *cfFormat*angegebene Zwischenablage Format hinausgehen. Wenn er NULL ist, werden die Standardwerte für die anderen Felder in der `FORMATETC` -Struktur verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-stgmedium)und [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) in der Windows SDK.

Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) im Windows SDK.

##  <a name="getfiledata"></a>COleDataObject:: GetFileData

Rufen Sie diese Funktion auf, `CFile` um `CFile`ein-oder-abgeleitetes Objekt zu erstellen und um Daten `CFile` im angegebenen Format in einen-Zeiger abzurufen.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parameter

*cfFormat*<br/>
Das Format, in dem Daten zurückgegeben werden sollen. Dieser Parameter kann eines der vordefinierten Zwischenablage Formate oder der Wert sein, der von der systemeigenen Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) -Funktion zurückgegeben wird.

*lpFormatEtc*<br/>
Verweist auf eine [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) -Struktur, die das Format beschreibt, in dem die Daten zurückgegeben werden sollen. Geben Sie einen Wert für diesen Parameter an, wenn Sie zusätzliche Formatierungsinformationen angeben möchten, die über das in *cfFormat*angegebene Zwischenablage Format hinausgehen. Wenn er NULL ist, werden die Standardwerte für die anderen Felder in der `FORMATETC` -Struktur verwendet.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `CFile` neue `CFile`oder von abgeleitete Objekt, das die Daten enthält, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Abhängig vom Medium, in dem die Daten gespeichert werden, kann der tatsächliche Typ, auf den der Rückgabewert `CFile`verweist `CSharedFile`,, `COleStreamFile`oder sein.

> [!NOTE]
>  Das `CFile` Objekt, auf das der Rückgabewert dieser Funktion zugreift, ist im Besitz des Aufrufers. Es liegt in der Verantwortung des Aufrufers, `CFile` das Objekt zu **Löschen** und damit die Datei zu schließen.

Weitere Informationen finden Sie unter [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) in der Windows SDK.

Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) im Windows SDK.

##  <a name="getglobaldata"></a>COleDataObject:: getglobaldata

Rufen Sie diese Funktion auf, um einen globalen Speicherblock zuzuordnen und Daten im angegebenen Format in einen HGLOBAL abzurufen.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parameter

*cfFormat*<br/>
Das Format, in dem Daten zurückgegeben werden sollen. Dieser Parameter kann eines der vordefinierten Zwischenablage Formate oder der Wert sein, der von der systemeigenen Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) -Funktion zurückgegeben wird.

*lpFormatEtc*<br/>
Verweist auf eine [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) -Struktur, die das Format beschreibt, in dem die Daten zurückgegeben werden sollen. Geben Sie einen Wert für diesen Parameter an, wenn Sie zusätzliche Formatierungsinformationen angeben möchten, die über das in *cfFormat*angegebene Zwischenablage Format hinausgehen. Wenn er NULL ist, werden die Standardwerte für die anderen Felder in der `FORMATETC` -Struktur verwendet.

### <a name="return-value"></a>Rückgabewert

Das Handle des globalen Speicherblocks, der die Daten enthält, wenn der Vorgang erfolgreich ist. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) in der Windows SDK.

Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) im Windows SDK.

##  <a name="getnextformat"></a>COleDataObject:: getnextformat

Rufen Sie diese Funktion wiederholt auf, um alle Formate abzurufen, die zum Abrufen von Daten aus dem Element verfügbar sind.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>Parameter

*lpFormatEtc*<br/>
Verweist auf die [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) -Struktur, die die Formatinformationen empfängt, wenn der Funktions Rückruf zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn ein anderes Format verfügbar ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Nach einem Aufrufen von [COleDataObject:: BeginEnumFormats](#beginenumformats)wird die Position des ersten Formats gespeichert, das von diesem Datenobjekt unterstützt wird. Bei aufeinander folgenden `GetNextFormat` Aufrufen von wird die Liste der verfügbaren Formate im Datenobjekt aufgelistet. Verwenden Sie diese Funktionen, um die verfügbaren Formate aufzulisten.

Um die Verfügbarkeit eines bestimmten Formats zu überprüfen, wenden Sie [COleDataObject:: IsDataAvailable](#isdataavailable)an.

Weitere Informationen finden Sie unter [IEnumXXXX:: Next](/previous-versions//ms695273\(v=vs.85\)) in der Windows SDK.

##  <a name="isdataavailable"></a>COleDataObject:: IsDataAvailable

Rufen Sie diese Funktion auf, um zu bestimmen, ob ein bestimmtes Format zum Abrufen von Daten aus dem OLE-Element verfügbar ist.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>Parameter

*cfFormat*<br/>
Das Datenformat der Zwischenablage, das in der Struktur verwendet werden soll, auf die von *lpformatetc*verwiesen wird. Dieser Parameter kann eines der vordefinierten Zwischenablage Formate oder der Wert sein, der von der systemeigenen Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) -Funktion zurückgegeben wird.

*lpFormatEtc*<br/>
Verweist auf eine [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) -Struktur, die das gewünschte Format beschreibt. Geben Sie einen Wert für diesen Parameter nur an, wenn Sie zusätzliche Formatierungsinformationen über das in *cfFormat*angegebene Zwischenablage Format angeben möchten. Wenn er NULL ist, werden die Standardwerte für die anderen Felder in der `FORMATETC` -Struktur verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn Daten im angegebenen Format verfügbar sind. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion ist nützlich, bevor `GetData`, `GetFileData`oder `GetGlobalData`aufgerufen wird.

Weitere Informationen finden Sie unter [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) und [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) in der Windows SDK.

Weitere Informationen finden Sie unter [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) im Windows SDK.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CRichEditView:: queryakzeptdata](../../mfc/reference/cricheditview-class.md#queryacceptdata).

##  <a name="release"></a>COleDataObject:: Release

Mit dieser Funktion wird der Besitz des [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) -Objekts, das zuvor dem `COleDataObject` -Objekt zugeordnet war, freigegeben.

```
void Release();
```

### <a name="remarks"></a>Hinweise

Die `IDataObject` wurde dem `COleDataObject` zugeordnet, indem oder `Attach` `AttachClipboard` explizit oder durch das Framework aufgerufen wurde. Wenn der Parameter " *bautorelease* " von `Attach` "false `IDataObject` " ist, wird das Objekt nicht freigegeben. In diesem Fall ist der Aufrufer für das `IDataObject` Freigeben von durch Aufrufen von [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)verantwortlich.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel Hierarchien](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource-Klasse](../../mfc/reference/coledatasource-class.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
