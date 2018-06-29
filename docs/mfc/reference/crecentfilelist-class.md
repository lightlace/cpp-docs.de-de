---
title: CRecentFileList Klasse | Microsoft Docs
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
ms.openlocfilehash: 8d1dc8b636d0c97bc220f9c7f0f1e1cd165369e0
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079015"
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
|[CRecentFileList::Add](#add)|Die Liste der zuletzt verwendeten Dateien hinzugefügt eine Datei.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|Stellt einen Anzeigenamen für die Menüanzeige im eine MRU-Dateinamen an.|  
|[CRecentFileList::GetSize](#getsize)|Ruft die Anzahl der Dateien in der Liste der zuletzt verwendeten Dateien ab.|  
|[CRecentFileList::ReadList](#readlist)|Liest die Liste der zuletzt verwendeten Dateien aus der Registrierung oder. INI-Datei.|  
|[CRecentFileList::Remove](#remove)|Entfernt eine Datei aus der Liste der zuletzt verwendeten Dateien.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|Aktualisiert die Anzeige im Menü von der Liste der zuletzt verwendeten Dateien.|  
|[CRecentFileList::WriteList](#writelist)|Schreibt die Liste der zuletzt verwendeten Dateien aus der Registrierung oder. INI-Datei.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecentFileList::operator]](#operator_at)|Gibt eine `CString` -Objekt an einer angegebenen Zeichenposition.|  
  
## <a name="remarks"></a>Hinweise  
 Dateien hinzugefügt oder aus der Liste der zuletzt verwendeten Dateien gelöscht werden können, die Dateiliste einlesen oder in die Registrierung geschrieben werden kann oder ein. INI-Datei, und klicken Sie im Menü Anzeigen der Liste der zuletzt verwendeten Dateien können aktualisiert werden.  
  
 Weitere Informationen zu MRU-Menüelemente finden Sie unter  
  
-   Knowledge Base-Artikel Q243751: So wird's gemacht: Hinzufügen von Befehlshandler für MRU-Menüelemente in MFC-Anwendung  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRecentFileList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="add"></a>  CRecentFileList::Add  
 Fügt eine Datei, die zuletzt verwendeten Dateiliste (MRU).  
  
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
 *lpszPathName*  
 Gibt die Pfadnamen der Liste hinzugefügt werden.  
  
 *lpszAppID*  
 Gibt die Anwendungsbenutzer-Modell-ID für die Anwendung an.  
  
 *pItem*  
 Gibt einen Zeiger auf die Shell-Element, das der Liste hinzugefügt werden.  
  
 *"plink"*  
 Gibt einen Zeiger auf die Shell-Link, um der Liste hinzugefügt werden.  
  
 *PIDL*  
 Gibt die Zonen für die Shellelement, das Ordner der zuletzt verwendeten Dokumente hinzugefügt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Der Dateiname wird an den Anfang der Liste der zuletzt verwendeten Objekte hinzugefügt werden. Wenn der Dateiname bereits in der MRU-Liste vorhanden ist, wird sie nach oben verschoben.  
  
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
 *nStart*  
 Offset für die Nummerierung in der Menüanzeige im der Dateiliste MRU (zuletzt verwendet).  
  
 *lpszSection*  
 Verweist auf den Namen des Abschnitts der Registrierung oder der Anwendungsverzeichnis. INI-Datei, in dem Liste der zuletzt verwendeten Dateien lesen und/oder geschrieben wird.  
  
 *lpszEntryFormat*  
 Verweist auf eine Formatzeichenfolge für die Namen der Einträge in der Registrierung oder der Anwendungsverzeichnis gespeichert verwendet werden soll. INI-Datei.  
  
 *nSize*  
 Maximale Anzahl von Dateien in der Liste der zuletzt verwendeten Dateien.  
  
 *nMaxDispLen*  
 Maximale Länge in Zeichen, für die Anzeige im Menü eines Dateinamens in der Liste der zuletzt verwendeten Dateien verfügbar.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatzeichenfolge verweist *LpszEntryFormat* "%d", die für das Ersetzen des Indexes jedes MRU-Elements verwendet werden dürfen. Wenn die Formatzeichenfolge wird beispielsweise `"file%d"` und dann die Einträge mit dem Namen `file0`, `file1`und so weiter.  
  
##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName  
 Ruft einen Anzeigenamen für eine Datei in der Liste der zuletzt verwendeten Dateien zur Verwendung in der Menüanzeige im der MRU-Liste ab.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *strName*  
 Vollständiger Pfad der Datei an, deren Name in der Liste der zuletzt verwendeten Dateien angezeigt werden.  
  
 *nIndex*  
 Nullbasierte Index der Datei in der Liste der zuletzt verwendeten Dateien.  
  
 *lpszCurDir*  
 Zeichenfolge, die das aktuelle Verzeichnis.  
  
 *nCurDir*  
 Die Länge der Zeichenfolge des aktuellen Verzeichnisses.  
  
 *bAtLeastName*  
 Wert ungleich NULL, gibt Sie an, dass der Basisname der Datei zurückgegeben werden sollen, selbst wenn die der maximale Anzeigelänge überschritten (als übergeben der *nMaxDispLen* Parameter an die `CRecentFileList` Konstruktor).  
  
### <a name="return-value"></a>Rückgabewert  
 **"False"** befindet sich kein Dateiname am angegebenen Index in der zuletzt verwendeten Dateiliste (MRU).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Datei im aktuellen Verzeichnis befindet, bleibt die Funktion das Verzeichnis der ausschalten. Wenn der Dateiname zu lang ist, werden das Verzeichnis und die Erweiterung entfernt. Wenn weiterhin der Dateiname zu lang ist, wird der angezeigte Name auf eine leere Zeichenfolge festgelegt, es sei denn, *bAtLeastName* ungleich NULL ist.  
  
##  <a name="getsize"></a>  CRecentFileList::GetSize  
 Ruft die Anzahl der Dateien in der Liste der zuletzt verwendeten Dateien ab.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Dateien in der aktuellen verwendet die zuletzt verwendeten Dateiliste (MRU).  
  
##  <a name="operator_at"></a>  CRecentFileList::operator]  
 Der überladene Feldindex ( `[]`) Operator gibt ein einzelnes `CString` angegeben durch den nullbasierten Index in *nIndex*.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der nullbasierte Index eine `CString` in einem Satz von `CString`s.  
  
##  <a name="readlist"></a>  CRecentFileList::ReadList  
 Liest den zuletzt verwendeten Dateiliste (MRU) aus der Registrierung oder der Anwendungsverzeichnis verwendeten. INI-Datei.  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>  CRecentFileList::Remove  
 Entfernt eine Datei aus der Liste der zuletzt verwendeten Dateien.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Nullbasierte Index der Datei aus der zuletzt verwendeten Dateiliste (MRU) entfernt werden soll.  
  
##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu  
 Aktualisiert die Anzeige im Menü von der Liste der zuletzt verwendeten Dateien.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 *nämlich pCmdUI*  
 Ein Zeiger auf die [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt für die zuletzt verwendeten Dateimenü Liste (MRU).  
  
##  <a name="writelist"></a>  CRecentFileList::WriteList  
 Schreibt die zuletzt verwendeten Dateiliste (MRU) in der Registrierung oder der Anwendungsverzeichnis. INI-Datei.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



