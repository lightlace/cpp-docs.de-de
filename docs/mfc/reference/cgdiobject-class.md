---
title: CGdiObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
ms.openlocfilehash: ea82e2c667dcbd476d22ed23085d409b448b27ed
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506253"
---
# <a name="cgdiobject-class"></a>CGdiObject-Klasse

Stellt eine Basisklasse für verschiedene Arten von Objekten der Windows GDI (Graphics Device Interface) wie Bitmaps, Bereiche, Pinsel, Stifte, Paletten und Schriftwarten bereit.

## <a name="syntax"></a>Syntax

```
class CGdiObject : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CGdiObject::CGdiObject](#cgdiobject)|Erstellt ein `CGdiObject`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CGdiObject:: Attach](#attach)|Fügt ein Windows-GDI-Objekt `CGdiObject` an ein-Objekt an.|
|[CGdiObject::CreateStockObject](#createstockobject)|Ruft ein Handle für eines der vordefinierten Windows-Aktien Stifte, Pinsel oder Schriftarten ab.|
|[CGdiObject::DeleteObject](#deleteobject)|Löscht das an das `CGdiObject` Objekt angefügte Windows-GDI-Objekt aus dem Arbeitsspeicher, indem der gesamte dem Objekt zugeordnete Systemspeicher freigegeben wird|
|[CGdiObject::DeleteTempMap](#deletetempmap)|Löscht alle temporären `CGdiObject` Objekte, die `FromHandle`von erstellt werden.|
|[CGdiObject::Detach](#detach)|Trennt ein Windows-GDI-Objekt von `CGdiObject` einem-Objekt und gibt ein Handle für das Windows-GDI-Objekt zurück.|
|[CGdiObject::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CGdiObject` -Objekt zurück, das ein Handle für ein Windows-GDI-Objekt erhält.|
|[CGdiObject::GetObject](#getobject)|Füllt einen Puffer mit Daten, die das an das `CGdiObject` -Objekt angefügte Windows-GDI-Objekt beschreiben.|
|[CGdiObject::GetObjectType](#getobjecttype)|Ruft den Typ des GDI-Objekts ab.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|Gibt `m_hObject` zurück, wenn **dieser** nicht NULL ist. in diesem Fall wird NULL zurückgegeben.|
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Setzt den Ursprung eines Pinsels zurück oder setzt eine logische Palette zurück.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CGdiObject:: Operator! =](#operator_neq)|Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.|
|[CGdiObject::operator ==](#operator_eq_eq)|Bestimmt, ob zwei GDI-Objekte logisch gleich sind.|
|[CGdiObject:: Operator hgdiobj](#operator_hgdiobj)|Ruft ein Handle für das angefügte Windows-GDI-Objekt ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|Ein Handle, das die HBITMAP, hpalette, hrgn, hBrush, HPEN oder hFont enthält, die an dieses Objekt angefügt sind.|

## <a name="remarks"></a>Hinweise

Sie erstellen niemals direkt `CGdiObject` ein. Stattdessen erstellen Sie ein Objekt aus einer der abgeleiteten Klassen, z `CPen` . b. oder. `CBrush`

Weitere Informationen zu `CGdiObject`finden Sie unter [Graphic Objects](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="attach"></a>CGdiObject:: Attach

Fügt ein Windows-GDI-Objekt `CGdiObject` an ein-Objekt an.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parameter

*hobject*<br/>
Ein Handle für ein Windows-GDI-Objekt (z. b. HPEN oder hBrush).

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn Anlage erfolgreich ist. andernfalls 0.

##  <a name="cgdiobject"></a>CGdiObject:: CGdiObject

Erstellt ein `CGdiObject`-Objekt.

```
CGdiObject();
```

### <a name="remarks"></a>Hinweise

Sie erstellen niemals direkt `CGdiObject` ein. Stattdessen erstellen Sie ein Objekt aus einer der abgeleiteten Klassen, z `CPen` . b. oder. `Cbrush`

##  <a name="createstockobject"></a>CGdiObject:: anatestockobject

Ruft ein Handle für einen der vordefinierten Windows-GDI-Stifte,-Pinsel oder-Schriftarten ab und fügt das GDI-Objekt `CGdiObject` an das-Objekt an.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Eine-Konstante, die den Typ des gewünschten Aktien Objekts angibt. Eine Beschreibung der entsprechenden Werte finden Sie unter dem Parameter " *bnobject* " für " [GetStockObject](/windows/win32/api/wingdi/nf-wingdi-getstockobject) " im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Diese Funktion wird mit einer der abgeleiteten Klassen aufgerufen, die dem Windows-GDI-Objekttyp entsprechen, z `CPen` . b. für einen Aktien Stift.

##  <a name="deleteobject"></a>CGdiObject::D eleteobject

Löscht das angefügte Windows-GDI-Objekt aus dem Arbeitsspeicher, indem alle dem Windows-GDI-Objekt zugeordneten Systemspeicher freigegeben

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das GDI-Objekt erfolgreich gelöscht wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Der dem- `CGdiObject` Objekt zugeordnete Speicher ist von diesem-Befehl nicht betroffen. Eine Anwendung sollte nicht für `DeleteObject` ein `CGdiObject` -Objekt aufgerufen werden, das derzeit in einem Gerätekontext ausgewählt ist.

Wenn ein Muster Pinsel gelöscht wird, wird die dem Pinsel zugeordnete Bitmap nicht gelöscht. Die Bitmap muss unabhängig gelöscht werden.

##  <a name="deletetempmap"></a>CGdiObject::D eletetempmap

Wird automatisch vom Leerlauf `CWinApp` Zeit Handler aufgerufen und löscht `DeleteTempMap` alle temporären `CGdiObject` Objekte, die von `FromHandle`erstellt werden.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Hinweise

`DeleteTempMap`trennt das an ein temporäres `CGdiObject` Objekt angefügte Windows-GDI-Objekt vor dem Löschen des `CGdiObject` Objekts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

##  <a name="detach"></a>CGdiObject::D Etach

Trennt ein Windows-GDI-Objekt von `CGdiObject` einem-Objekt und gibt ein Handle für das Windows-GDI-Objekt zurück.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein `HANDLE` -Objekt für das getrennte Windows-GDI-Objekt; andernfalls NULL, wenn kein GDI-Objekt angefügt wird.

##  <a name="fromhandle"></a>CGdiObject:: FromHandle

Gibt einen Zeiger auf ein `CGdiObject` -Objekt zurück, das ein Handle für ein Windows-GDI-Objekt erhält.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parameter

*hobject*<br/>
Ein Handle für ein Windows-GDI-Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf einen `CGdiObject` , der temporär oder permanent sein kann.

### <a name="remarks"></a>Hinweise

Wenn ein `CGdiObject` -Objekt noch nicht an das Windows-GDI-Objekt angefügt `CGdiObject` ist, wird ein temporäres Objekt erstellt und angefügt.

Dieses temporäre `CGdiObject` Objekt ist nur gültig, bis das nächste Mal die Leerlaufzeit der Anwendung in der Ereignisschleife liegt. zu diesem Zeitpunkt werden alle temporären Grafik Objekte gelöscht. Eine andere Möglichkeit, dies zu sagen, besteht darin, dass das temporäre Objekt nur während der Verarbeitung einer Fenster Nachricht gültig ist.

##  <a name="getobject"></a>CGdiObject:: GetObject

Füllt einen Puffer mit Daten, die ein angegebenes Objekt definieren.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Parameter

*nCount*<br/>
Gibt die Anzahl der Bytes an, die in den *lpobject* -Puffer kopiert werden sollen.

*lpObject*<br/>
Verweist auf einen vom Benutzer bereitgestellten Puffer, der die Informationen empfangen soll.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der abgerufenen Bytes. andernfalls 0, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Die-Funktion Ruft eine Datenstruktur ab, deren Typ vom Typ des Grafik Objekts abhängt, wie in der folgenden Liste gezeigt:

|Objekt|Puffertyp|
|------------|-----------------|
|`CPen`|[LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|["LOGFONT"](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|Nicht unterstützt|

Wenn es sich bei dem `CBitmap` Objekt um `GetObject` ein-Objekt handelt, werden nur die breiten-, Höhen-und Farb Formatinformationen der Bitmap zurückgegeben. Die tatsächlichen Bits können mithilfe von [CBitmap:: getbitmapbits](../../mfc/reference/cbitmap-class.md#getbitmapbits)abgerufen werden.

Wenn es sich bei dem `CPalette` Objekt um `GetObject` ein-Objekt handelt, Ruft ein Wort ab, das die Anzahl der Einträge in der Palette angibt. Die-Funktion ruft nicht die [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) -Struktur ab, die die Palette definiert. Eine Anwendung kann Informationen zu paletteneinträgen abrufen, indem [CPalette:: GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)aufgerufen wird.

##  <a name="getobjecttype"></a>CGdiObject:: getObjectType

Ruft den Typ des GDI-Objekts ab.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Rückgabewert

Der Typ des Objekts, wenn erfolgreich. andernfalls 0. Der Wert kann in folgenden Formen vorliegen:

- OBJ_BITMAP-Bitmap

- OBJ_BRUSH-Pinsel

- OBJ_FONT-Schriftart

- OBJ_PAL-Palette

- OBJ_PEN Stift

- OBJ_EXTPEN erweiterter Stift

- OBJ_REGION-Region

- OBJ_DC-Gerätekontext

- OBJ_MEMDC Speichergeräte Kontext

- OBJ_METAFILE-Metadatei

- OBJ_METADC Metafile-Gerätekontext

- Erweiterte Metadatendatei OBJ_ENHMETAFILE

- OBJ_ENHMETADC Enhanced-Metafile-Gerätekontext

##  <a name="getsafehandle"></a>CGdiObject:: gezafehandle

Gibt `m_hObject` zurück, wenn **dieser** nicht NULL ist. in diesem Fall wird NULL zurückgegeben.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das angefügte Windows-GDI-Objekt. andernfalls NULL, wenn kein Objekt angefügt ist.

### <a name="remarks"></a>Hinweise

Dies ist Teil des allgemeinen Handles der Schnittstellen Schnittstelle und ist nützlich, wenn NULL ein gültiger oder spezieller Wert für ein Handle ist.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CWnd:: iswindowenabled](../../mfc/reference/cwnd-class.md#iswindowenabled).

##  <a name="m_hobject"></a>CGdiObject:: m_hObject

Ein Handle, das die HBITMAP, hrgn, hBrush, HPEN, hpalette oder hFont enthält, die an dieses Objekt angefügt sind.

```
HGDIOBJ m_hObject;
```

##  <a name="operator_neq"></a>CGdiObject:: Operator! =

Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parameter

*obj*<br/>
Ein Zeiger auf einen vorhandenen `CGdiObject`.

### <a name="remarks"></a>Hinweise

Bestimmt, ob ein GDI-Objekt auf der linken Seite gleich einem GDI-Objekt auf der rechten Seite ist.

##  <a name="operator_eq_eq"></a>CGdiObject:: Operator = =

Bestimmt, ob zwei GDI-Objekte logisch gleich sind.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parameter

*obj*<br/>
Ein Verweis auf eine vorhandene `CGdiObject`.

### <a name="remarks"></a>Hinweise

Bestimmt, ob ein GDI-Objekt auf der linken Seite gleich einem GDI-Objekt auf der rechten Seite ist.

##  <a name="operator_hgdiobj"></a>CGdiObject:: Operator hgdiobj

Ruft ein Handle für das angefügte Windows-GDI-Objekt ab. andernfalls NULL, wenn kein Objekt angefügt ist.

```
operator HGDIOBJ() const;
```

##  <a name="unrealizeobject"></a>CGdiObject:: UnrealizeObject

Setzt den Ursprung eines Pinsels zurück oder setzt eine logische Palette zurück.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Obwohl `UnrealizeObject` eine Member-Funktion `CGdiObject` der-Klasse ist, sollte Sie nur für `CBrush` -oder `CPalette` -Objekte aufgerufen werden.

Weist `CBrush` bei- `UnrealizeObject` Objekten das System an, den Ursprung des angegebenen Pinsels zurückzusetzen, wenn er das nächste Mal in einem Gerätekontext ausgewählt wird. Wenn es sich bei dem `CPalette` Objekt um `UnrealizeObject` ein-Objekt handelt, weist das System an, die Palette so zu erkennen, als wäre es zuvor noch nicht realisiert worden. Wenn die Anwendung das nächste Mal die [CDC:: RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) -Funktion für die angegebene Palette aufruft, ordnet das System die logische Palette vollständig der Systempalette zu.

Die `UnrealizeObject` -Funktion sollte nicht mit Aktien Objekten verwendet werden. Die `UnrealizeObject` -Funktion muss immer dann aufgerufen werden, wenn ein neuer Pinsel Ursprung festgelegt wird (mittels der [CDC:: setbrushorg](../../mfc/reference/cdc-class.md#setbrushorg) -Funktion). Die `UnrealizeObject` Funktion darf nicht für den aktuell ausgewählten Pinsel oder die aktuell ausgewählte Palette eines beliebigen Anzeige Kontexts aufgerufen werden.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush-Klasse](../../mfc/reference/cbrush-class.md)<br/>
[CFont-Klasse](../../mfc/reference/cfont-class.md)<br/>
[CPalette-Klasse](../../mfc/reference/cpalette-class.md)<br/>
[CPen-Klasse](../../mfc/reference/cpen-class.md)<br/>
[CRgn-Klasse](../../mfc/reference/crgn-class.md)
