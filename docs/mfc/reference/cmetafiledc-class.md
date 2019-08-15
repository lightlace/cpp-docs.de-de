---
title: Cmetafiledc-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
ms.openlocfilehash: 61e8442c085a5be0a7266409daf973bf63f52a7f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505506"
---
# <a name="cmetafiledc-class"></a>Cmetafiledc-Klasse

Implementiert eine Windows-Metadatei, die eine Sequenz von Graphics Device Interface (GDI)-Befehlen enthält, dass Sie wiedergeben können, um ein gewünschtes Bild oder einen Text zu erstellen.

## <a name="syntax"></a>Syntax

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|Erstellt ein `CMetaFileDC`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMetaFileDC::Close](#close)|Schließt den Gerätekontext und erstellt ein metadateihandle.|
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Schließt einen erweiterten Metafile-Gerätekontext und erstellt ein erweitertes Metafile-handle.|
|[CMetaFileDC::Create](#create)|Erstellt den Windows-Metadatei-Gerätekontext und fügt ihn `CMetaFileDC` an das-Objekt an.|
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Erstellt einen Metadatei-Gerätekontext für eine Metadatei mit erweitertem Format.|

## <a name="remarks"></a>Hinweise

Zum Implementieren einer Windows-Metadatendatei erstellen Sie `CMetaFileDC` zuerst ein-Objekt. Rufen Sie `CMetaFileDC` den Konstruktor auf, und rufen Sie dann die [Create](#create) Member-Funktion auf, die einen Windows-Metadatei- `CMetaFileDC` Gerätekontext erstellt und an das-Objekt anfügt.

Senden Sie das `CMetaFileDC` Objekt als nächstes die Sequenz der CDC-GDI-Befehle, die Sie wiedergeben möchten. Es können nur die GDI `MoveTo` -Befehle verwendet werden, die eine Ausgabe erstellen, z. b. und. `LineTo`

Nachdem Sie die gewünschten Befehle an die Metadatendatei gesendet haben, müssen `Close` Sie die Member-Funktion aufzurufen, die die Metadatei-Geräte Kontexte schließt und ein Metadatei-handle zurückgibt. Löschen Sie dann das `CMetaFileDC` -Objekt.

[CDC::P laymetafile](../../mfc/reference/cdc-class.md#playmetafile) kann dann das metadateihandle verwenden, um die Metadatendatei wiederholt wiederzugeben. Die Metadatendatei kann auch von Windows-Funktionen wie [copymetafile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)bearbeitet werden, die eine Metadatei auf einen Datenträger kopieren.

Wenn die Metadatei nicht mehr benötigt wird, löschen Sie Sie mit der Windows-Funktion [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) aus dem Arbeitsspeicher.

Sie können das `CMetaFileDC` -Objekt auch implementieren, damit es sowohl Ausgabe Aufrufe als auch Attribut-GDI-Aufrufe `GetTextExtent`wie verarbeiten kann. Eine solche Metadatendatei ist flexibler und kann allgemeinen GDI-Code, der häufig aus einer Mischung aus Ausgabe-und Attribut aufrufen besteht, leichter wieder verwenden. Die `CMetaFileDC` `m_hDC` -Klasse erbt zwei Geräte Kontexte und `m_hAttribDC`, von CDC. Der `m_hDC` Gerätekontext verarbeitet alle [CDC](../../mfc/reference/cdc-class.md) -GDI-Ausgabe Aufrufe `m_hAttribDC` , und der Gerätekontext verarbeitet alle CDC-GDI-Attribut Aufrufe. Normalerweise verweisen diese beiden Geräte Kontexte auf dasselbe Gerät. Im Fall von `CMetaFileDC`wird das Attribut DC standardmäßig auf NULL festgelegt.

Erstellen Sie einen zweiten Gerätekontext, der auf den Bildschirm, einen Drucker oder ein anderes Gerät als eine Metadatei verweist, `SetAttribDC` und rufen Sie dann die Member-Funktion auf `m_hAttribDC`, um den neuen Gerätekontext zuzuordnen. GDI-Aufrufe werden nun an die neue `m_hAttribDC`weitergeleitet. Ausgabe-GDI-Aufrufe werden `m_hDC`an weitergeleitet, der die Metadatei darstellt.

Weitere Informationen zu `CMetaFileDC`finden Sie unter [Geräte Kontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>Anforderungen

**Header:** Afxext. h

##  <a name="close"></a>Cmetafiledc:: Close

Schließt den Metadatei-Gerätekontext und erstellt ein Windows-metadateihandle, das verwendet werden kann, um die Metadatei mithilfe der [CDC::P laymetafile](../../mfc/reference/cdc-class.md#playmetafile) -Member-Funktion wiederzugeben.

```
HMETAFILE Close();
```

### <a name="return-value"></a>Rückgabewert

Eine gültige HMETAFILE, wenn die Funktion erfolgreich ist. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Das Windows-Metadatei-Handle kann auch verwendet werden, um die Metadatendatei mit Windows-Funktionen wie [copymetafile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)zu bearbeiten.

Löschen Sie die Metadatendatei nach der Verwendung, indem Sie die Windows [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) -Funktion aufrufen.

##  <a name="closeenhanced"></a>Cmetafiledc:: closeenhanced

Schließt einen erweiterten Metafile-Gerätekontext und gibt ein Handle zurück, das eine Metadatei mit erweitertem Format identifiziert.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle einer erweiterten Metadatei, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Eine Anwendung kann das von dieser Funktion zurückgegebene erweiterte metadateihandle verwenden, um die folgenden Aufgaben auszuführen:

- Anzeigen eines Bilds, das in einer erweiterten Metadatei gespeichert ist

- Kopien der erweiterten Metadatei erstellen

- Auflisten, bearbeiten oder Kopieren einzelner Datensätze in der erweiterten Metadatei

- Eine optionale Beschreibung des metadateiinhalts aus dem Enhanced-Metadatei-Header abrufen

- Abrufen einer Kopie des Headers "Enhanced-Metafile"

- Abrufen einer binären Kopie der erweiterten Metadatei

- Auflisten der Farben in der optionalen Palette

- Konvertieren einer Metadatei mit erweitertem Format in eine Metadatei im Windows-Format

Wenn die Anwendung das erweiterte metadateihandle nicht mehr benötigt, sollte das Handle durch Aufrufen der Win32 `DeleteEnhMetaFile` -Funktion freigegeben werden.

##  <a name="cmetafiledc"></a>Cmetafiledc:: cmetafiledc

Erstellen Sie `CMetaFileDC` ein-Objekt in zwei Schritten.

```
CMetaFileDC();
```

### <a name="remarks"></a>Hinweise

Zuerst wird aufgerufen `CMetaFileDC`, und dann `Create`wird aufgerufen, wodurch der Windows-Metadatei-Gerätekontext erstellt und `CMetaFileDC` an das-Objekt angefügt wird.

##  <a name="create"></a>Cmetafiledc:: Create

Erstellen Sie `CMetaFileDC` ein-Objekt in zwei Schritten.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFilename*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge. Gibt den Dateinamen der zu erstellenden Metadatendatei an. Wenn *lpszfilename* den Wert NULL hat, wird eine neue in-Memory-Metadatei erstellt.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Zuerst wird der-Konstruktor `CMetaFileDC`aufgerufen, und `Create`dann wird aufgerufen, wodurch der Windows-Metadatei-Gerätekontext erstellt `CMetaFileDC` und an das-Objekt angefügt wird.

##  <a name="createenhanced"></a>Cmetafiledc:: kreateenhanced

Erstellt einen Gerätekontext für eine Metadatei mit erweitertem Format.

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>Parameter

*pDCRef*<br/>
Identifiziert ein Referenzgerät für die erweiterte Metadatei.

*lpszFileName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge. Gibt den Dateinamen für die erweiterte Metadatendatei an, die erstellt werden soll. Wenn dieser Parameter NULL ist, ist die erweiterte Metadatei Speicher basiert, und die Inhalte gehen verloren, wenn das Objekt zerstört wird `DeleteEnhMetaFile` oder wenn die Win32-Funktion aufgerufen wird.

*lpBounds*<br/>
Verweist auf eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Datenstruktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Dimensionen in HIMETRIC-Einheiten (in 01-Millimeter-Schritten) des Bildes angibt, das in der erweiterten Metadatei gespeichert werden soll.

*lpszDescription*<br/>
Verweist auf eine mit NULL endend beendete Zeichenfolge, die den Namen der Anwendung angibt, die das Bild erstellt hat, sowie den Titel des Bilds.

### <a name="return-value"></a>Rückgabewert

Ein Handle des Geräte Kontexts für die erweiterte Metadatei, wenn erfolgreich. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Domänen Controller kann zum Speichern eines geräteunabhängigen Bilds verwendet werden.

Windows verwendet das Referenzgerät, das vom Parameter *pdkref* identifiziert wird, um die Auflösung und die Einheiten des Geräts aufzuzeichnen, auf dem das Bild ursprünglich angezeigt wurde. Wenn der *pdkref* -Parameter NULL ist, wird das aktuelle Anzeigegerät für den Verweis verwendet.

Die linken und oberen Elemente der `RECT` Datenstruktur, auf die durch den *lpbounds* -Parameter verwiesen wird, müssen kleiner als die Rechte bzw. untersten Member sein. Punkte entlang der Kanten des Rechtecks sind im Bild enthalten. Wenn *lpbounds* den Wert NULL aufweist, berechnet die Graphics Device Interface (GDI) die Dimensionen des kleinsten Rechtecks, das das Bild einschließen kann, das von der Anwendung gezeichnet wird. Der *lpbounds* -Parameter sollte nach Möglichkeit bereitgestellt werden.

Die Zeichenfolge, auf die durch den *lpszdescription* -Parameter verwiesen wird, muss ein NULL-Zeichen zwischen dem Anwendungsnamen und dem Bildnamen enthalten und muss mit zwei NULL-Zeichen enden – z. b. "XYZ graphics editor\0kahl eagle\0\0", wobei \ 0 den Wert darstellt. das NULL Zeichen. Wenn *lpszdescription* NULL ist, gibt es keinen entsprechenden Eintrag im Enhanced-Metafile-Header.

Anwendungen verwenden den von dieser Funktion erstellten DC zum Speichern eines Grafik Bilds in einer erweiterten Metadatei. Das Handle, das diesen DC identifiziert, kann an jede GDI-Funktion übermittelt werden.

Nachdem eine Anwendung ein Bild in einer erweiterten Metadatei gespeichert hat, kann Sie das Bild auf jedem Ausgabegerät anzeigen, indem `CDC::PlayMetaFile` die-Funktion aufgerufen wird. Beim Anzeigen des Bilds verwendet Windows das Rechteck, auf das durch den *lpbounds* -Parameter verwiesen wird, und die Auflösungs Daten des Referenz Geräts, um das Bild zu positionieren und zu skalieren. Der von dieser Funktion zurückgegebene Gerätekontext enthält dieselben Standard Attribute, die mit jedem neuen DC verknüpft sind.

Anwendungen müssen die Win32 `GetWinMetaFileBits` -Funktion verwenden, um eine erweiterte Metadatei in das ältere Windows-Metadatei-Format zu konvertieren.

Der Dateiname für die erweiterte Metadatei sollte den verwenden. EMF-Erweiterung.

## <a name="see-also"></a>Siehe auch

[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
