---
title: Klasse CRecentFileList | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecentFileList
dev_langs:
- C++
helpviewer_keywords:
- files [C++], most recently used
- MRU files
- CRecentFileList class
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5d18daee2e4d809c750ae4654d731888df1db39e
ms.lasthandoff: 02/24/2017

---
# <a name="crecentfilelist-class"></a>CRecentFileList-Klasse
Unterstützt die Verwendung der zuletzt verwendeten Dateiliste (MRU).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Erstellt ein `CRecentFileList`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|Fügt eine Datei der Liste der zuletzt verwendeten Dateien.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|Stellt einen Anzeigenamen für die Anzeige des Menüs eine MRU-Dateinamen an.|  
|[CRecentFileList::GetSize](#getsize)|Ruft die Anzahl der Dateien in der Liste der zuletzt verwendeten Dateien ab.|  
|[CRecentFileList::ReadList](#readlist)|Die Liste der zuletzt verwendeten Dateien aus der Registrierung liest oder. INI-Datei.|  
|[CRecentFileList::Remove](#remove)|Entfernt eine Datei aus der Liste der zuletzt verwendeten Dateien.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|Aktualisiert die Anzeige im Menü von der Liste der zuletzt verwendeten Dateien.|  
|[CRecentFileList::WriteList](#writelist)|Die Liste der zuletzt verwendeten Dateien aus der Registrierung schreibt oder. INI-Datei.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecentFileList::operator]](#operator_at)|Gibt ein `CString` -Objekt an einer angegebenen Zeichenposition.|  
  
## <a name="remarks"></a>Hinweise  
 Dateien können hinzugefügt oder aus der Liste der zuletzt verwendeten Dateien gelöscht werden, die Dateiliste auslesen oder in die Registrierung geschrieben werden kann oder ein. INI-Datei, und klicken Sie im Menü Anzeigen der Liste der zuletzt verwendeten Dateien können aktualisiert werden.  
  
 Weitere Informationen zum zuletzt verwendeten Elemente finden Sie unter  
  
-   Knowledge Base-Artikel Q243751: So wird's gemacht: Hinzufügen von Befehlshandler für MRU-Menüelemente in MFC-Anwendung  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRecentFileList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="a-nameadda--crecentfilelistadd"></a><a name="add"></a>CRecentFileList::Add  
 Fügt eine Datei zur zuletzt verwendeten Dateiliste (MRU).  
  
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
 `lpszPathName`  
 Gibt die Pfadnamen der Liste hinzugefügt werden.  
  
 `lpszAppID`  
 Gibt Benutzer Modell-ID für die Anwendung an.  
  
 `pItem`  
 Gibt einen Zeiger auf die Shell-Element, das der Liste hinzugefügt werden.  
  
 `pLink`  
 Gibt einen Zeiger auf die Shell-Link zu der Liste hinzugefügt werden.  
  
 `pidl`  
 Gibt die Zonen für die Shellelement, das Ordner der zuletzt verwendeten Dokumente hinzugefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Dateiname wird an den Anfang der Liste der zuletzt verwendeten hinzugefügt. Wenn Sie der Dateinamen in der MRU-Liste bereits vorhanden ist, wird es an den Anfang verschoben werden.  
  
##  <a name="a-namecrecentfilelista--crecentfilelistcrecentfilelist"></a><a name="crecentfilelist"></a>CRecentFileList::CRecentFileList  
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
 `nStart`  
 Offset für die Nummerierung in der Menüanzeige im der Dateiliste MRU (zuletzt verwendet).  
  
 `lpszSection`  
 Zeigt den Namen des Abschnitts der Registrierung oder der Anwendungsverzeichnis. INI-Datei, in die Liste der zuletzt verwendeten Dateien gelesen und/oder geschrieben wird.  
  
 `lpszEntryFormat`  
 Zeigt auf eine Zeichenfolge für die Namen von den Einträgen in der Registrierung oder der Anwendungsverzeichnis verwendet werden soll. INI-Datei.  
  
 `nSize`  
 Maximale Anzahl der Dateien in der Liste der zuletzt verwendeten Dateien.  
  
 `nMaxDispLen`  
 Maximale Länge in Zeichen für die Anzeige im Menü des Dateinamens in der Liste der zuletzt verwendeten Dateien verfügbar.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatzeichenfolge verweist `lpszEntryFormat` sollte '%d', das verwendet wird, für das Ersetzen des Indexes jedes Elements MRU enthalten. Wenn die Formatzeichenfolge beispielsweise `"file%d"` und dann die Einträge mit dem Namen `file0`, `file1`und so weiter.  
  
##  <a name="a-namegetdisplaynamea--crecentfilelistgetdisplayname"></a><a name="getdisplayname"></a>CRecentFileList::GetDisplayName  
 Ruft einen Anzeigenamen für eine Datei in der Liste zuletzt für die Anzeige im Menü der MRU-Liste.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strName`  
 Vollständiger Pfad der Datei an, deren Name in der Liste der zuletzt verwendeten Dateien angezeigt werden.  
  
 `nIndex`  
 Nullbasierte Index der Datei in der Liste der zuletzt verwendeten Dateien.  
  
 *lpszCurDir*  
 Zeichenfolge, die das aktuelle Verzeichnis.  
  
 *nCurDir*  
 Länge der Zeichenfolge des aktuellen Verzeichnisses.  
  
 `bAtLeastName`  
 Ein Wert ungleich NULL, der Namen der Datei zurückgegeben werden sollen, selbst wenn sie die angezeigte maximale Länge überschreitet angibt (übergeben als die `nMaxDispLen` Parameter, um die `CRecentFileList` Konstruktor).  
  
### <a name="return-value"></a>Rückgabewert  
 **FALSE** befindet sich kein Dateiname am angegebenen Index in der zuletzt verwendeten Dateiliste (MRU).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Datei im aktuellen Verzeichnis ist, bleibt die Funktion das Verzeichnis die Anzeige. Wenn der Dateiname zu lang ist, werden das Verzeichnis und die Erweiterung entfernt. Wenn immer noch der Dateiname zu lang ist, wird der Anzeigename auf eine leere Zeichenfolge festgelegt, es sei denn, `bAtLeastName` ungleich NULL ist.  
  
##  <a name="a-namegetsizea--crecentfilelistgetsize"></a><a name="getsize"></a>CRecentFileList::GetSize  
 Ruft die Anzahl der Dateien in der Liste der zuletzt verwendeten Dateien ab.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Dateien in der aktuellen werden zuletzt verwendeten Dateiliste (MRU).  
  
##  <a name="a-nameoperatorata--crecentfilelistoperator--"></a><a name="operator_at"></a>CRecentFileList::operator]  
 Der überladene Index ( `[]`) Operator gibt einen Single- `CString` der nullbasierte Index im angegebenen `nIndex`.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index einer `CString` in einem Satz von `CString`s.  
  
##  <a name="a-namereadlista--crecentfilelistreadlist"></a><a name="readlist"></a>CRecentFileList::ReadList  
 Liest die zuletzt verwendeten Dateiliste (MRU), aus der Registrierung oder der Anwendungsverzeichnis. INI-Datei.  
  
```  
virtual void ReadList();
```  
  
##  <a name="a-nameremovea--crecentfilelistremove"></a><a name="remove"></a>CRecentFileList::Remove  
 Entfernt eine Datei aus der Liste der zuletzt verwendeten Dateien.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index der Datei aus der zuletzt verwendeten Dateiliste (MRU) entfernt werden soll.  
  
##  <a name="a-nameupdatemenua--crecentfilelistupdatemenu"></a><a name="updatemenu"></a>CRecentFileList::UpdateMenu  
 Aktualisiert die Anzeige im Menü von der Liste der zuletzt verwendeten Dateien.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf die [CCmdUI](../../mfc/reference/ccmdui-class.md) Objekt für die zuletzt verwendeten Dateimenü Liste (MRU).  
  
##  <a name="a-namewritelista--crecentfilelistwritelist"></a><a name="writelist"></a>CRecentFileList::WriteList  
 Schreibt die zuletzt verwendeten Dateiliste (MRU) in der Registrierung oder der Anwendungsverzeichnis. INI-Datei.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




