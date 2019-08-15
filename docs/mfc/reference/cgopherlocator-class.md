---
title: CGopherLocator-Klasse
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: 9ce95a712af6502bff2a2502582a7fa843bf9653
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506160"
---
# <a name="cgopherlocator-class"></a>CGopherLocator-Klasse

Ruft einen Gopher-"Serverlocatorpunkt" von einem Gopher-Server ab, bestimmt den Typ des Locators und macht den Serverlocatorpunkt für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)verfügbar.

> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind` undihreMembersindveraltet,daSienichtaufderWindowsXP-Plattformfunktionieren,aberSiefunktionierenweiterhinauf`CGopherLocator` früheren Plattformen.

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
|[CGopherLocator::GetLocatorType](#getlocatortype)|Analysiert einen Gopher-Serverlocatorpunkt und bestimmt seine Attribute.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CGopherLocator:: Operator LPCTSTR](#operator_lpctstr)|Greift direkt auf in einem `CGopherLocator` -Objekt gespeicherte Zeichen als Zeichenfolge im C-Format zu.|

## <a name="remarks"></a>Hinweise

Eine Anwendung muss den Serverlocatorpunkt eines Gopher-Servers abrufen, bevor Informationen von diesem Server abgerufen werden können. Sobald Sie den Serverlocatorpunkt hat, muss Sie den Serverlocatorpunkt als nicht transparentes Token behandeln.

Jeder Gopher-Serverlocatorpunkt verfügt über Attribute, die den Typ der gefundenen Datei oder des gefundenen Servers bestimmen. Eine Liste der Typen von Gopher-Locators finden Sie unter [getlocatortype](#getlocatortype) .

Eine Anwendung verwendet normalerweise den Serverlocatorpunkt für Aufrufe von [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) , um bestimmte Informationen abzurufen.

Weitere Informationen `CGopherLocator` zum Arbeiten mit den anderen MFC-Internet Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cgopherlocator"></a>CGopherLocator:: CGopherLocator

Diese Member-Funktion wird aufgerufen, um `CGopherLocator` ein-Objekt zu erstellen.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Parameter

*ref*<br/>
Ein Verweis auf ein konstantes `CGopherLocator` Objekt.

### <a name="remarks"></a>Hinweise

Sie erstellen niemals direkt `CGopherLocator` ein-Objekt. Rufen Sie stattdessen [CGopherConnection:: kreatelocator](../../mfc/reference/cgopherconnection-class.md#createlocator) auf, um einen Zeiger auf das `CGopherLocator` -Objekt zu erstellen und zurückzugeben.

##  <a name="getlocatortype"></a>CGopherLocator:: getlocatortype

Mit dieser Member-Funktion können Sie den Locatortyp abrufen.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Parameter

*dwRef*<br/>
Ein Verweis auf ein DWORD, das den Locatortyp empfängt. Siehe **Hinweise** für eine Tabelle der locatortypen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Folgende Typen sind möglich:

|Wert|Bedeutung|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Eine ASCII-Textdatei.|
|GOPHER_TYPE_DIRECTORY|Ein Verzeichnis mit zusätzlichen Gopher-Elementen.|
|GOPHER_TYPE_CSO|Einen CSO-Telefonbuch Server.|
|GOPHER_TYPE_ERROR|Gibt eine Fehlerbedingung an.|
|GOPHER_TYPE_MAC_BINHEX|Eine Macintosh-Datei im BinHex-Format.|
|GOPHER_TYPE_DOS_ARCHIVE|Eine DOS-Archivdatei.|
|GOPHER_TYPE_UNIX_UUENCODED|Eine uucodierte Datei.|
|GOPHER_TYPE_INDEX_SERVER|Ein Index Server.|
|GOPHER_TYPE_TELNET|Ein Telnet-Server.|
|GOPHER_TYPE_BINARY|Eine Binärdatei.|
|GOPHER_TYPE_REDUNDANT|Ein doppelter Server. Die in enthaltenen Informationen sind ein Duplikat des primären Servers. Der primäre Server ist der letzte Verzeichniseintrag, bei dem es sich nicht um einen GOPHER_TYPE_REDUNDANT-Typ handelt.|
|GOPHER_TYPE_TN3270|Ein TN3270-Server.|
|GOPHER_TYPE_GIF|Eine GIF-Grafikdatei.|
|GOPHER_TYPE_IMAGE|Eine Bilddatei.|
|GOPHER_TYPE_BITMAP|Eine Bitmapdatei.|
|GOPHER_TYPE_MOVIE|Eine Filmdatei.|
|GOPHER_TYPE_SOUND|Eine Audiodatei.|
|GOPHER_TYPE_HTML|Ein HTML-Dokument.|
|GOPHER_TYPE_PDF|Eine PDF-Datei.|
|GOPHER_TYPE_CALENDAR|Eine Kalenderdatei.|
|GOPHER_TYPE_INLINE|Eine Inline Datei.|
|GOPHER_TYPE_UNKNOWN|Der Elementtyp ist unbekannt.|
|GOPHER_TYPE_ASK|Ein "Ask +"-Element.|
|GOPHER_TYPE_GOPHER_PLUS|Ein Gopher +-Element.|

##  <a name="operator_lpctstr"></a>CGopherLocator:: Operator LPCTSTR

Dieser nützliche Umwandlungs Operator stellt eine effiziente Methode für den Zugriff auf die in einem `CGopherLocator` -Objekt enthaltene in NULL endend C-Zeichenfolge bereit.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeichen Zeiger auf die Daten der Zeichenfolge.

### <a name="remarks"></a>Hinweise

Es werden keine Zeichen kopiert. Es wird nur ein-Zeiger zurückgegeben.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)
