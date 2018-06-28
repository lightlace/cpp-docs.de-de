---
title: CJumpList Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
dev_langs:
- C++
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc609fac36ccdbb9f84ce8f2b9b7c0ccfc5ccd3f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038502"
---
# <a name="cjumplist-class"></a>CJumpList-Klasse
Ein `CJumpList` ist die Liste der Verknüpfungen, die angezeigt werden, wenn Sie mit der rechten Maustaste auf ein Symbol in der Taskleiste klicken.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|Erstellt ein `CJumpList`-Objekt.|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|Zerstört ein `CJumpList`-Objekt.|  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|Eine Liste erstellen-Transaktion abbricht, ohne dass.|  
|[CJumpList::AddDestination](#adddestination)|Überladen. Ziel hinzugefügt der Liste.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|Fügt eine Kategorie bezeichnet der Liste an.|  
|[CJumpList::AddTask](#addtask)|Überladen. Die kanonische Aufgaben Kategorie hinzugefügt Elemente.|  
|[CJumpList::AddTasks](#addtasks)|Die kanonische Aufgaben Kategorie hinzugefügt Elemente.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Fügt ein Trennzeichen zwischen den Aufgaben hinzu.|  
|[CJumpList::ClearAll](#clearall)|Entfernt alle Aufgaben und Ziele, die mit der aktuellen Instanz von hinzugefügt wurden `CJumpList` bisher.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Entfernt alle Ziele, die mit der aktuellen Instanz von hinzugefügt wurden `CJumpList` bisher.|  
|[CJumpList::CommitList](#commitlist)|Beendet eine Liste erstellen-Transaktion und führt einen Commit für die gemeldeten Liste in den zugeordneten Speicher (die Registrierung in diesem Fall).|  
|[CJumpList::GetDestinationList](#getdestinationlist)|Ruft einen Schnittstellenzeiger auf Zielliste ab.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|Ruft die maximale Anzahl von Elementen, einschließlich der kategorienheader, die in der aufrufenden Anwendung Ziel im Menü angezeigt werden können.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|Gibt ein Array von Elementen, die darstellen, entfernt die Ziele.|  
|[CJumpList::InitializeList](#initializelist)|Startet eine Transaktion Liste erstellen.|  
|[CJumpList::SetAppID](#setappid)|Legt die Anwendungsbenutzer-Modell-ID für die Liste, die erstellt werden.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>  CJumpList:: ~ CJumpList  
 Zerstört ein `CJumpList`-Objekt.  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>  CJumpList::AbortList  
 Eine Liste erstellen-Transaktion abbricht, ohne dass.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufrufen dieser Methode hat dieselbe Wirkung wie das Zerstören von `CJumpList` ohne Aufruf `CommitList`.  
  
##  <a name="adddestination"></a>  CJumpList::AddDestination  
 Ziel hinzugefügt der Liste.  
  
```  
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,  
    LPCTSTR strDestinationPath);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellItem* pShellItem);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>Parameter  
 *lpcszCategoryName*  
 Gibt an, einen Kategorienamen ein. Wenn die angegebene Kategorie nicht vorhanden ist, wird sie erstellt.  
  
 *strDestinationPath*  
 Gibt einen Pfad zur Zieldatei.  
  
 *strCategoryName*  
 Gibt an, einen Kategorienamen ein. Wenn die angegebene Kategorie nicht vorhanden ist, wird sie erstellt.  
  
 *pShellItem*  
 Gibt ein Shell-Element, das das hinzuzufügende Ziel darstellt.  
  
 *pShellLink*  
 Gibt eine Shell-Verknüpfung, die das hinzuzufügende Ziel darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Instanz von `CJumpList` intern akkumuliert hinzugefügten Ziele aus, und klicken Sie dann ein Commit ausgeführt, im `CommitList`.  
  
##  <a name="addknowncategory"></a>  CJumpList::AddKnownCategory  
 Fügt eine Kategorie bezeichnet der Liste an.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>Parameter  
 *category*  
 Gibt einen bekannten Kategorietyp. Kann es sich um `KDC_RECENT`, oder `KDC_KNOWN`.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Kategorien bekanntermaßen häufig und zuletzt Kategorien, die wir automatisch für jede Anwendung berechnet, die nutzt `SHAddToRecentDocs` (oder indirekt verwendet, wie die Befehlsshell in der Anwendung Auftrag in einigen Szenarien aufgerufen wird).  
  
##  <a name="addtask"></a>  CJumpList::AddTask  
 Die kanonische Aufgaben Kategorie hinzugefügt Elemente.  
  
```  
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,  
    LPCTSTR strCommandLineArgs,  
    LPCTSTR strTitle,  
    LPCTSTR strIconLocation,  
    int iIconIndex);  
  
BOOL AddTask(IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>Parameter  
 *strTargetExecutablePath*  
 Gibt den Zielpfad für den Task an.  
  
 *strCommandLineArgs*  
 Gibt die Befehlszeilenargumente der ausführbaren Datei von StrTargetExecutablePath angegeben.  
  
 *strTitle*  
 Der Name der Aufgabe, die in der Zielliste angezeigt werden.  
  
 *strIconLocation*  
 Der Speicherort des Symbols, die in der Zielliste zusammen mit den Titel angezeigt werden.  
  
 *iIconIndex*  
 Symbol "-Index.  
  
 *pShellLink*  
 Shell-Link, der eine Aufgabe hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Instanz von `CJumpList` akkumuliert angegebene Aufgaben und der Zielliste während hinzugefügt `CommitList`. Task-Elemente in einer Kategorie am unteren Rand der Anwendungsmenü Ziel angezeigt. Diese Kategorie hat Vorrang vor allen anderen Kategorien, wenn sie in der Benutzeroberfläche aufgefüllt wird.  
  
##  <a name="addtasks"></a>  CJumpList::AddTasks  
 Die kanonische Aufgaben Kategorie hinzugefügt Elemente.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>Parameter  
 *pObjectCollection*  
 Eine Auflistung von Aufgaben hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Instanz von CJumpList akkumuliert angegebene Aufgaben und der Zielliste während hinzugefügt `CommitList`. Task-Elemente in einer Kategorie am unteren Rand der Anwendungsmenü Ziel angezeigt. Diese Kategorie hat Vorrang vor allen anderen Kategorien, wenn sie in der Benutzeroberfläche aufgefüllt wird.  
  
##  <a name="addtaskseparator"></a>  CJumpList::AddTaskSeparator  
 Fügt ein Trennzeichen zwischen den Aufgaben hinzu.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, 0, wenn er nicht ist.  
  
##  <a name="cjumplist"></a>  CJumpList::CJumpList  
 Erstellt ein `CJumpList`-Objekt.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutoCommit*  
 Wenn dieser Parameter auf "false" ist die Liste nicht automatisch im Destruktor übertragen wurde.  
  
##  <a name="clearall"></a>  CJumpList::ClearAll  
 Entfernt alle Aufgaben und Ziele, die mit der aktuellen Instanz von hinzugefügt wurden `CJumpList` bisher.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht und alle Daten und internen Schnittstellen frei.  
  
##  <a name="clearalldestinations"></a>  CJumpList::ClearAllDestinations  
 Entfernt alle Ziele, die mit der aktuellen Instanz von CJumpList bisher hinzugefügt wurden.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, wenn Sie alle Ziele entfernen, die bisher in der aktuellen Sitzung, beim Erstellen von Ziel-Liste hinzugefügt wurden, und andere Ziele wieder hinzufügen möchten. Wenn das interne `ICustomDestinationList` wurde initialisiert, es bleibt aktiv.  
  
##  <a name="commitlist"></a>  CJumpList::CommitList  
 Beendet eine Liste erstellen-Transaktion und führt einen Commit für die gemeldeten Liste in den zugeordneten Speicher (in diesem Fall die Registrierung).  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Das Commit ist atomarisch. Wenn dies fehlschlägt, wird ein Fehler zurückgegeben werden.  Wenn `CommitList` aufgerufen wird, wird die aktuelle Liste der entfernten Elementen werden bereinigt. Beim Aufrufen dieser Methode setzt das Objekt, damit sie nicht über eine aktive Transaktion für die Liste-Erstellung verfügt. Zum Aktualisieren der Liste `BeginList` erneut aufgerufen werden muss.  
  
##  <a name="getdestinationlist"></a>  CJumpList::GetDestinationList  
 Ruft einen Schnittstellenzeiger auf Zielliste ab.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Sprungliste nicht initialisiert wurde, oder ein Commit ausgeführt oder wurde abgebrochen, wird der zurückgegebene Wert werden `NULL`.  
  
##  <a name="getmaxslots"></a>  CJumpList::GetMaxSlots  
 Ruft die maximale Anzahl von Elementen, einschließlich der kategorienheader, die in der aufrufenden Anwendung Ziel im Menü angezeigt werden können.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Clientanwendungen melden möglicherweise nur eine Reihe von Elementen und kategorienheader, die bis zu diesem Wert kombiniert. Wenn Aufrufe von `AppendCategory`, `AppendKnownCategory`, oder `AddUserTasks` diese Anzahl überschreiten, wird Fehler zurückgegeben.  
  
##  <a name="getremoveditems"></a>  CJumpList::GetRemovedItems  
 Gibt ein Array von Elementen, die darstellen, entfernt die Ziele.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die entfernte Ziele werden während der Initialisierung der Sprungliste abgerufen. Zur Erstellung eine neuen Zielliste voraussichtlich Anwendungen entfernt Zieleliste, deaktivieren die Überwachungsdaten für jedes Element der Liste entfernten-Enumerator zurückgegebenes zuerst zu verarbeiten. Wenn eine Anwendung versucht, ein Element bereitstellen, die gerade, in der Transaktion, die das aktuelle aufrufen entfernt wurde, um `BeginList` gestartet, der Aufruf der Methode, die dieses Element erneut hinzugefügt schlägt fehlt, um sicherzustellen, dass die Anwendungen die Liste entfernte ressourcenbezogene sind.  
  
##  <a name="initializelist"></a>  CJumpList::InitializeList  
 Startet eine Transaktion Liste erstellen.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Methode explizit aufrufen, es sei denn, Sie einen Zeiger auf abzurufen möchten `ICustomDestinationList` mit `GetDestinationList`, die Anzahl der Steckplätze verfügbar, die mit `GetMaxSlots`, oder eine Liste von entfernten Elementen mit `GetRemovedItems`.  
  
##  <a name="setappid"></a>  CJumpList::SetAppID  
 Legt die Anwendungsbenutzer-Modell-ID für die Liste, die erstellt werden.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>Parameter  
 *strAppID*  
 Eine Zeichenfolge, die das Anwendungsmodell für die Benutzer-ID angibt  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
