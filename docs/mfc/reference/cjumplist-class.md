---
title: CJumpList-Klasse
ms.date: 03/27/2019
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
ms.openlocfilehash: 9296912c97b1efb5f7cbd1ed9f769d0222d5f85c
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565307"
---
# <a name="cjumplist-class"></a>CJumpList-Klasse

Ein `CJumpList` ist die Liste der Tastenkombinationen angezeigt wird, wenn Sie mit der rechten auf ein Symbol in der Taskleiste Maustaste.

## <a name="syntax"></a>Syntax

```
class CJumpList;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|Erstellt ein `CJumpList`-Objekt.|
|[CJumpList::~CJumpList](#_dtorcjumplist)|Zerstört ein `CJumpList`-Objekt.|

|Name|Beschreibung|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|Bricht eine Liste zum Erstellen von Transaktionen ohne Commit ab.|
|[CJumpList::AddDestination](#adddestination)|Überladen. Ziel hinzugefügt der Liste.|
|[CJumpList::AddKnownCategory](#addknowncategory)|Fügt eine bekannte Kategorie der Liste an.|
|[CJumpList::AddTask](#addtask)|Überladen. Fügt Elemente in der kanonischen Aufgaben Kategorie an.|
|[CJumpList::AddTasks](#addtasks)|Fügt Elemente in der kanonischen Aufgaben Kategorie an.|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Fügt ein Trennzeichen zwischen Aufgaben.|
|[CJumpList::ClearAll](#clearall)|Entfernt alle Aufgaben und Ziele, die die aktuelle Instanz von hinzugefügt wurden `CJumpList` bisher.|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Entfernt alle Ziele, die mit der aktuellen Instanz von hinzugefügt wurden `CJumpList` bisher.|
|[CJumpList::CommitList](#commitlist)|Beendet eine Liste zum Erstellen von-Transaktion und führt einen Commit für die gemeldeten Liste in den zugeordneten Speicher (die Registrierung, die in diesem Fall.)|
|[CJumpList::GetDestinationList](#getdestinationlist)|Ruft einen Schnittstellenzeiger auf Zielliste ab.|
|[CJumpList::GetMaxSlots](#getmaxslots)|Ruft die maximale Anzahl der Elemente, einschließlich der Kategorie-Header, die in der aufrufenden Anwendung Ziel im Menü angezeigt werden können.|
|[CJumpList::GetRemovedItems](#getremoveditems)|Gibt ein Array von Elementen, die darstellen, entfernt die Ziele.|
|[CJumpList::InitializeList](#initializelist)|Startet eine Transaktion zum Erstellen von Liste.|
|[CJumpList::SetAppID](#setappid)|Legt fest, die Anwendungsbenutzer-Modell-ID für die Liste, die erstellt wird.|

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

Bricht eine Liste zum Erstellen von Transaktionen ohne Commit ab.

```
void AbortList();
```

### <a name="remarks"></a>Hinweise

Das Aufrufen dieser Methode hat dieselbe Wirkung wie das Zerstören von `CJumpList` ohne `CommitList`.

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

*lpcszCategoryName*<br/>
Gibt an, einen Kategorienamen ein. Wenn die angegebene Kategorie nicht vorhanden ist, wird er erstellt.

*strDestinationPath*<br/>
Gibt einen Pfad zur Zieldatei an.

*strCategoryName*<br/>
Gibt an, einen Kategorienamen ein. Wenn die angegebene Kategorie nicht vorhanden ist, wird er erstellt.

*pShellItem*<br/>
Gibt ein Shell-Element, das das hinzugefügte Ziel darstellt.

*pShellLink*<br/>
Gibt eine Shell-Verknüpfung, die das hinzugefügte Ziel darstellt.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die Instanz von `CJumpList` intern akkumuliert zusätzliche Ziele, und klicken Sie dann ein Commit ausgeführt, in `CommitList`.

##  <a name="addknowncategory"></a>  CJumpList::AddKnownCategory

Fügt eine bekannte Kategorie der Liste an.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Parameter

*category*<br/>
Gibt einen bekannten Typ an. Hierbei kann es sich um KDC_RECENT oder KDC_KNOWN sein.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Kategorien bekanntermaßen häufige und zuletzt Kategorien, die wir automatisch für jede Anwendung berechnet, der verwendet `SHAddToRecentDocs` (oder indirekt verwendet, wie die Shell im Auftrag der Anwendung, in einigen Szenarien aufgerufen werden).

##  <a name="addtask"></a>  CJumpList::AddTask

Fügt Elemente in der kanonischen Aufgaben Kategorie an.

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

*strTargetExecutablePath*<br/>
Gibt den Zielpfad für den Task an.

*strCommandLineArgs*<br/>
Gibt die Befehlszeilenargumente der ausführbaren Datei gemäß *StrTargetExecutablePath*.

*strTitle*<br/>
Der Name der Aufgabe, die in der Zielliste angezeigt werden.

*strIconLocation*<br/>
Speicherort des Symbols, der in der Zielliste zusammen mit dem Titel angezeigt wird.

*iIconIndex*<br/>
Symbol-Index.

*pShellLink*<br/>
Shell-Link, der eine Aufgabe hinzugefügt werden darstellt.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die Instanz von `CJumpList` sammelt die angegebene Aufgaben und fügt sie der Zielliste während hinzu `CommitList`. Task-Elemente werden in einer Kategorie, unten auf der Ziel-Menü der Anwendung angezeigt. Diese Kategorie hat Vorrang vor allen anderen Kategorien, wenn sie in der Benutzeroberfläche aufgefüllt wird.

##  <a name="addtasks"></a>  CJumpList::AddTasks

Fügt Elemente in der kanonischen Aufgaben Kategorie an.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Parameter

*pObjectCollection*<br/>
Eine Auflistung von Aufgaben hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die Instanz von CJumpList sammelt die angegebene Aufgaben und fügt sie der Zielliste während hinzu `CommitList`. Task-Elemente werden in einer Kategorie, unten auf der Ziel-Menü der Anwendung angezeigt. Diese Kategorie hat Vorrang vor allen anderen Kategorien, wenn sie in der Benutzeroberfläche aufgefüllt wird.

##  <a name="addtaskseparator"></a>  CJumpList::AddTaskSeparator

Fügt ein Trennzeichen zwischen Aufgaben.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich ist, ist 0, wenn er nicht ist.

##  <a name="cjumplist"></a>  CJumpList::CJumpList

Erstellt ein `CJumpList`-Objekt.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Parameter

*bAutoCommit*<br/>
Wenn dieser Parameter auf "false" ist die Liste nicht automatisch im Destruktor committet.

##  <a name="clearall"></a>  CJumpList::ClearAll

Entfernt alle Aufgaben und Ziele, die die aktuelle Instanz von hinzugefügt wurden `CJumpList` bisher.

```
void ClearAll();
```

### <a name="remarks"></a>Hinweise

Diese Methode löscht und gibt alle Daten und internen Schnittstellen frei.

##  <a name="clearalldestinations"></a>  CJumpList::ClearAllDestinations

Entfernt alle Ziele, die mit der aktuellen Instanz von CJumpList bisher hinzugefügt wurden.

```
void ClearAllDestinations();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, wenn Sie alle Ziele zu entfernen, die bisher in der Ziel-Liste erstellen von der aktuellen Sitzung hinzugefügt wurden, und andere Ziele wieder hinzufügen möchten. Wenn die interne `ICustomDestinationList` wurde initialisiert, es bleibt aktiv.

##  <a name="commitlist"></a>  CJumpList::CommitList

Beendet eine Liste zum Erstellen von Transaktion und führt einen Commit für die gemeldeten Liste in den zugeordneten Speicher (die Registrierung in diesem Fall).

```
BOOL CommitList();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Der Commit ist unteilbar. Wenn der Commitvorgang fehlschlägt, wird ein Fehler zurückgegeben werden.  Wenn `CommitList` aufgerufen wird, wird die aktuelle Liste der entfernten Elemente werden bereinigt. Das Aufrufen dieser Methode setzt das Objekt zurück, damit sie nicht über eine aktive Transaktion für die Liste zum Erstellen von verfügt. Zum Aktualisieren der Liste, `BeginList` erneut aufgerufen werden muss.

##  <a name="getdestinationlist"></a>  CJumpList::GetDestinationList

Ruft einen Schnittstellenzeiger auf Zielliste ab.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Wenn die Sprungliste nicht initialisiert wurde, oder ein Commit ausgeführt oder wurde abgebrochen, wird der zurückgegebene Wert NULL sein.

##  <a name="getmaxslots"></a>  CJumpList::GetMaxSlots

Ruft die maximale Anzahl der Elemente, einschließlich der Kategorie-Header, die in der aufrufenden Anwendung Ziel im Menü angezeigt werden können.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Anwendungen melden möglicherweise nur eine Reihe von Elementen und Kategorie-Header, die bis zu diesem Wert kombiniert. Wenn Aufrufe von `AppendCategory`, `AppendKnownCategory`, oder `AddUserTasks` diese Anzahl überschreiten, diese Fehler zurück.

##  <a name="getremoveditems"></a>  CJumpList::GetRemovedItems

Gibt ein Array von Elementen, die darstellen, entfernt die Ziele.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die entfernte Ziele werden während der Initialisierung der Sprungliste abgerufen. Wenn Sie eine neue Zielliste generieren, sollten Anwendungen die Zieleliste entfernt löschen ihre Überwachungsdaten für jedes Element der Liste der entfernten-Enumerator zurückgegebenes zuerst zu verarbeiten. Wenn eine Anwendung versucht, ein Element bereit, die gerade, in der Transaktion, die die aktuelle aufrufen entfernt wurde, um `BeginList` gestartet wurde, den Aufruf der Methode, die das Element erneut hinzugefügt schlägt fehl, um sicherzustellen, dass Anwendungen Benennung von der Liste entfernt werden.

##  <a name="initializelist"></a>  CJumpList::InitializeList

Startet eine Transaktion zum Erstellen von Liste.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Sie müssen diese Methode explizit aufrufen, es sei denn, Sie einen Zeiger auf abrufen möchten `ICustomDestinationList` mit `GetDestinationList`, die Anzahl der verfügbaren Slots mit `GetMaxSlots`, oder eine Liste der entfernten Elemente, die mit `GetRemovedItems`.

##  <a name="setappid"></a>  CJumpList::SetAppID

Legt fest, die Anwendungsbenutzer-Modell-ID für die Liste, die erstellt wird.

```
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Parameter

*strAppID*<br/>
Eine Zeichenfolge, die Anwendungsbenutzermodell-ID angibt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
