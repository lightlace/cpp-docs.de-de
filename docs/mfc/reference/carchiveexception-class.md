---
title: CArchiveException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
ms.openlocfilehash: 731735bccf9225e67d82b1fe90336c92a630b368
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391308"
---
# <a name="carchiveexception-class"></a>CArchiveException-Klasse

Stellt eine serialisierungsausnahmebedingung

## <a name="syntax"></a>Syntax

```
class CArchiveException : public CException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CArchiveException::CArchiveException](#carchiveexception)|Erstellt ein `CArchiveException`-Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CArchiveException::m_cause](#m_cause)|Gibt die Ursache der Ausnahme.|
|[CArchiveException::m_strFileName](#m_strfilename)|Gibt den Namen der Datei für diese Ausnahmebedingung.|

## <a name="remarks"></a>Hinweise

Die `CArchiveException` Klasse enthält einen öffentlichen Datenmember, der die Ursache der Ausnahme angibt.

`CArchiveException` Objekte werden erstellt und ausgelöst in [CArchive](../../mfc/reference/carchive-class.md) Memberfunktionen. Sie können auf zugreifen, diese Objekte innerhalb des Bereichs einer **CATCH** Ausdruck. Der Ursachencode ist unabhängig von dem Betriebssystem. Weitere Informationen zur ausnahmeverarbeitung finden Sie unter [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException

Erstellt eine `CArchiveException` Objekt, das Speichern des Werts *dazu führen, dass* im-Objekt.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parameter

*cause*<br/>
Ein enumerierter Typ-Variable, die den Grund für die Ausnahme angibt. Eine Liste der Enumeratoren, finden Sie unter den [M_cause](#m_cause) -Datenmember.

*lpszArchiveName*<br/>
Verweist auf eine Zeichenfolge, die mit dem Namen des der `CArchive` Objekt, die die Ausnahme verursacht.

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CArchiveException` Objekt auf dem Heap und selbst auslösen, oder lassen Sie die globale Funktion [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) für Sie behandeln.

Verwenden Sie diesen Konstruktor nicht direkt. Rufen Sie stattdessen die globale Funktion `AfxThrowArchiveException`.

##  <a name="m_cause"></a>  CArchiveException::m_cause

Gibt an, die Ursache der Ausnahme.

```
int m_cause;
```

### <a name="remarks"></a>Hinweise

Dieses Datenelement ist eine öffentliche Variable des Typs **Int**. Die Werte definieren, indem eine `CArchiveException` Enumerationstyp. Die Enumeratoren und ihre Bedeutungen lauten wie folgt:

- `CArchiveException::none` Kein Fehler aufgetreten ist.

- `CArchiveException::genericException` Unbekannter Fehler.

- `CArchiveException::readOnly` Versucht, das Schreiben in ein Archiv für das Laden von geöffnet.

- `CArchiveException::endOfFile` Erreicht der Dateiende beim Lesen eines Objekts.

- `CArchiveException::writeOnly` Versucht, das Lesen eines Archivs, das zum Speichern von geöffnet.

- `CArchiveException::badIndex` Ungültiges Dateiformat.

- `CArchiveException::badClass` Versucht, ein Objekt in ein Objekt des falschen Typs zu lesen.

- `CArchiveException::badSchema` Versucht, ein Objekt mit einer anderen Version der Klasse zu lesen.

    > [!NOTE]
    >  Diese `CArchiveException`-Ursachenenumeratoren unterscheiden sich von den `CFileException`-Ursachenenumeratoren.

    > [!NOTE]
    > `CArchiveException::generic` ist veraltet. Verwenden Sie stattdessen `genericException`. Wenn **generische** ist in einer Anwendung verwendet und erstellt mit/CLR, fallen Syntaxfehler, die nicht leicht entschlüsselt werden.

##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName

Gibt den Namen der Datei für diese Ausnahmebedingung.

```
CString m_strFileName;
```

## <a name="see-also"></a>Siehe auch

[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CArchive-Klasse](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)
