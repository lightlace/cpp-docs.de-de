---
title: CSingleLock-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 31bd43f7f7a6fbccd4680db013ac5c654123061e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324102"
---
# <a name="csinglelock-class"></a>CSingleLock-Klasse

Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.

## <a name="syntax"></a>Syntax

```
class CSingleLock
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|Erstellt ein `CSingleLock`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSingleLock::IsLocked](#islocked)|Bestimmt, ob das Objekt gesperrt ist.|
|[CSingleLock::Lock](#lock)|Klicken Sie auf ein Synchronisierungsobjekt wartet.|
|[CSingleLock::Unlock](#unlock)|Gibt ein Synchronisierungsobjekt frei.|

## <a name="remarks"></a>Hinweise

`CSingleLock` eine Basisklasse keinen.

Um der Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), und [CEvent](../../mfc/reference/cevent-class.md), müssen Sie erstellen entweder eine `CSingleLock` oder [CMultiLock](../../mfc/reference/cmultilock-class.md) Objekt gewartet werden soll, und das Synchronisierungsobjekt freizugeben. Verwendung `CSingleLock` Wenn müssen Sie nur auf ein Objekt zu einem Zeitpunkt zu warten. Verwenden Sie `CMultiLock` Wenn mehrere Objekte, die Sie zu einem bestimmten Zeitpunkt verwenden können.

Verwenden einer `CSingleLock` Objekt, dessen Konstruktor innerhalb einer Memberfunktion in der gesteuerte Ressource-Klasse aufrufen. Rufen Sie dann die [IsLocked](#islocked) Memberfunktion, um zu bestimmen, ob die Ressource verfügbar ist. Wenn es sich handelt, fahren Sie mit der Rest der Memberfunktion fort. Wenn die Ressource nicht verfügbar ist, warten Sie, bis eine angegebene Zeitspanne für die Ressource freigegeben werden oder Fehler zurück. Nach der Verwendung der Ressource abgeschlossen ist, rufen Sie entweder die [Unlock](#unlock) ausgeführt werden, wenn die `CSingleLock` Objekt ist, erneut verwendet werden, oder ermöglichen die `CSingleLock` Objekt, das zerstört werden.

`CSingleLock` die Objekte sind erforderlich, das Vorhandensein eines Objekts abgeleitet [CSyncObject](../../mfc/reference/csyncobject-class.md). Dies ist normalerweise ein Mitglied von Daten für die gesteuerte Ressource-Klasse. Weitere Informationen zur Verwendung von `CSingleLock` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CSingleLock`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="csinglelock"></a>  CSingleLock::CSingleLock

Erstellt ein `CSingleLock`-Objekt.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parameter

*pObject*<br/>
Verweist auf das Synchronisierungsobjekt zugegriffen werden kann. Darf nicht NULL sein.

*bInitialLock*<br/>
Gibt an, ob zunächst versuchen, die Zugriff auf das angegebene Objekt.

### <a name="remarks"></a>Hinweise

Diese Funktion wird in der Regel aus einer Access-Memberfunktion der gesteuerte Ressource aufgerufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

##  <a name="islocked"></a>  CSingleLock::IsLocked

Bestimmt, ob das Objekt zugeordnet. die `CSingleLock` Objekt ist "nicht signalisiert" (nicht verfügbar).

```
BOOL IsLocked();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Objekt gesperrt ist; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

##  <a name="lock"></a>  CSingleLock::Lock

Mit dieser Funktion wird für den Zugriff auf die Ressource, gesteuert durch Synchronisierungsobjekt die `CSingleLock` Konstruktor.

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Parameter

*dwTimeOut*<br/>
Gibt den Umfang der Wartezeit für das Synchronisierungsobjekt verfügbar sein (signalisiert). Wenn INFINITE, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn das Synchronisierungsobjekt, das signalisiert wird, `Lock` erfolgreich zurückgegeben wird und der Thread wird jetzt das Objekt besitzt. Wenn das Synchronisierungsobjekt, das auf "nicht signalisiert" festgelegt ist (nicht verfügbar), `Lock` wartet darauf, dass das Synchronisierungsobjekt, das die Anzahl von Millisekunden, die im angegebenen signalisiert wird die *DwTimeOut* Parameter. Wenn das Synchronisierungsobjekt, das in die angegebene Zeitspanne nicht signalisiert `Lock` Fehler zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

##  <a name="unlock"></a>  CSingleLock::Unlock

Gibt das Synchronisierungsobjekt, das im Besitz von `CSingleLock`.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parameter

*lCount*<br/>
Die Anzahl von Zugriffen auf freigeben. Muss größer als 0 sein. Wenn die angegebene Menge der Objektanzahl überschreitet die maximale Anzahl führen würde, wird die Anzahl die nicht geändert, und die Funktion gibt "false" zurück.

*lPrevCount*<br/>
Verweist auf eine Variable, die die vorherige Anzahl von Synchronisierungsobjekt zu erhalten. Wenn der Wert NULL ist, wird die vorherige Anzahl nicht zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, indem `CSingleLock`den Destruktor.

Bei Bedarf, um mehr als eine Zugriffsversuche ein Semaphor freizugeben, verwenden Sie die zweite Form der `Unlock` und die Anzahl von Zugriffen auf die Version angeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock-Klasse](../../mfc/reference/cmultilock-class.md)
