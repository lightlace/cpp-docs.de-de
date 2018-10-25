---
title: CRecentFileList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8f3d1b4be06caeacc86718eafed432979b0c59
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069424"
---
# <a name="crecentfilelist-class"></a>CRecentFileList-Klasse

Unterstützt die Verwendung der zuletzt verwendeten Dateiliste (MRU).

## <a name="syntax"></a>Syntax

```
class CRecentFileList
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Erstellt ein `CRecentFileList`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRecentFileList::Add](#add)|Die Liste der zuletzt verwendeten Dateien, eine Datei hinzugefügt.|
|[CRecentFileList::GetDisplayName](#getdisplayname)|Stellt einen Anzeigenamen für die Menüanzeige im eine MRU-Dateinamen an.|
|[CRecentFileList::GetSize](#getsize)|Ruft die Anzahl der Dateien in die Liste der zuletzt verwendeten Dateien ab.|
|[CRecentFileList::ReadList](#readlist)|Liest die Liste der zuletzt verwendeten Dateien aus der Registrierung oder. INI-Datei.|
|[CRecentFileList::Remove](#remove)|Entfernt eine Datei aus der Liste der zuletzt verwendeten Dateien.|
|[CRecentFileList::UpdateMenu](#updatemenu)|Aktualisiert die Anzeige im Menü, der Liste der zuletzt verwendeten Dateien.|
|[CRecentFileList::WriteList](#writelist)|Schreibt die Liste der zuletzt verwendeten Dateien aus der Registrierung oder. INI-Datei.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CRecentFileList::operator]](#operator_at)|Gibt eine `CString` Objekt an einer bestimmten Position.|

## <a name="remarks"></a>Hinweise

Dateien hinzugefügt oder aus der Liste der zuletzt verwendeten Dateien gelöscht werden können, die Dateiliste einlesen oder in die Registrierung geschrieben werden kann oder ein. INI-Datei, und klicken Sie im Menü, die Anzeige der Liste der MRU-Datei kann aktualisiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CRecentFileList`

## <a name="requirements"></a>Anforderungen

**Header:** afxadv.h

##  <a name="add"></a>  CRecentFileList::Add

Die Liste der zuletzt verwendeten (MRU)-Dateien wird eine Datei hinzugefügt.

```
virtual void Add(LPCTSTR lpszPathName);

virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```

### <a name="parameters"></a>Parameter

*lpszPathName*<br/>
Gibt die Pfadnamen der Liste hinzugefügt werden.

*lpszAppID*<br/>
Gibt die Anwendungsbenutzer-Modell-ID für die Anwendung an.

*pItem*<br/>
Gibt einen Zeiger auf die Shell-Element, das der Liste hinzugefügt werden.

*Sie plink herunter*<br/>
Gibt einen Zeiger auf die Shell-Link zu der Liste hinzugefügt werden.

*PIDL*<br/>
Gibt an, die Zonen für die Shellelement, das die aktuelle Dokumentenordner hinzugefügt werden soll.

### <a name="remarks"></a>Hinweise

Der Dateiname wird an den Anfang der MRU-Liste hinzugefügt. Wenn der Dateiname der MRU-Liste bereits vorhanden ist, wird es an den Anfang verschoben werden.

##  <a name="crecentfilelist"></a>  CRecentFileList::CRecentFileList

Erstellt ein `CRecentFileList`-Objekt.

```
CRecentFileList(
    UINT nStart,
    LPCTSTR lpszSection,
    LPCTSTR lpszEntryFormat,
    int nSize,
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```

### <a name="parameters"></a>Parameter

*nmit*<br/>
Offset für die Nummerierung in der Menüanzeige im der Dateiliste zuletzt verwendeten Objekte (die zuletzt verwendet).

*lpszSection*<br/>
Zeigt auf den Namen des Abschnitts der Registrierung oder der Anwendung. INI-Datei, in dem Liste der zuletzt verwendeten Dateien gelesen und/oder geschrieben wird.

*lpszEntryFormat*<br/>
Verweist auf eine Zeichenfolge, die für die Namen von den Einträgen in der Registrierung oder der Anwendung verwendet werden. INI-Datei.

*nSize*<br/>
Maximale Anzahl von Dateien in der Liste der MRU-Menü Datei.

*nMaxDispLen*<br/>
Maximale Länge in Zeichen, für die Anzeige im Menü eines Dateinamens in der Liste der MRU-Datei verfügbar.

### <a name="remarks"></a>Hinweise

Die Formatzeichenfolge verweist *LpszEntryFormat* muss enthalten "%d", die zum Ersetzen des Indexes jedes MRU-Elements verwendet wird. Wenn die Formatzeichenfolge lautet z. B. `"file%d"` und klicken Sie dann die Einträge mit dem Namen `file0`, `file1`und so weiter.

##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName

Ruft einen Anzeigenamen für eine Datei in Dateiliste für den MRU-Menü für die Verwendung in der Menüanzeige im der MRU-Liste ab.

```
virtual BOOL GetDisplayName(
    CString& strName,
    int nIndex,
    LPCTSTR lpszCurDir,
    int nCurDir,
    BOOL bAtLeastName = TRUE) const;
```

### <a name="parameters"></a>Parameter

*strName*<br/>
Vollständiger Pfad der Datei an, deren Name in der Liste der zuletzt verwendeten Dateien angezeigt werden.

*nIndex*<br/>
Nullbasierte Index der Datei in die Liste der zuletzt verwendeten Dateien.

*lpszCurDir*<br/>
Zeichenfolge, die das aktuelle Verzeichnis enthält.

*nCurDir*<br/>
Länge der Zeichenfolge des aktuellen Verzeichnisses.

*bAtLeastName*<br/>
Wert ungleich NULL, gibt Sie an, dass der Basisname der Datei zurückgegeben werden sollen, auch wenn die der maximale Anzeigelänge überschritten (als übergeben die *nMaxDispLen* Parameter, um die `CRecentFileList` Konstruktor).

### <a name="return-value"></a>Rückgabewert

**"False"** liegt kein Dateiname am angegebenen Index in der Liste der zuletzt verwendeten (MRU)-Datei.

### <a name="remarks"></a>Hinweise

Wenn die Datei im aktuellen Verzeichnis ist, bleibt die Funktion das Verzeichnis deaktiviert die Anzeige. Wenn der Dateiname zu lang ist, werden das Verzeichnis und die Erweiterung entfernt. Wenn weiterhin der Dateiname zu lang ist, wird der Anzeigename auf eine leere Zeichenfolge festgelegt, es sei denn, *bAtLeastName* ungleich NULL ist.

##  <a name="getsize"></a>  CRecentFileList::GetSize

Ruft die Anzahl der Dateien in die Liste der zuletzt verwendeten Dateien ab.

```
int GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Zuletzt verwendeten die Anzahl der Dateien in der aktuellen Dateiliste (MRU).

##  <a name="operator_at"></a>  CRecentFileList::operator]

Der überladene Feldindex (`[]`) Operator gibt einen einzelnen `CString` angegeben wird, über den nullbasierten Index in *nIndex*.

```
CString& operator[ ](int nindex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Nullbasierter Index, der eine `CString` in einem Satz von `CString`s.

##  <a name="readlist"></a>  CRecentFileList::ReadList

Liest die zuletzt verwendeten Dateiliste (MRU), aus der Registrierung oder der Anwendung. INI-Datei.

```
virtual void ReadList();
```

##  <a name="remove"></a>  CRecentFileList::Remove

Entfernt eine Datei aus der Liste der zuletzt verwendeten Dateien.

```
virtual void Remove(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Nullbasierte Index der Datei, die aus der Liste der zuletzt verwendeten (MRU)-Datei entfernt werden.

##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu

Aktualisiert die Anzeige im Menü, der Liste der zuletzt verwendeten Dateien.

```
virtual void UpdateMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf die [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekt für die zuletzt verwendeten (MRU)-Datei Liste-Menü.

##  <a name="writelist"></a>  CRecentFileList::WriteList

Schreibt die zuletzt verwendeten Dateiliste (MRU) in der Registrierung oder der Anwendung. INI-Datei.

```
virtual void WriteList();
```

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

