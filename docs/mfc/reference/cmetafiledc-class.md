---
title: CMetaFileDC-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4b19358b97ca0afbe7a70347e5b05bed9916846
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076346"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC-Klasse

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
|[CMetaFileDC::Close](#close)|Schließt den Gerätekontext aus, und erstellt ein Metadateihandle.|
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Schließt eine EMF-Gerätekontext aus, und erstellt eine EMF-Handle.|
|[CMetaFileDC::Create](#create)|Erstellt die Windows-Metadatei-Gerätekontexts und fügt es der `CMetaFileDC` Objekt.|
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Erstellt eine Metadatei-Gerätekontexts für eine EMF-Datei an.|

## <a name="remarks"></a>Hinweise

Um eine Windows-Metadatei zu implementieren, erstellen Sie zunächst eine `CMetaFileDC` Objekt. Aufrufen der `CMetaFileDC` Konstruktor rufen Sie dann die [erstellen](#create) Memberfunktion, die ein Windows-Metadatei-Gerätekontexts erstellt und fügt es der `CMetaFileDC` Objekt.

Als Nächstes senden die `CMetaFileDC` -Objekt die Reihenfolge der CDC-GDI-Befehle, die Sie möchten dafür wiedergegeben. Nur die GDI-Befehle, die Ausgabe, z. B. erstellen `MoveTo` und `LineTo`, kann verwendet werden.

Nachdem Sie die gewünschten Befehle an der Metadatei gesendet haben, rufen Sie die `Close` Memberfunktion, die die Metadatei Gerätekontexte schließt, und gibt ein Metadateihandle zurück. Dann verwerfen der `CMetaFileDC` Objekt.

[CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) können Sie dann das Metadateihandle die Metadatei wiederholt abzuspielen. Die Metadatei kann auch bearbeitet werden von Windows-Funktionen wie z. B. [CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea), die eine Metadatei auf den Datenträger kopiert.

Wenn die Metadatei nicht mehr benötigt wird, löschen Sie es aus dem Speicher mit der [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) Windows-Funktion.

Sie können auch implementieren die `CMetaFileDC` Objekts, sodass er verarbeiten kann, beide Aufrufe ausgegeben und GDI-Aufrufe wie z. B. Attribut `GetTextExtent`. Solche eine Metadatei ist flexibler und können weitere einfach allgemeine GDI-Code, der aus der Ausgabe und Attribut Aufrufe häufig besteht aus wiederverwenden. Die `CMetaFileDC` -Klasse erbt, zwei Gerätekontexte, `m_hDC` und `m_hAttribDC`, aus der CDC. Die `m_hDC` Gerätekontext verarbeitet alle [CDC](../../mfc/reference/cdc-class.md) GDI Ausgabe aufrufen und die `m_hAttribDC` Gerätekontext behandelt alle Aufrufe der CDC-GDI-Attribut. In der Regel finden Sie diese beiden Kontexte, in dem gleichen Gerät zu erhalten. Im Fall von `CMetaFileDC`, das DC-Attribut ist standardmäßig auf NULL festgelegt.

Erstellen Sie einen zweiten Gerätekontext, die Punkte auf dem Bildschirm, einem Drucker oder Geräte als eine Metadatei, Sie dann rufen die `SetAttribDC` Memberfunktion versucht, ordnen Sie den neuen Gerätekontext mit `m_hAttribDC`. GDI-Aufrufe Informationen nun geleitet werden, die neue `m_hAttribDC`. Ausgehende Aufrufe von GDI kehre zur `m_hDC`, die die Metadatei darstellt.

Weitere Informationen zu `CMetaFileDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="close"></a>  CMetaFileDC::Close

Schließt die Metadatei-Gerätekontexts und erstellt ein Windows-Metadatei-Handle, das verwendet werden kann, zur Wiedergabe der Metadatei mithilfe der [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) Member-Funktion.

```
HMETAFILE Close();
```

### <a name="return-value"></a>Rückgabewert

Eine gültige HMETAFILE, wenn die Funktion erfolgreich ist; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Das Windows Metafile-Handle kann auch verwendet werden, bearbeiten Sie die Metadatei mit Windows-Funktionen wie z. B. [CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea).

Löschen Sie die Metadatei nach der Verwendung durch den Aufruf der Windows [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) Funktion.

##  <a name="closeenhanced"></a>  CMetaFileDC::CloseEnhanced

Schließt eine EMF-Gerätekontext aus, und gibt ein Handle, das eine EMF-Datei identifiziert.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für eine erweiterte Metadatei, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Eine Anwendung kann der von dieser Funktion zurückgegebenen EMF-Handle verwenden, um die folgenden Aufgaben ausführen:

- Zeigen Sie ein Bild in eine erweiterte Metadatei gespeichert

- Erstellen Sie Kopien der erweiterten Metadatei

- Auflisten Sie, bearbeiten Sie oder kopieren Sie die einzelnen Datensätze in der erweiterten Metadatei

- Rufen Sie eine optionale Beschreibung der Metadatei Inhalte aus dem EMF-header

- Rufen Sie eine Kopie des EMF-Headers

- Rufen Sie eine binäre Kopie der erweiterten Metadatei

- Auflisten der Farben in der befehlspalette von optional

- Konvertieren Sie eine EMF-Datei in eine Windows-Metadatei

Wenn die Anwendung nicht mehr das Handle für die erweiterte Metadatei benötigt, sollte er das Handle freigeben, durch Aufruf der Win32 `DeleteEnhMetaFile` Funktion.

##  <a name="cmetafiledc"></a>  CMetaFileDC::CMetaFileDC

Erstellen einer `CMetaFileDC` Objekt in zwei Schritten.

```
CMetaFileDC();
```

### <a name="remarks"></a>Hinweise

Rufen Sie zunächst `CMetaFileDC`, rufen Sie anschließend `Create`, die die Windows-Metadatei-Gerätekontexts erstellt, und fügt es der `CMetaFileDC` Objekt.

##  <a name="create"></a>  CMetaFileDC::Create

Erstellen einer `CMetaFileDC` Objekt in zwei Schritten.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>Parameter

*lpszFilename*<br/>
Verweist auf eine Null-terminierte Zeichenfolge. Gibt den Dateinamen der Metadatei zu erstellen. Wenn *LpszFilename* NULL ist, wird eine neue in-Memory-Metadatei erstellt.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Rufen Sie zunächst den Konstruktor `CMetaFileDC`, rufen Sie anschließend `Create`, die die Windows-Metadatei-Gerätekontexts erstellt, und fügt es der `CMetaFileDC` Objekt.

##  <a name="createenhanced"></a>  CMetaFileDC::CreateEnhanced

Erstellt einen Gerätekontext für eine EMF-Datei an.

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>Parameter

*pDCRef*<br/>
Identifiziert ein Referenzgerät für die erweiterte Metadatei an.

*lpszFileName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge. Gibt den Dateinamen für die erweiterte Metadatei erstellt werden. Wenn dieser Parameter NULL ist, wird die erweiterte Metadatei speicherbasierten und seinen Inhalt verloren gehen, wenn das Objekt zerstört wird oder wenn die Win32 `DeleteEnhMetaFile` -Funktion aufgerufen wird.

*lpBounds*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Datenstruktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Abmessungen gibt an, in HIMETRIC-Einheiten (in Schritten von.01-Millimeter) des Bilds in der erweiterten Metadatei gespeichert werden.

*lpszDescription*<br/>
Verweist auf eine 0 (null) endende Zeichenfolge, die den Namen der Anwendung angibt, die das Bild als auch der Grafik Titel erstellt.

### <a name="return-value"></a>Rückgabewert

Ein Handle des Gerätekontexts für die erweiterte Metadatei, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Domänencontroller kann verwendet werden, um eine geräteunabhängige Grafik zu speichern.

Windows verwendet, das Referenzgerät identifizierte die *pDCRef* Parameter zum Aufzeichnen der Auflösung und Einheiten des Geräts auf dem ein Bild ursprünglich angezeigt wurde. Wenn die *pDCRef* Parameter NULL ist, das aktuelle Anzeigegerät zu Referenzzwecken verwendet.

Die linken und oberen Elemente von der `RECT` Datenstruktur verweist die *LpBounds* Parameter muss kleiner sein als die Rechte und untere Elemente bzw. In der Abbildung sind die Punkte, an den Rändern des Rechtecks enthalten. Wenn *LpBounds* NULL ist, die Graphics Device Interface (GDI) berechnet, die Abmessungen des das kleinste Rechteck befindet, die das Bild gezeichnet wird, von der Anwendung einschließen können. Die *LpBounds* Parameter muss angegeben werden, wenn möglich.

Die Zeichenfolge verweist die *LpszDescription* Parameter muss ein Null-Zeichen zwischen den Namen der Anwendung und den Namen des Bilds enthalten und muss mit zwei Null-Zeichen beendet werden, z. B. "XYZ Grafiken Editor\0Bald Eagle\0\0, "\0 darstellt, in dem das Null-Zeichen. Wenn *LpszDescription* NULL ist, kein entsprechenden Eintrag im EMF-Header vorhanden ist.

Anwendungen verwenden den DC, der von dieser Funktion erstellt ein Bild Grafiken in eine erweiterte Metadatei zu speichern. Das Handle, das diesen Domänencontroller identifizieren kann an jede GDI-Funktion übergeben werden.

Eine Anwendung ein Bild in eine erweiterte Metadatei gespeichert werden, können angezeigt das Bild auf einem beliebigen Ausgabegerät durch Aufrufen der `CDC::PlayMetaFile` Funktion. Wenn das Bild angezeigt wird, verwendet Windows die verweist Rectangle der *LpBounds* Parameter und die Daten vom Gerät Verweis zu positionieren und Skalieren das Bild. Der Gerätekontext, die von dieser Funktion zurückgegebenen enthält die gleichen Standardattribute, die alle neuen Domänencontroller zugeordnet.

Anwendungen müssen die Win32 verwenden `GetWinMetaFileBits` Funktion, um eine erweiterte Metadatei in älteren Windows-Metafile-Format zu konvertieren.

Verwenden Sie der Dateinamen für die erweiterte Metadatei sollte die. EMF-Erweiterung.

## <a name="see-also"></a>Siehe auch

[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

