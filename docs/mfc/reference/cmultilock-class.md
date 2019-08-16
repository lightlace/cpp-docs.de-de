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
ms.openlocfilehash: b2fe3ecf2197b8edb13e89600b16e550deff9af2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504550"
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
|[CMultiLock::IsLocked](#islocked)|Bestimmt, ob ein bestimmtes Synchronisierungs Objekt im-Array gesperrt ist.|
|[CMultiLock::Lock](#lock)|Wartet auf das Array von Synchronisierungs Objekten.|
|[CMultiLock::Unlock](#unlock)|Gibt alle im Besitz befindlichen Synchronisierungs Objekte frei.|

## <a name="remarks"></a>Hinweise

`CMultiLock`weist keine Basisklasse auf.

Wenn Sie die Synchronisierungs Klassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md)und [CEvent](../../mfc/reference/cevent-class.md)verwenden möchten, können Sie entweder `CMultiLock` ein-oder ein [CSingleLock](../../mfc/reference/csinglelock-class.md) -Objekt erstellen, um darauf zu warten und das Synchronisierungs Objekt freizugeben. Verwenden `CMultiLock` Sie, wenn mehrere Objekte zu einem bestimmten Zeitpunkt verwendet werden können. Verwenden `CSingleLock` Sie, wenn Sie nur auf ein Objekt gleichzeitig warten müssen.

Um ein `CMultiLock` -Objekt zu verwenden, erstellen Sie zunächst ein Array der Synchronisierungs Objekte, auf die gewartet werden soll. Als nächstes wird der `CMultiLock` Konstruktor des Objekts in einer Member-Funktion in der Klasse der kontrollierten Ressource aufgerufen. Anschließend können Sie die Funktion zum [Sperren](#lock) eines Members aufzurufen, um zu bestimmen, ob eine Ressource verfügbar (signalisiert) ist Wenn ein solcher Wert ist, fahren Sie mit dem Rest der Member-Funktion fort. Wenn keine Ressource verfügbar ist, warten Sie entweder einen bestimmten Zeitraum auf die Freigabe einer Ressource, oder geben Sie einen Fehler zurück. Wenn die Verwendung einer Ressource beendet ist, müssen Sie entweder die [Unlock](#unlock) -Funktion `CMultiLock` aufzurufen, wenn das Objekt erneut verwendet werden soll `CMultiLock` , oder das Objekt zerstören lassen.

`CMultiLock`-Objekte sind besonders nützlich, wenn ein Thread über eine große `CEvent` Anzahl von Objekten verfügt, auf die er reagieren kann. Erstellen Sie ein Array, das `CEvent` alle Zeiger enthält, `Lock`und rufen Sie auf. Dadurch wird der Thread gewartet, bis eines der Ereignisse signalisiert wird.

Weitere Informationen zur Verwendung `CMultiLock` von Objekten finden Sie im Artikel [Multithreading: Verwenden der Synchronisierungs Klassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CMultiLock`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="cmultilock"></a>CMultiLock:: CMultiLock

Erstellt ein `CMultiLock`-Objekt.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parameter

*ppObjects*<br/>
Array von Zeigern zu den Synchronisierungs Objekten, auf die gewartet werden soll. Lässt keine NULL-Werte zu.

*dwCount*<br/>
Anzahl von Objekten in *ppobjects*. Muss größer als 0 sein.

*bInitialLock*<br/>
Gibt an, ob zunächst versucht wird, auf eines der bereitgestellten-Objekte zuzugreifen.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, nachdem das Array von Synchronisierungs Objekten erstellt wurde, auf das gewartet werden soll. Sie wird in der Regel aus dem Thread aufgerufen, der darauf warten muss, dass eines der Synchronisierungs Objekte verfügbar wird.

##  <a name="islocked"></a>CMultiLock:: IsLocked

Bestimmt, ob das angegebene Objekt nicht signalisiert (nicht verfügbar) ist.

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>Parameter

*dwItem*<br/>
Der Index im Array von-Objekten, das dem-Objekt entspricht, dessen Zustand abgefragt wird.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das angegebene Objekt gesperrt ist. andernfalls 0.

##  <a name="lock"></a>CMultiLock:: Lock

Mit dieser Funktion erhalten Sie Zugriff auf eine oder mehrere Ressourcen, die von den Synchronisierungs Objekten gesteuert werden, `CMultiLock` die für den Konstruktor bereitgestellt werden.

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>Parameter

*dwTimeOut*<br/>
Gibt die Zeitspanne an, die gewartet werden soll, bis das Synchronisierungs Objekt verfügbar (signalisiert) ist. Wenn unendlich, `Lock` wartet, bis das Objekt signalisiert wird, bevor es zurückgegeben wird.

*bWaitForAll*<br/>
Gibt an, ob alle Objekte, auf die gewartet wird, gleichzeitig vor der Rückgabe signalisiert werden müssen. Wenn der Wert `Lock` false ist, wird zurückgegeben, wenn eines der-Objekte signalisiert wird.

*dwWakeMask*<br/>
Gibt andere Bedingungen an, die für das Abbrechen des warte Vorgangs zulässig sind. Eine vollständige Liste der verfügbaren Optionen für diesen Parameter finden Sie im Windows SDK unter [MsgWaitForMultipleObjects](/windows/win32/api/winuser/nf-winuser-msgwaitformultipleobjects) .

### <a name="return-value"></a>Rückgabewert

Wenn `Lock` fehlschlägt, wird-1 zurückgegeben. Bei erfolgreicher Ausführung wird einer der folgenden Werte zurückgegeben:

- Zwischen WAIT_OBJECT_0 und WAIT_OBJECT_0 + (Anzahl von Objekten-1)

   Wenn *bwaitforall* den Wert true hat, werden alle Objekte signalisiert (verfügbar). Wenn *bwaitforall* den Wert false hat, ist der Rückgabewert-WAIT_OBJECT_0 der Index im Array von Objekten des Objekts, das signalisiert wird (verfügbar).

- WAIT_OBJECT_0 + (Anzahl der Objekte)

   Ein in *dwwakemask* angegebenes Ereignis ist in der Eingabe Warteschlange des Threads verfügbar.

- Zwischen WAIT_ABANDONED_0 und WAIT_ABANDONED_0 + (Anzahl von Objekten-1)

   Wenn *bwaitforall* den Wert true hat, werden alle Objekte signalisiert, und mindestens eines der Objekte ist ein abgebrochenes Mutex-Objekt. Wenn *bwaitforall* den Wert false hat, ist der Rückgabewert-WAIT_ABANDONED_0 der Index im Array von Objekten des abgebrochenen Mutex-Objekts, das den warte Vorgang erfüllt hat.

- WAIT_TIMEOUT

   Das in *dwtimeout* angegebene Timeout Intervall ist abgelaufen, ohne dass der Warte Vorgang erfolgreich abgeschlossen wurde.

### <a name="remarks"></a>Hinweise

Wenn *bwaitforall* den Wert true `Lock` hat, wird erfolgreich zurückgegeben, sobald alle Synchronisierungs Objekte gleichzeitig signalisiert werden. Wenn *bwaitforall* den Wert false `Lock` hat, wird zurückgegeben, sobald mindestens ein Synchronisierungs Objekt signalisiert wird.

Wenn `Lock` nicht sofort zurückgeben kann, wartet es nicht mehr als die im *dwtimeout* -Parameter angegebene Anzahl von Millisekunden, bevor die Rückgabe erfolgt. Wenn *dwtimeout* unbegrenzt ist, `Lock` wird von nicht zurückgegeben, bis der Zugriff auf ein Objekt erreicht oder eine in *dwwakemask* angegebene Bedingung erfüllt wurde. Wenn `Lock` dann ein Synchronisierungs Objekt abrufen konnte, wird es erfolgreich zurückgegeben; andernfalls wird ein Fehler zurückgegeben.

##  <a name="unlock"></a>CMultiLock:: Unlock

Gibt das Synchronisierungs Objekt im `CMultiLock`Besitz von frei.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parameter

*lCount*<br/>
Anzahl der zu veröffentlichenden Verweis Zähler. Muss größer als 0 sein. Wenn der angegebene Betrag bewirkt, dass die Anzahl der Objekte den maximalen Wert überschreitet, wird die Anzahl nicht geändert, und die Funktion gibt false zurück.

*lPrevCount*<br/>
Verweist auf eine Variable, um die vorherige Anzahl für das Synchronisierungs Objekt zu empfangen. Wenn der Wert NULL ist, wird die vorherige Anzahl nicht zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion wird vom Dekonstruktor von `CMultiLock`aufgerufen.

Die erste Form von `Unlock` versucht, das von `CMultiLock`verwaltete Synchronisierungs Objekt zu entsperren. Die zweite Form von `Unlock` versucht, die Objekte `CSemaphore` zu entsperren, `CMultiLock`die im Besitz von sind. Wenn `CMultiLock` kein gesperrtes `CSemaphore` Objekt besitzt, gibt die Funktion false zurück; andernfalls wird true zurückgegeben. *lCount* und *lpprevcount* sind exakt mit den Parametern von [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)identisch. Die zweite Form von `Unlock` ist nur selten auf multisperrungs Situationen anwendbar.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
