---
title: CPalette-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
ms.openlocfilehash: 1dc29a675f6ab3883683b3afae7e22e7ed0f1cc3
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504762"
---
# <a name="cpalette-class"></a>CPalette-Klasse

Kapselt eine Windows-Farbpalette.

## <a name="syntax"></a>Syntax

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPalette::CPalette](#cpalette)|Erstellt eine `CPalette` Objekt mit keine angefügten Windows-Palette. Sie initialisieren, müssen die `CPalette` Objekt mit einem der Initialisierung-Memberfunktionen, bevor sie verwendet werden kann.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|Ersetzt die Einträge in der logischen Palette von identifiziert die `CPalette` Objekt. Die Anwendung verfügt nicht zum Aktualisieren seines Clientbereichs, da Windows die neuen Einträge in der Systempalette direkt zugeordnet.|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Erstellt eine Halbtonpalette für den Gerätekontext und fügt es der `CPalette` Objekt.|
|[CPalette::CreatePalette](#createpalette)|Erstellt eine Windows-Farben-Palette, und fügt es der `CPalette` Objekt.|
|[CPalette::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CPalette` Objekt, wenn ein Handle auf ein Objekt der Windows-Palette zu erhalten.|
|[CPalette::GetEntryCount](#getentrycount)|Ruft die Anzahl der Paletteneinträge in einer logischen Palette ab.|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Gibt den Index des Eintrags in der logischen Palette, die einen Farbwert am ehesten entspricht.|
|[CPalette::GetPaletteEntries](#getpaletteentries)|Ruft einen Bereich von Palette von Einträgen in einer logischen Palette ab.|
|[CPalette::ResizePalette](#resizepalette)|Ändert die Größe der logischen Palette anhand der `CPalette` Objekt, das die angegebene Anzahl von Einträgen.|
|[CPalette::SetPaletteEntries](#setpaletteentries)|Legt RGB-Werte und die Flags in einem Bereich von Einträgen in einer logischen Palette fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[HPALETTE-CPalette](#operator_hpalette)|Gibt die HPALETTE angefügt, um die `CPalette`.|

## <a name="remarks"></a>Hinweise

Eine Palette stellt eine Schnittstelle zwischen einer Anwendung und eine Farbe Ausgabegerät (z. B. ein Anzeigegerät) bereit. Die Schnittstelle kann es sich um die Anwendung, der die Funktionen der Farbe des Ausgabegeräts optimal zu nutzen, ohne mit den Farben angezeigt, die von anderen Anwendungen erheblich beeinträchtigen. Windows verwendet logische Palette von der Anwendung (eine Liste der erforderlichen Farben) und der Systempalette (die verfügbare Farben definiert), um die verwendeten Farben zu bestimmen.

Ein `CPalette` Objekt bietet Memberfunktionen aus, für die Bearbeitung der Palette, von dem Objekt bezeichnet. Erstellen einer `CPalette` Objekt, und seine Memberfunktionen verwenden, um die tatsächlichen Palette, ein Graphics Device Interface (GDI)-Objekt, zu erstellen und seine Einträge und andere Eigenschaften ändern.

Weitere Informationen zur Verwendung von `CPalette`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="animatepalette"></a>  : CPalette:: AnimatePalette

Einträge in der logischen Palette an angefügt ersetzt die `CPalette` Objekt.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parameter

*nStartIndex*<br/>
Gibt den ersten Eintrag in der Palette animiert werden soll.

*nNumEntries*<br/>
Gibt die Anzahl der Einträge in der Palette animiert werden soll.

*lpPaletteColors*<br/>
Verweist auf das erste Element eines Arrays von [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) Strukturen, ersetzen Sie die Paletteneinträge identifizierte *nStartIndex* und *nNumEntries*.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung ruft `AnimatePalette`, es muss keine aktualisieren seines Clientbereichs, da Windows die neuen Einträge in der Systempalette direkt zugeordnet.

Die `AnimatePalette` Funktion ändert nur Einträge mit dem PC_RESERVED-Flag festlegen, in der entsprechenden `palPaletteEntry` Mitglied der [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) -Struktur, die angefügt ist die `CPalette` Objekt. Finden Sie unter LOGPALETTE im Windows SDK für Weitere Informationen zu dieser Struktur.

##  <a name="cpalette"></a>  CPalette::CPalette

Erstellt ein `CPalette`-Objekt.

```
CPalette();
```

### <a name="remarks"></a>Hinweise

Das Objekt hat keine angefügten Palette bis zum Aufruf von `CreatePalette` eine anfügen.

##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette

Erstellt eine Halbtonpalette für den Gerätekontext.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Gibt den Gerätekontext.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Eine Anwendung sollte eine Halbtonpalette erstellen, wenn der streckmodus eines Gerätekontexts auf HALBTON festgelegt ist. Die logische Halbtonpalette zurückgegebenes der [CreateHalftonePalette](/windows/desktop/api/wingdi/nf-wingdi-createhalftonepalette) Member-Funktion muss dann ausgewählt und in den Gerätekontext, bevor Sie erkannte die [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) oder [ StretchDIBits](/windows/desktop/api/wingdi/nf-wingdi-stretchdibits) -Funktion aufgerufen wird.

Finden Sie im Windows-SDK Weitere Informationen zu `CreateHalftonePalette` und `StretchDIBits`.

##  <a name="createpalette"></a>  CPalette::CreatePalette

Initialisiert eine `CPalette` Objekt durch Erstellen einer logischen Windows-Farbpalette aus, und fügen Sie diesen auf den `CPalette` Objekt.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Parameter

*lpLogPalette*<br/>
Verweist auf eine [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) Struktur, die Informationen über die Farben in der logischen Palette enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Finden Sie im Windows-SDK Weitere Informationen zu den `LOGPALETTE` Struktur.

##  <a name="fromhandle"></a>  CPalette::FromHandle

Gibt einen Zeiger auf eine `CPalette` Objekt, wenn ein Handle auf ein Objekt der Windows-Palette zu erhalten.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Parameter

*hPalette*<br/>
Ein Handle für eine Windows-GDI-Farben-Palette.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CPalette` -Objekt, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn eine `CPalette` Objekt ist noch nicht auf die Windows-Farbpalette, eine temporäre angefügt `CPalette` Objekt erstellt und angefügt. Diese temporären `CPalette` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Zeit im Leerlauf in seiner Ereignisschleife verfügt, an der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht für ein Fenster gültig.

##  <a name="getentrycount"></a>  CPalette::GetEntryCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Einträge in einer bestimmten logischen Palette an.

```
int GetEntryCount();
```

### <a name="return-value"></a>Rückgabewert

Anzahl von Einträgen in einer logischen Palette.

##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex

Gibt den Index des Eintrags in der logischen Palette, die den Wert der angegebenen Farbe am ehesten entspricht.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Parameter

*crColor*<br/>
Gibt die Farbe, die abgeglichen werden.

### <a name="return-value"></a>Rückgabewert

Der Index eines Eintrags in einer logischen Palette. Der Eintrag enthält, die Farbe, die am häufigsten fast mit die angegebene Farbe übereinstimmt.

##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries

Ruft einen Bereich von Palette von Einträgen in einer logischen Palette ab.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Parameter

*nStartIndex*<br/>
Gibt den ersten Eintrag in der logischen Palette abgerufen werden sollen.

*nNumEntries*<br/>
Gibt die Anzahl der Einträge in der logischen Palette abgerufen werden sollen.

*lpPaletteColors*<br/>
Verweist auf ein Array von [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) Datenstrukturen für die Paletteneinträge zu erhalten. Das Array muss mindestens so viele Datenstrukturen laut enthalten *nNumEntries*.

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Einträgen, die von der logischen Palette abgerufen werden soll; 0, wenn die Funktion fehlgeschlagen ist.

##  <a name="operator_hpalette"></a>  HPALETTE-CPalette

Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle des erhalten die `CPalette` Objekt.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CPalette` Objekt; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung eines Objekts HPALETTE unterstützt.

Weitere Informationen zur Verwendung von Grafikobjekten finden Sie im Artikel [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.

##  <a name="resizepalette"></a>  CPalette::ResizePalette

Ändert die Größe der logischen Palette angefügt, um die `CPalette` Objekt, das die Anzahl von Einträgen, die anhand des *nNumEntries*.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Parameter

*nNumEntries*<br/>
Gibt die Anzahl der Einträge in der Palette an, nachdem sie die Größe geändert wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Palette erfolgreich geändert wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung ruft `ResizePalette` um die Größe der Palette zu reduzieren, werden die Einträge in der Größe Palette verbleibende unverändert. Wenn die Anwendung ruft `ResizePalette` um der Palette zu vergrößern, werden die Einträge für die zusätzliche Palette auf Schwarz festgelegt (die Rot-, Grün- und Blau-Werte sind alle 0) festgelegt, und die Flags für alle weiteren Einträge werden auf 0 festgelegt.

Weitere Informationen zur Windows-API `ResizePalette`, finden Sie unter [ResizePalette](/windows/desktop/api/wingdi/nf-wingdi-resizepalette) im Windows SDK.

##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries

Legt RGB-Werte und die Flags in einem Bereich von Einträgen in einer logischen Palette fest.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parameter

*nStartIndex*<br/>
Gibt den ersten Eintrag in der logischen Palette festgelegt werden.

*nNumEntries*<br/>
Gibt die Anzahl der Einträge in der logischen Palette festgelegt werden.

*lpPaletteColors*<br/>
Verweist auf ein Array von [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) Datenstrukturen für die Paletteneinträge zu erhalten. Das Array muss mindestens so viele Datenstrukturen laut enthalten *nNumEntries*.

### <a name="return-value"></a>Rückgabewert

Legen Sie die Anzahl der Einträge in der logischen Palette; 0, wenn die Funktion fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Wenn die logische Palette für einen Gerätekontext ausgewählt wird, wenn die Anwendung aufruft `SetPaletteEntries`, werden die Änderungen nicht wirksam bis die Anwendung ruft [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).

Weitere Informationen finden Sie unter [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEntries](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)
