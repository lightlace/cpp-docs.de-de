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
ms.openlocfilehash: 87545d67addb6a1f0931007d8912989968f7a74a
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53177848"
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
|[CGdiObject::Attach](#attach)|Fügt ein Windows-GDI-Objekt an eine `CGdiObject` Objekt.|
|[CGdiObject::CreateStockObject](#createstockobject)|Ruft ein Handle für eine der vordefinierten vordefinierten Stifte für Windows, Pinsel oder Schriftarten ab.|
|[CGdiObject::DeleteObject](#deleteobject)|Löscht das Windows-GDI-Objekt an die `CGdiObject` Objekt vom Arbeitsspeicher freigegeben werden und alle Dateisystem-Speicherkapazität, die dem Objekt zugeordnet.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|Löscht temporäre `CGdiObject` Objekten von erstellt `FromHandle`.|
|[CGdiObject::Detach](#detach)|Trennt ein Windows-GDI-Objekt aus einem `CGdiObject` Objekt und gibt ein Handle für das Windows-GDI-Objekt.|
|[CGdiObject::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CGdiObject` Objekts, dem ein Handle auf ein Windows-GDI-Objekt.|
|[CGdiObject::GetObject](#getobject)|Füllt ein Puffer mit Daten, die beschreibt, das Windows-GDI-Objekt angefügt die `CGdiObject` Objekt.|
|[CGdiObject::GetObjectType](#getobjecttype)|Ruft den Typ der GDI-Objekt ab.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|Gibt `m_hObject` , wenn **dies** NULL ist, in dem Groß-/Kleinschreibung NULL zurückgegeben wird.|
|[CGdiObject:: UnrealizeObject](#unrealizeobject)|Setzt den Ursprung eines Pinsels oder eine logische Palette zurückgesetzt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CGdiObject::operator! =](#operator_neq)|Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.|
|[CGdiObject::operator ==](#operator_eq_eq)|Bestimmt, ob zwei GDI-Objekte logisch gleich sind.|
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Ruft ein HANDLE für das angefügte Windows-GDI-Objekt ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|Ein HANDLE, mit der HBITMAP, HPALETTE, HRGN, HBRUSH, HPEN oder HFONT an dieses Objekt angefügt ist.|

## <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CGdiObject` direkt. Stattdessen erstellen Sie ein Objekt aus einer der davon abgeleiteten Klassen, z. B. `CPen` oder `CBrush`.

Weitere Informationen zu `CGdiObject`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="attach"></a>  CGdiObject::Attach

Fügt ein Windows-GDI-Objekt an eine `CGdiObject` Objekt.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parameter

*hObject*<br/>
Ein HANDLE für ein Windows-GDI-Objekt (z. B. HPEN oder HBRUSH).

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Anlage erfolgreich ist; andernfalls 0.

##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject

Erstellt ein `CGdiObject`-Objekt.

```
CGdiObject();
```

### <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CGdiObject` direkt. Stattdessen erstellen Sie ein Objekt aus einer der davon abgeleiteten Klassen, z. B. `CPen` oder `Cbrush`.

##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject

Ruft ein Handle auf eine der vordefinierten vordefinierten Windows-GDI-Stifte, Pinsel oder Schriftarten ab und fügt das GDI-Objekt, das die `CGdiObject` Objekt.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Eine Konstante, die den Typ des gewünschten Bestandsobjekt angibt. Der Parameter *FnObject* für [GetStockObject](/windows/desktop/api/wingdi/nf-wingdi-getstockobject) im Windows SDK für eine Beschreibung der entsprechenden Werte.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Aufruf dieser Funktion mit einer der abgeleiteten Klassen, entspricht der Windows-GDI-Objekttyp, z. B. `CPen` für einen vordefinierten Stift.

##  <a name="deleteobject"></a>  CGdiObject::DeleteObject

Löscht das angefügte Windows-GDI-Objekt vom Arbeitsspeicher freigegeben werden und alle Dateisystem-Speicherkapazität, die dem Windows-GDI-Objekt zugeordnet.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die GDI-Objekt wurde erfolgreich gelöscht wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Der zugeordnete Speicher der `CGdiObject` Objekt wird durch diesen Aufruf nicht beeinflusst. Eine Anwendung sollte nicht aufrufen `DeleteObject` auf eine `CGdiObject` -Objekt, das derzeit für einen Gerätekontext ausgewählt wird.

Wenn ein Musterpinsel gelöscht wird, wird die Bitmap dem Pinsel zugeordneten nicht gelöscht werden. Die Bitmap muss separat gelöscht werden.

##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap

Wird automatisch aufgerufen, die `CWinApp` -leerlaufzeithandler, `DeleteTempMap` löscht temporäre `CGdiObject` Objekten von erstellt `FromHandle`.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Hinweise

`DeleteTempMap` trennt das Windows-GDI-Objekt, das in ein temporäres angefügt `CGdiObject` Objekt vor dem Löschen der `CGdiObject` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

##  <a name="detach"></a>  CGdiObject::Detach

Trennt ein Windows-GDI-Objekt aus einem `CGdiObject` Objekt und gibt ein Handle für das Windows-GDI-Objekt.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein `HANDLE` so die Windows-GDI-Objekt getrennt; andernfalls NULL, wenn keine GDI-Objekt verknüpft ist.

##  <a name="fromhandle"></a>  CGdiObject::FromHandle

Gibt einen Zeiger auf eine `CGdiObject` Objekts, dem ein Handle auf ein Windows-GDI-Objekt.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parameter

*hObject*<br/>
Ein HANDLE für ein Windows-GDI-Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CGdiObject` temporär oder permanent sein können.

### <a name="remarks"></a>Hinweise

Wenn eine `CGdiObject` Objekt ist noch nicht auf das Windows-GDI-Objekt, ein temporäres angefügt `CGdiObject` Objekt erstellt und angefügt.

Diese temporären `CGdiObject` Objekt ist nur gültig, bis das nächste Mal die Anwendung hat die Zeit im Leerlauf in seiner Event-Schleife, die zu diesem Zeitpunkt werden alle temporären grafische Objekte gelöscht. Anders ausgedrückt: Dies ist, dass der Zugriff auf das temporäre Objekt während der Verarbeitung der Nachricht von einem Fenster nur gültig ist.

##  <a name="getobject"></a>  CGdiObject::GetObject

Füllt einen Puffer mit Daten, die ein angegebenen Objekt zu definieren.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Parameter

*nCount*<br/>
Gibt die Anzahl der Bytes für den Kopiervorgang die *LpObject* Puffer.

*lpObject*<br/>
Verweist auf einen vom Benutzer bereitgestellten Puffer, der besteht darin, die Informationen zu erhalten.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die abgerufen werden soll; Tritt auf, andernfalls 0, wenn ein Fehler an.

### <a name="remarks"></a>Hinweise

Die Funktion ruft eine Datenstruktur, die den Typ des grafisches Objekt, dessen Typ abhängt, wie in der folgenden Liste gezeigt:

|Object|Puffertyp|
|------------|-----------------|
|`CPen`|[LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen)|
|`CBrush`|[LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)|
|`CFont`|["LOGFONT"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)|
|`CBitmap`|[BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap)|
|`CPalette`|WORD|
|`CRgn`|Nicht unterstützt|

Wenn das Objekt ist ein `CBitmap` Objekt `GetObject` gibt nur die Breite, Höhe und Farbe Formatierungsinformationen der Bitmap. Die eigentlichen Bits können abgerufen werden, mithilfe von [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).

Wenn das Objekt ist ein `CPalette` Objekt `GetObject` Ruft ein Wort, das die Anzahl der Einträge in der Palette angibt. Ruft die Funktion nicht die [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) Struktur, die die Palette definiert. Eine Anwendung erhalten Sie Informationen zur Paletteneinträge durch Aufrufen von [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).

##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType

Ruft den Typ der GDI-Objekt ab.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Rückgabewert

Der Typ des Objekts, wenn erfolgreich; andernfalls 0. Der Wert kann in folgenden Formen vorliegen:

- OBJ_BITMAP Bitmap

- OBJ_BRUSH Pinsel

- OBJ_FONT Schriftart

- OBJ_PAL Palette

- OBJ_PEN Stift

- Erweiterte OBJ_EXTPEN Stift

- OBJ_REGION Region

- OBJ_DC Gerätekontext

- OBJ_MEMDC Speichergerätekontext

- OBJ_METAFILE Metadatei

- OBJ_METADC Metadatei-Gerätekontexts

- OBJ_ENHMETAFILE Erweiterte Metadatei

- OBJ_ENHMETADC erweitert-Metadatei-Gerätekontexts

##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle

Gibt `m_hObject` , wenn **dies** NULL ist, in dem Groß-/Kleinschreibung NULL zurückgegeben wird.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Ein HANDLE auf das angefügte Windows-GDI-Objekt Wenn kein Objekt verbunden ist, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dies ist Teil des Paradigmas Schnittstelle Allgemein Handle und ist nützlich, wenn NULL ein gültiger oder spezielle Wert für ein Handle ist.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).

##  <a name="m_hobject"></a>  CGdiObject::m_hObject

Ein HANDLE, mit der HBITMAP, HRGN, HBRUSH, HPEN, HPALETTE oder HFONT an dieses Objekt angefügt ist.

```
HGDIOBJ m_hObject;
```

##  <a name="operator_neq"></a>  CGdiObject::operator! =

Bestimmt, ob zwei GDI-Objekte logisch nicht gleich sind.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parameter

*obj*<br/>
Ein Zeiger auf eine vorhandene `CGdiObject`.

### <a name="remarks"></a>Hinweise

Bestimmt, ob ein GDI-Objekt auf der linken Seite ungleich ein GDI-Objekt auf der rechten Seite ist.

##  <a name="operator_eq_eq"></a>  CGdiObject::operator ==

Bestimmt, ob zwei GDI-Objekte logisch gleich sind.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parameter

*obj*<br/>
Ein Verweis auf einen vorhandenen `CGdiObject`.

### <a name="remarks"></a>Hinweise

Bestimmt, ob ein GDI-Objekt auf der linken Seite gleich ein GDI-Objekt auf der rechten Seite ist.

##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ

Ruft ein HANDLE für das angefügte Windows-GDI-Objekt ab. Wenn kein Objekt verbunden ist, andernfalls NULL.

```
operator HGDIOBJ() const;
```

##  <a name="unrealizeobject"></a>  CGdiObject:: UnrealizeObject

Setzt den Ursprung eines Pinsels oder eine logische Palette zurückgesetzt.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Während `UnrealizeObject` ist eine Memberfunktion der `CGdiObject` -Klasse, es sollte aufgerufen werden nur auf `CBrush` oder `CPalette` Objekte.

Für `CBrush` Objekte `UnrealizeObject` weist das System an den Ursprung der angegebenen Pinsel das nächste Mal zurücksetzen einen Gerätekontext ist ausgewählt. Wenn das Objekt ist ein `CPalette` Objekt `UnrealizeObject` weist das System an der Palette zu erkennen, als wäre es nicht bereits erzielt wurde. Das nächste Mal die Anwendung ruft die [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) -Funktion für die angegebene Palette, das System ordnet vollständig neu zu der Systempalette logische Palette.

Die `UnrealizeObject` Funktion sollte nicht mit vordefinierten Objekten verwendet werden. Die `UnrealizeObject` -Funktion muss aufgerufen werden, wenn Sie ein neuen Pinsel Ursprung festgelegt ist (von der [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) Funktion). Die `UnrealizeObject` Funktion muss nicht aufgerufen werden, für die derzeit ausgewählten Pinsels oder der aktuell ausgewählten Palette von keinem Anzeigekontext.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush-Klasse](../../mfc/reference/cbrush-class.md)<br/>
[CFont-Klasse](../../mfc/reference/cfont-class.md)<br/>
[CPalette-Klasse](../../mfc/reference/cpalette-class.md)<br/>
[CPen-Klasse](../../mfc/reference/cpen-class.md)<br/>
[CRgn-Klasse](../../mfc/reference/crgn-class.md)
