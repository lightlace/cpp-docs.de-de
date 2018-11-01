---
title: CGopherFile-Klasse
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: 9e5fbdcd14c0f988e894718f357d40e4b238c7c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658197"
---
# <a name="cgopherfile-class"></a>CGopherFile-Klasse

Stellt die Funktionalität bereit, um Dateien auf einem Gopherserver zu suchen und zu lesen.

> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und deren Member sind veraltet, da, nicht auf der Windows XP-Plattform funktionieren, während sie weiterhin auf frühere Plattformen funktionieren.

## <a name="syntax"></a>Syntax

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CGopherFile::CGopherFile](#cgopherfile)|Erstellt ein `CGopherFile`-Objekt.|

## <a name="remarks"></a>Hinweise

Gopher-Dienst ist nicht zulässig, Daten in einer Gopherdatei zu schreiben, da für diesen Dienst hauptsächlich als menügesteuerten-Schnittstelle für die Suche nach Informationen Funktionen. Die `CGopherFile` Memberfunktionen `Write`, `WriteString`, und `Flush` sind nicht für implementiert `CGopherFile`. Diese Funktionen aufrufen, auf eine `CGopherFile` -Objekts gibt ein [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Weitere Informationen finden Sie `CGopherFile` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile

Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherFile` Objekt.

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>Parameter

*hFile*<br/>
Ein Handle für eine HINTERNET-Datei.

*refLocator*<br/>
Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.

*pConnection*<br/>
Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.

*hSession*<br/>
Ein Handle für die aktuelle Internet-Sitzung.

*pstrLocator*<br/>
Ein Zeiger auf eine Zeichenfolge, die zum Suchen des Gopher-Server verwendet. Finden Sie unter [Gopher-Sitzungen](cgopherlocator-class.md) für Weitere Informationen über das Gopher-Locators.

*dwLocLen*<br/>
Ein DWORD, das mit der Anzahl der Bytes im *PstrLocator*.

*dwContext*<br/>
Ein Zeiger auf den Kontextbezeichner, der die zu öffnende Datei.

### <a name="remarks"></a>Hinweise

Sie müssen eine `CGopherFile` Objekt, das während einer Sitzung des Gopher Internet aus einer Datei gelesen.

Erstellen Sie nie eine `CGopherFile` direkt. Rufen Sie stattdessen [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) zum Öffnen einer Datei auf einem Gopherserver.

## <a name="see-also"></a>Siehe auch

[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)
