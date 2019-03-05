---
title: CMultiLock-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
ms.openlocfilehash: 107ed227c5515cbf2fcb08e957a64a4a17d8287a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288663"
---
# <a name="cmultilock-class"></a>CMultiLock-Klasse

Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.

## <a name="syntax"></a>Syntax

```
class CMultiLock
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMultiLock::CMultiLock](#cmultilock)|Erstellt ein `CMultiLock`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMultiLock::IsLocked](#islocked)|Bestimmt, ob eine bestimmte Synchronisierungsobjekt, das im Array gesperrt ist.|
|[CMultiLock::Lock](#lock)|Wartet auf das Array von Synchronisierungsobjekten.|
|[CMultiLock::Unlock](#unlock)|Gibt alle Synchronisierungsobjekte im Besitz des Benutzers frei.|

## <a name="remarks"></a>Hinweise

`CMultiLock` eine Basisklasse keinen.

Der Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), und [CEvent](../../mfc/reference/cevent-class.md), erstellen Sie entweder eine `CMultiLock` oder [CSingleLock](../../mfc/reference/csinglelock-class.md)Objekt gewartet werden soll, und das Synchronisierungsobjekt freizugeben. Verwenden Sie `CMultiLock` Wenn mehrere Objekte, die Sie zu einem bestimmten Zeitpunkt verwenden können. Verwendung `CSingleLock` Wenn müssen Sie nur auf ein Objekt zu einem Zeitpunkt zu warten.

Verwenden einer `CMultiLock` Objekt, das zuerst erstellt ein Array von die Synchronisierungsobjekte, die auf die gewartet werden sollen. Rufen Sie als Nächstes die `CMultiLock` Konstruktor des Objekts innerhalb einer Memberfunktion in der gesteuerte Ressource-Klasse. Rufen Sie dann die [Sperre](#lock) Memberfunktion, um zu bestimmen, ob eine Ressource verfügbar ist (signalisiert). Wenn eine ist, weiterhin mit den übrigen von der Memberfunktion. Wenn keine Ressource verfügbar ist, warten Sie, bis eine angegebene Zeitspanne für eine Ressource freigegeben werden oder Fehler zurück. Nach der Verwendung einer Ressource abgeschlossen ist, rufen Sie entweder die [Unlock](#unlock) ausgeführt werden, wenn die `CMultiLock` Objekt ist, erneut verwendet werden, oder ermöglichen die `CMultiLock` Objekt, das zerstört werden.

`CMultiLock` Objekte sind besonders hilfreich, wenn ein Thread eine große Anzahl von `CEvent` reagiert er auf Objekte. Erstellen Sie ein Array mit allen dem `CEvent` Zeiger, und rufen `Lock`. Dadurch wird den Thread wartet, bis eines der Ereignisse signalisiert wird.

Weitere Informationen zur Verwendung von `CMultiLock` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CMultiLock`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="cmultilock"></a>  CMultiLock::CMultiLock

Erstellt ein `CMultiLock`-Objekt.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parameter

*ppObjects*<br/>
Array von Zeigern auf die Synchronisierungsobjekte, auf die gewartet werden soll. Darf nicht NULL sein.

*dwCount*<br/>
Anzahl von Objekten in *PpObjects*. Muss größer als 0 sein.

*bInitialLock*<br/>
Gibt an, ob zunächst versuchen, auf die angegebenen Objekte zuzugreifen.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, nach dem Erstellen des Arrays mit Synchronisierungsobjekte, auf die gewartet wird. Sie wird in der Regel von innerhalb des Threads aufgerufen, die auf eines der Synchronisierungsobjekte auf das Freiwerden warten müssen.

##  <a name="islocked"></a>  CMultiLock::IsLocked

Bestimmt, ob das angegebene Objekt auf "nicht signalisiert" festgelegt ist (nicht verfügbar).

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>Parameter

*dwItem*<br/>
Der Index im Array von Objekten, die für das Objekt, dessen Status abgefragt wird.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das angegebene Objekt gesperrt ist; andernfalls 0.

##  <a name="lock"></a>  CMultiLock::Lock

Mit dieser Funktion wird für den Zugriff auf eine oder mehrere Ressourcen gesteuert durch die Synchronisierungsobjekte, die `CMultiLock` Konstruktor.

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>Parameter

*dwTimeOut*<br/>
Gibt den Umfang der Wartezeit für das Synchronisierungsobjekt verfügbar sein (signalisiert). Wenn INFINITE, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.

*bWaitForAll*<br/>
Gibt an, ob alle Objekte, die auf die gewartet, die zur gleichen Zeit vor der Rückgabe signalisiert werden müssen. False gibt an, `Lock` zurück, wenn die Objekte, die auf die gewartet signalisiert wird.

*dwWakeMask*<br/>
Gibt andere Bedingungen, die zulässig sind, den Wartevorgang abgebrochen. Eine vollständige Liste der verfügbaren Optionen für diesen Parameter, finden Sie unter [MsgWaitForMultipleObjects](/windows/desktop/api/winuser/nf-winuser-msgwaitformultipleobjects) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Wenn `Lock` fehlschlägt, wird – 1. Im Erfolgsfall gibt es einen der folgenden Werte zurück:

- WAIT_OBJECT_0 und WAIT_OBJECT_0 + (Anzahl der Objekte – 1)

   Wenn *bWaitForAll* ist "true", alle Objekte (verfügbar) signalisiert werden. Wenn *bWaitForAll* ist "false", der Rückgabewert - WAIT_OBJECT_0 ist der Index im Array von Objekten des Objekts, das (verfügbar) signalisiert wird.

- WAIT_OBJECT_0 + (Anzahl von Objekten)

   Ein Ereignis, das im angegebenen *DwWakeMask* finden Sie in der Eingabewarteschlange des Threads.

- Zwischen WAIT_ABANDONED_0 und WAIT_ABANDONED_0 + (Anzahl der Objekte – 1)

   Wenn *bWaitForAll* ist "true", alle Objekte signalisiert werden und mindestens eines der Objekte wird ein abgebrochener Mutex-Objekt. Wenn *bWaitForAll* ist "false", der Rückgabewert - WAIT_ABANDONED_0 ist der Index im Array von Objekten des abgebrochenen Mutex-Objekts, das den Wartevorgang erfüllt hat.

- WAIT_TIMEOUT

   Das Timeoutintervall, die im angegebenen *DwTimeOut* erfolglos dem Wartevorgang abgelaufen ist.

### <a name="remarks"></a>Hinweise

Wenn *bWaitForAll* ist "true", `Lock` wird erfolgreich zurückgegeben, sobald die Synchronisierungsobjekte gleichzeitig signalisiert werden. Wenn *bWaitForAll* ist "false", `Lock` wird zurückgegeben, sobald eine oder mehrere der die Synchronisierungsobjekte signalisiert wird.

Wenn `Lock` kann nicht sofort zurückkehren, wartet es nicht mehr als die Anzahl der Millisekunden, die im angegebenen die *DwTimeOut* Parameter vor der Rückgabe. Wenn *DwTimeOut* lautet "INFINITE", " `Lock` nicht zurückgegeben, bis der Zugriff auf ein Objekt erzielt wird, oder eine Bedingung angegeben wird, *DwWakeMask* erfüllt wurde. Andernfalls gilt: Wenn `Lock` wurde ein Synchronisierungsobjekt abrufen können, wird zurückgegeben, die erfolgreich; Falls nicht, diese Fehler zurück.

##  <a name="unlock"></a>  CMultiLock::Unlock

Gibt das Synchronisierungsobjekt, das im Besitz von `CMultiLock`.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parameter

*lCount*<br/>
Verweis zählt zum Freigeben. Muss größer als 0 sein. Wenn die angegebene Menge der Objektanzahl überschreitet die maximale Anzahl führen würde, wird die Anzahl die nicht geändert, und die Funktion gibt "false" zurück.

*lPrevCount*<br/>
Verweist auf eine Variable, die die vorherige Anzahl für das Synchronisierungsobjekt zu erhalten. Wenn der Wert NULL ist, wird die vorherige Anzahl nicht zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, indem `CMultiLock`den Destruktor.

Die erste Form der `Unlock` versucht, das Synchronisierungsobjekt, die von verwaltet zu entsperren `CMultiLock`. Die zweite Form der `Unlock` versucht, die zum Entsperren der `CSemaphore` Objekte, die im Besitz von `CMultiLock`. Wenn `CMultiLock` besitzt eine nicht gesperrte `CSemaphore` Objekts, die Funktion gibt "false" zurück; andernfalls wird "true" zurückgegeben. *lCount* und *LpPrevCount* entsprechen exakt mit den Parametern der [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). Die zweite Form der `Unlock` ist nur selten auf multilock Situationen anwendbar.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
