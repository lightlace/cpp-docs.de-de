---
title: CSyncObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: 842ff5f98f05425fbbb511d112ae3e4fd65ff076
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263709"
---
# <a name="csyncobject-class"></a>CSyncObject-Klasse

Eine rein virtuelle Klasse, welche die Funktionalität bereitstellt, die alle Synchronisierungsobjekte in Win32 gemeinsam haben.

## <a name="syntax"></a>Syntax

```
class CSyncObject : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|Erstellt ein `CSyncObject`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSyncObject::Lock](#lock)|Verschafft sich Zugriff auf das Synchronisierungsobjekt.|
|[CSyncObject::Unlock](#unlock)|Verschafft sich Zugriff auf das Synchronisierungsobjekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CSyncObject::operator HANDLE](#operator_handle)|Bietet Zugriff auf das Synchronisierungsobjekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CSyncObject::m_hObject](#m_hobject)|Das Handle für das zugrunde liegende Synchronisierungsobjekt.|

## <a name="remarks"></a>Hinweise

Die Microsoft Foundation Class Library stellt mehrere Klassen, die von `CSyncObject`. Hierbei handelt es sich [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), und [CSemaphore](../../mfc/reference/csemaphore-class.md).

Informationen dazu, wie die Synchronisierungsobjekte verwenden, finden Sie im Artikel [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="csyncobject"></a>  CSyncObject::CSyncObject

Erstellt ein Synchronisierungsobjekt, das mit dem angegebenen Namen.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Parameter

*pstrName*<br/>
Der Name des Objekts. Wenn der Wert NULL, *PstrName* NULL.

##  <a name="lock"></a>  CSyncObject::Lock

Rufen Sie diese Funktion für den Zugriff auf die Ressource, die durch das Synchronisierungsobjekt gesteuert.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Parameter

*dwTimeout*<br/>
Gibt die Zeitspanne in Millisekunden zu warten, bis das Synchronisierungsobjekt verfügbar sein (signalisiert). Wenn INFINITE, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn das Synchronisierungsobjekt, das signalisiert wird, `Lock` erfolgreich zurückgegeben wird und der Thread wird jetzt das Objekt besitzt. Wenn das Synchronisierungsobjekt, das auf "nicht signalisiert" festgelegt ist (nicht verfügbar), `Lock` wartet darauf, dass das Synchronisierungsobjekt, das die Anzahl von Millisekunden, die im angegebenen signalisiert wird die *DwTimeOut* Parameter. Wenn das Synchronisierungsobjekt, das in die angegebene Zeitspanne nicht signalisiert `Lock` Fehler zurückgegeben.

##  <a name="m_hobject"></a>  CSyncObject::m_hObject

Das Handle für das zugrunde liegende Synchronisierungsobjekt.

```
HANDLE m_hObject;
```

##  <a name="operator_handle"></a>  CSyncObject::operator HANDLE

Verwenden Sie diesen Operator, um das Handle des erhalten die `CSyncObject` Objekt.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle des Objekts Synchronisierung andernfalls NULL.

### <a name="remarks"></a>Hinweise

Sie können das Handle verwenden, um Windows-APIs direkt aufrufen.

##  <a name="unlock"></a>  CSyncObject::Unlock

Die Deklaration von `Unlock` ohne Parameter ist eine reine virtuelle Funktion, und muss von der alle von abgeleiteten Klassen überschrieben werden `CSyncObject`.

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>Parameter

*lCount*<br/>
Von der Standardimplementierung verwendet nicht.

*lpPrevCount*<br/>
Von der Standardimplementierung verwendet nicht.

### <a name="return-value"></a>Rückgabewert

Immer die Standardimplementierung gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung der Deklaration immer mit zwei Parametern gibt "true" zurück. Diese Funktion wird aufgerufen, um den Zugriff auf das Synchronisierungsobjekt, das im Besitz des aufrufenden Threads freizugeben. Für Synchronisierungsobjekten wie Semaphoren, die mehr als ein Zugriff auf eine gesteuerte Ressource zu ermöglichen, wird die zweite Deklaration bereitgestellt.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
