---
title: CGopherLocator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs:
- C++
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d9309917fe89abbf3679060898861e1c698d660
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445840"
---
# <a name="cgopherlocator-class"></a>CGopherLocator-Klasse

Ruft einen Gopher-"Locator" von einem Gopherserver zu ab, bestimmt den Locatortyp und macht den Locator für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).

> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und deren Member sind veraltet, da, nicht auf der Windows XP-Plattform funktionieren, während sie weiterhin auf frühere Plattformen funktionieren.

## <a name="syntax"></a>Syntax

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Erstellt ein `CGopherLocator`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|Analysiert einen Gopher-Locator und die Attribute bestimmt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Greift direkt in gespeicherten Zeichen auf eine `CGopherLocator` Objekts als Zeichenfolge im C-Stil.|

## <a name="remarks"></a>Hinweise

Eine Anwendung muss einem Gopherserver Locator abrufen, bevor Informationen von diesem Server abgerufen werden können. Sobald sie die Locator verfügt, müssen sie die Locator als nicht transparente Token behandeln.

Jeden Gopher-Locator verfügt über Attribute, die bestimmen den Typ der Datei oder der Server gefunden. Finden Sie unter [GetLocatorType](#getlocatortype) eine Liste der Gopher-Locator-Typen.

Eine Anwendung verwendet normalerweise den Locator für Aufrufe von [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) um eine bestimmte Information abzurufen.

Weitere Informationen finden Sie `CGopherLocator` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cgopherlocator"></a>  CGopherLocator::CGopherLocator

Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherLocator` Objekt.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Parameter

*ref*<br/>
Ein Verweis auf eine Konstante `CGopherLocator` Objekt.

### <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CGopherLocator` direkt. Rufen Sie stattdessen [CGopherConnection:: CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) erstellen, und geben Sie einen Zeiger auf die `CGopherLocator` Objekt.

##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType

Rufen Sie diese Memberfunktion um den Locatortyp erhalten.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Parameter

*dwRef*<br/>
Ein Verweis auf einen DWORD-Wert, der den Locatortyp erhält. Finden Sie unter **"Hinweise"** für eine Tabelle der locatortypen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Die möglichen Typen lauten wie folgt aus:

|Wert|Bedeutung|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Eine ASCII-Textdatei.|
|GOPHER_TYPE_DIRECTORY|Ein Verzeichnis mit den anderen Gopher-Optionen.|
|GOPHER_TYPE_CSO|Ein CSO Telefonbuch-Server.|
|GOPHER_TYPE_ERROR|Gibt einen Fehler.|
|GOPHER_TYPE_MAC_BINHEX|Einen Macintosh-Datei im BINHEX-Format.|
|GOPHER_TYPE_DOS_ARCHIVE|Eine DOS-Archivdatei.|
|GOPHER_TYPE_UNIX_UUENCODED|Eine UUENCODED-Datei.|
|GOPHER_TYPE_INDEX_SERVER|Ein Indexserver.|
|GOPHER_TYPE_TELNET|Ein Telnet-Server.|
|GOPHER_TYPE_BINARY|Eine Binärdatei.|
|GOPHER_TYPE_REDUNDANT|Eine doppelte Server. Die enthaltenen Informationen ist ein Duplikat des primären Servers. Der primäre Server ist dem letzten Verzeichniseintrag, der nicht über ein GOPHER_TYPE_REDUNDANT verfügt.|
|GOPHER_TYPE_TN3270|Ein TN3270-Server.|
|GOPHER_TYPE_GIF|Eine GIF-Grafikdatei.|
|GOPHER_TYPE_IMAGE|Eine Bilddatei.|
|GOPHER_TYPE_BITMAP|Eine Bitmapdatei.|
|GOPHER_TYPE_MOVIE|Eine Movie-Datei.|
|GOPHER_TYPE_SOUND|Eine Audiodatei.|
|GOPHER_TYPE_HTML|Ein HTML-Dokument.|
|GOPHER_TYPE_PDF|Eine PDF-Datei.|
|GOPHER_TYPE_CALENDAR|Eine Datei dar.|
|GOPHER_TYPE_INLINE|Eine Inlinedatei.|
|GOPHER_TYPE_UNKNOWN|Der Elementtyp ist unbekannt.|
|GOPHER_TYPE_ASK|Ein Ask + Element.|
|GOPHER_TYPE_GOPHER_PLUS|Eine Gopher-Element.|

##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR

Diese nützliche Typumwandlungsoperator bietet eine effiziente Methode für den Zugriff auf die Null-terminierte C-Zeichenfolge enthalten, die einem `CGopherLocator` Objekt.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeichenzeiger auf Daten von der Zeichenfolge.

### <a name="remarks"></a>Hinweise

Es werden keine Zeichen kopiert werden. nur ein Zeiger zurückgegeben.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)
