---
title: Klasse CJumpList | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CJumpList class
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b3662bd00f7c757df3a77f5920c48389bbd749fb
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cjumplist-class"></a>CJumpList-Klasse
Ein `CJumpList` ist die Liste der Tastenkombinationen angezeigt wird, wenn Sie mit der rechten Maustaste auf ein Symbol in der Taskleiste klicken.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|Erstellt ein `CJumpList`-Objekt.|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|Zerstört ein `CJumpList`-Objekt.|  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|Eine Liste erstellen-Transaktion abbricht, ohne zu übernehmen.|  
|[CJumpList::AddDestination](#adddestination)|Überladen. Ziel hinzugefügt der Liste.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|Fügt eine Kategorie bezeichnet der.|  
|[CJumpList::AddTask](#addtask)|Überladen. Die kanonische Aufgaben Kategorie hinzugefügt Elemente.|  
|[CJumpList::AddTasks](#addtasks)|Die kanonische Aufgaben Kategorie hinzugefügt Elemente.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Fügt ein Trennzeichen zwischen Aufgaben.|  
|[CJumpList::ClearAll](#clearall)|Entfernt alle Aufgaben und Ziele, die der aktuellen Instanz der hinzugefügten `CJumpList` bisher.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Entfernt alle Ziele, die mit der aktuellen Instanz von hinzugefügt wurden `CJumpList` bisher.|  
|[CJumpList::CommitList](#commitlist)|Beendet eine Liste erstellen-Transaktion und führt einen Commit für die gemeldeten Liste in den zugehörigen Speicher (die Registrierung in diesem Fall).|  
|[CJumpList::GetDestinationList](#getdestinationlist)|Ruft einen Schnittstellenzeiger auf Zielliste ab.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|Ruft die maximale Anzahl von Elementen, einschließlich der Kategorie-Header, die in der aufrufenden Anwendung Ziel im Menü angezeigt werden können.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|Gibt ein Array von Elementen, die darstellen entfernt Ziele.|  
|[CJumpList::InitializeList](#initializelist)|Beginnt eine Transaktion Liste erstellen.|  
|[CJumpList::SetAppID](#setappid)|Legt die Benutzer-Modell-ID für die Liste, die erstellt wird.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>CJumpList:: ~ CJumpList  
 Zerstört ein `CJumpList`-Objekt.  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>CJumpList::AbortList  
 Eine Liste erstellen-Transaktion abbricht, ohne zu übernehmen.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Methode hat dieselbe Wirkung wie das Zerstören `CJumpList` ohne Aufruf von `CommitList`.  
  
##  <a name="adddestination"></a>CJumpList::AddDestination  
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
 `lpcszCategoryName`  
 Gibt den Kategorienamen. Wenn die angegebene Kategorie nicht vorhanden ist, wird sie erstellt.  
  
 `strDestinationPath`  
 Gibt einen Pfad zur Zieldatei.  
  
 `strCategoryName`  
 Gibt den Kategorienamen. Wenn die angegebene Kategorie nicht vorhanden ist, wird sie erstellt.  
  
 `pShellItem`  
 Gibt ein Shell-Element, das das hinzuzufügende Ziel darstellt.  
  
 `pShellLink`  
 Gibt eine Shell-Verknüpfung, die das hinzuzufügende Ziel darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Instanz von `CJumpList` intern akkumuliert hinzugefügten Ziele und dann ein Commit in `CommitList`.  
  
##  <a name="addknowncategory"></a>CJumpList::AddKnownCategory  
 Fügt eine Kategorie bezeichnet der.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>Parameter  
 `category`  
 Gibt einen bekannten Typ an. Kann entweder `KDC_RECENT`, oder `KDC_KNOWN`.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Kategorien bekanntermaßen häufig und zuletzt Kategorien, die wir automatisch für jede Anwendung berechnet, die nutzt `SHAddToRecentDocs` (oder indirekt verwendet, wie die Shell im Auftrag von der Anwendung in einigen Szenarien aufgerufen wird).  
  
##  <a name="addtask"></a>CJumpList::AddTask  
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
 `strTargetExecutablePath`  
 Gibt den Zielpfad für den Task an.  
  
 `strCommandLineArgs`  
 Gibt die Befehlszeilenargumente der ausführbaren Datei von StrTargetExecutablePath angegeben.  
  
 `strTitle`  
 Der Name der Aufgabe, die in der Liste Ziel angezeigt werden.  
  
 `strIconLocation`  
 Die Position des Symbols, die in der Liste Ziel zusammen mit dem Titel angezeigt werden.  
  
 `iIconIndex`  
 Symbolindex.  
  
 `pShellLink`  
 Shell-Link, der eine Aufgabe hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Instanz von `CJumpList` sammelt die angegebenen Vorgänge und die Zielliste während hinzugefügt `CommitList`. Task-Elemente in einer Kategorie am unteren Rand der Anwendung Ziel im Menü angezeigt. Diese Kategorie hat Vorrang vor allen anderen Kategorien, wenn sie in der Benutzeroberfläche aufgefüllt wird.  
  
##  <a name="addtasks"></a>CJumpList::AddTasks  
 Die kanonische Aufgaben Kategorie hinzugefügt Elemente.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>Parameter  
 `pObjectCollection`  
 Eine Auflistung von Aufgaben hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die Instanz von CJumpList sammelt die angegebenen Vorgänge und während der Empfängerliste hinzugefügt `CommitList`. Task-Elemente in einer Kategorie am unteren Rand der Anwendung Ziel im Menü angezeigt. Diese Kategorie hat Vorrang vor allen anderen Kategorien, wenn sie in der Benutzeroberfläche aufgefüllt wird.  
  
##  <a name="addtaskseparator"></a>CJumpList::AddTaskSeparator  
 Fügt ein Trennzeichen zwischen Aufgaben.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei erfolgreicher Ausführung, 0, wenn er nicht ist.  
  
##  <a name="cjumplist"></a>CJumpList::CJumpList  
 Erstellt ein `CJumpList`-Objekt.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutoCommit`  
 Wenn dieser Parameter auf "false" ist die Liste nicht automatisch im Destruktor übertragen wurde.  
  
##  <a name="clearall"></a>CJumpList::ClearAll  
 Entfernt alle Aufgaben und Ziele, die der aktuellen Instanz der hinzugefügten `CJumpList` bisher.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht und alle Daten und internen Schnittstellen frei.  
  
##  <a name="clearalldestinations"></a>CJumpList::ClearAllDestinations  
 Entfernt alle Ziele, die bisher mit der aktuellen Instanz von CJumpList hinzugefügt wurden.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, wenn müssen Sie alle Ziele entfernen, die bisher in der Ziel-Liste erstellen von der aktuellen Sitzung hinzugefügt wurden, und andere Ziele erneut hinzufügen. Wenn die interne `ICustomDestinationList` wurde initialisiert, es bleibt aktiv.  
  
##  <a name="commitlist"></a>CJumpList::CommitList  
 Beendet eine Liste erstellen-Transaktion und führt einen Commit für die gemeldeten Liste in den zugehörigen Speicher (in diesem Fall der Registrierung).  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Der Commit ist atomar. Wenn dies fehlschlägt, wird ein Fehler zurückgegeben werden.  Wenn `CommitList` aufgerufen wird, wird die aktuelle Liste der entfernten Elemente werden bereinigt. Das Aufrufen dieser Methode setzt das Objekt, damit sie nicht über eine aktive Transaktion für den Aufbau von Liste verfügt. Zum Aktualisieren der Liste `BeginList` erneut aufgerufen werden muss.  
  
##  <a name="getdestinationlist"></a>CJumpList::GetDestinationList  
 Ruft einen Schnittstellenzeiger auf Zielliste ab.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Sprungliste nicht initialisiert wurde, oder ein Commit ausgeführt oder wurde abgebrochen, wird der zurückgegebene Wert `NULL`.  
  
##  <a name="getmaxslots"></a>CJumpList::GetMaxSlots  
 Ruft die maximale Anzahl von Elementen, einschließlich der Kategorie-Header, die in der aufrufenden Anwendung Ziel im Menü angezeigt werden können.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Clientanwendungen melden möglicherweise nur eine Reihe von Elementen und Kategorie-Header, die bis zu diesem Wert kombiniert. Wenn Aufrufe von `AppendCategory`, `AppendKnownCategory`, oder `AddUserTasks` diese Anzahl übersteigt, wird Fehler zurückgegeben.  
  
##  <a name="getremoveditems"></a>CJumpList::GetRemovedItems  
 Gibt ein Array von Elementen, die darstellen entfernt Ziele.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die entfernten Ziele werden bei der Initialisierung der Sprungliste abgerufen. Beim Generieren einer neuen Zielliste Applications vorausgesetzt, dass die Zieleliste entfernten deaktivieren die Überwachungsdaten für jedes Element der entfernten NodeList-Enumerator zurückgegebenes zuerst verarbeitet. Wenn eine Anwendung versucht, ein Element bereitstellen, die gerade, in der Transaktion, die die aktuelle aufrufen entfernt wurde, um `BeginList` gestartet, der Aufruf der Methode, die das Element erneut hinzugefügt fehl, um sicherzustellen, dass die Anwendung die Liste entfernte zu beachten sind.  
  
##  <a name="initializelist"></a>CJumpList::InitializeList  
 Beginnt eine Transaktion Liste erstellen.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Methode explizit aufrufen, es sei denn, Sie einen Zeiger auf abrufen möchten `ICustomDestinationList` mit `GetDestinationList`, die Anzahl der Steckplätze verfügbar, die mit `GetMaxSlots`, oder eine Liste der entfernten Elemente mit `GetRemovedItems`.  
  
##  <a name="setappid"></a>CJumpList::SetAppID  
 Legt die Benutzer-Modell-ID für die Liste, die erstellt wird.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>Parameter  
 `strAppID`  
 Eine Zeichenfolge, die die Anwendungsmodell für Benutzer-ID angibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

