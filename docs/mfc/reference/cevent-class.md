---
title: CEvent-Klasse
ms.date: 11/04/2016
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
ms.openlocfilehash: d7731c87c6d6b0ebdec9a0c72c24b04334aa0662
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206042"
---
# <a name="cevent-class"></a>CEvent-Klasse

Stellt ein Ereignis, d.h. ein Synchronisierungsobjekt, das es einem Thread ermöglicht anderen darüber zu benachrichtigen, die ein Ereignis aufgetreten ist.

## <a name="syntax"></a>Syntax

```
class CEvent : public CSyncObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CEvent::CEvent](#cevent)|Erstellt ein `CEvent`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CEvent::PulseEvent](#pulseevent)|Legt das Ereignis verfügbar (als Signal verwendet), wartenden Threads frei, und das Ereignis auf nicht verfügbar ("nicht signalisiert").|
|[CEvent::ResetEvent](#resetevent)|Legt fest, das Ereignis, nicht verfügbar ("nicht signalisiert").|
|[CEvent::SetEvent](#setevent)|Legt das Ereignis verfügbaren fest (signalisiert) aus, und alle wartenden Threads frei.|
|[CEvent::Unlock](#unlock)|Gibt das Ereignisobjekt frei.|

## <a name="remarks"></a>Hinweise

Ereignisse sind nützlich, wenn ein Thread bei seiner Aufgaben benötigen. Beispielsweise muss ein Thread, der Daten an ein Datenarchiv kopiert benachrichtigt, wenn neue Daten verfügbar sind. Mithilfe einer `CEvent` Objekt, das den kopieren-Thread zu benachrichtigen, wenn neue Daten verfügbar ist, werden der Thread seine Aufgabe so bald wie möglich ausführen.

`CEvent` Objekte verfügen über zwei Arten: manuelle und automatische.

Ein automatisches `CEvent` Objekt wird automatisch in einen nicht signalisierten (nicht verfügbar) Zustand zurückkehrt, nach der Veröffentlichung mindestens einen Thread. Standardmäßig eine `CEvent` Objekt erfolgt automatisch, es sei denn, Sie übergeben `TRUE` für die *bManualReset* Parameter während der Erstellung.

Eine manuelle `CEvent` Objekt verbleibt im Zustand "festlegen, indem" [SetEvent](#setevent) oder [ResetEvent](#resetevent) , bis die andere Funktion aufgerufen wird. Erstellen Sie eine manuelle `CEvent` Objekt, und übergeben `TRUE` für die `bManualReset` Parameter während der Erstellung.

Verwenden einer `CEvent` Objekt, das Erstellen der `CEvent` Objekt, wenn dies erforderlich ist. Geben Sie den Namen des Ereignisses, die Sie verwenden möchten, warten Sie auf, und auch angeben, dass Ihre Anwendung anfänglich besitzen sollen. Sie können dann das Ereignis, wenn Sie den Konstruktor zurück, zugreifen. Rufen Sie [SetEvent](#setevent) auf Signal (verfügbar machen) die Ereignisobjekt und rufen dann [Unlock](#unlock) Wenn Sie fertig sind den Zugriff auf gesteuerte Ressource.

Eine alternative Methode für die Verwendung von `CEvent` Objekten ist eine Variable des Typs hinzufügen `CEvent` als Datenmember der Klasse, die Sie steuern möchten. Rufen Sie während der Erstellung des kontrollierten-Objekts, den Konstruktor von den `CEvent` -Datenmember und anzugeben, ob das Ereignis ursprünglich signalisiert wird, sowie Specifythe-Typ des Ereignisobjekts werden sollen, den Namen des Ereignisses (wenn es zwischen Prozessen verwendet werden soll Grenzen), und alle gewünschten Sicherheitsattribute.

Zugriff auf eine Ressource, gesteuert durch eine `CEvent` Objekt auf diese Weise, erstellen Sie zunächst eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in die Zugriffsmethode für Ihre Ressource. Rufen Sie dann die `Lock` -Methode des Objekts Sperre (z. B. [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). Der Thread an diesem Punkt wird entweder Zugriff auf die Ressource, die Wartezeit für die Ressource freigegeben werden und Zugriff oder warten Sie, bis die Ressource freigegeben werden, die einen Timeout beendet und Fehler beim Zugriff auf die Ressource zu erhalten. In jedem Fall hat die Ressource auf threadsichere Weise erfolgt. Um die Ressource freizugeben, rufen `SetEvent` das Ereignisobjekt zu signalisieren, und klicken Sie dann verwenden die `Unlock` -Methode des Objekts Sperre (z. B. [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), oder Sie können das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.

Weitere Informationen zur Verwendung von `CEvent` Objekten finden Sie [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="cevent"></a>  CEvent::CEvent

Erstellt einen benannten oder unbenannten `CEvent` Objekt.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parameter

*bInitiallyOwn*<br/>
True gibt an, den Thread für die `CMultilock` oder `CSingleLock` -Objekt aktiviert ist. Andernfalls müssen alle Threads, die die Ressource zugreifen möchten warten.

*bManualReset*<br/>
True gibt an, gibt an, dass das Ereignisobjekt einen manuellen Ereignisses ist, andernfalls ist das Ereignisobjekt automatische Ereignis.

*Wert*<br/>
Name des `CEvent`-Objekts. Muss angegeben werden, wenn das Objekt über Prozessgrenzen hinweg verwendet werden soll. Der Name ein vorhandenes Ereignisses übereinstimmt, der Konstruktor erstellt ein neues `CEvent` Objekt, das das Ereignis mit diesem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf ein Ereignis ist übereinstimmt, schlägt die Erstellung fehl. Wenn der Wert NULL ist, wird der Name null sein.

*lpsaAttribute*<br/>
Von Sicherheitsattributen für das Ereignisobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) im Windows SDK.

### <a name="remarks"></a>Hinweise

Zum Zugreifen auf oder release eine `CEvent` Objekt, das Erstellen einer [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Member-Funktionen.

So ändern Sie den Status des eine `CEvent` auf die Signalisierung (Threads müssen nicht warten), rufen Sie [SetEvent](#setevent) oder [PulseEvent](#pulseevent). Zum Festlegen des Status von einem `CEvent` Objekt, das "nicht signalisiert" (Threads müssen warten), rufen Sie [ResetEvent](#resetevent).

> [!IMPORTANT]
>  Nach dem Erstellen der `CEvent` -Objekts [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex nicht vorhanden. Wenn der Mutex unerwartet vorhanden war, kann dies bedeuten, ein nicht autorisierten Prozess ist squatting und möglicherweise beabsichtigt Mutex in böswilliger Absicht verwendet werden. Die empfohlene Vorgehensweise für sicherheitsorientierten werden in diesem Fall das Handle geschlossen und fortgesetzt, als wäre der Fehler beim Erstellen des Objekts.

##  <a name="pulseevent"></a>  CEvent::PulseEvent

Legt den Zustand des Ereignisses auf signalisiert (verfügbar), alle wartenden Threads frei und damit "nicht signalisiert" (nicht verfügbar) automatisch zurückgesetzt.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Das Ereignis auf manuell eingestellt ist, werden alle wartenden Threads aufgehoben, wird das Ereignis zu "nicht signalisiert", und `PulseEvent` zurückgibt. Das Ereignis automatisch ist, wird ein einzelner Thread freigegeben, wird das Ereignis zu "nicht signalisiert", und `PulseEvent` zurückgibt.

Wenn keine Threads warten, oder keine Threads können, sofort freigegeben werden `PulseEvent` legt den Zustand des Ereignisses auf "nicht signalisiert" und gibt.

`PulseEvent` verwendet die zugrunde liegende Win32 `PulseEvent` -Funktion, die von einem asynchronen im Kernelmodus-Prozeduraufruf vorübergehend vom Zustand "Warten" entfernt werden kann. Aus diesem Grund `PulseEvent` nicht zuverlässig ist und nicht durch neue Anwendungen verwendet werden soll. Weitere Informationen finden Sie unter den [PulseEvent Funktion](/windows/desktop/api/winbase/nf-winbase-pulseevent).

##  <a name="resetevent"></a>  CEvent::ResetEvent

Legt den Zustand des Ereignisses, das "nicht signalisiert", bis explizit durch auf signalisiert festgelegt, die [SetEvent](#setevent) Member-Funktion.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Dies bewirkt, dass alle Threads, die auf dieses Ereignis warten möchte.

Diese Memberfunktion wird nicht durch automatische Ereignisse verwendet werden.

##  <a name="setevent"></a>  CEvent::SetEvent

Legt fest, dass den Status des Ereignisses, das signalisiert, alle wartenden Threads freigegeben.

```
BOOL SetEvent();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn das Ereignis auf manuell eingestellt ist, wird das Ereignis signalisiert, bis bleiben [ResetEvent](#resetevent) aufgerufen wird. Mehr als ein Thread kann in diesem Fall freigegeben werden. Wenn das Ereignis automatisch ist, bleibt das Ereignis signalisiert, bis ein einzelner Thread freigegeben wird. Das System wird der Zustand des Ereignisses auf "nicht signalisiert" festgelegt. Wenn keine Threads warten, bleibt der Zustand signalisiert, bis ein Thread freigegeben wird.

##  <a name="unlock"></a>  CEvent::Unlock

Gibt das Ereignisobjekt frei.

```
BOOL Unlock();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Thread das Ereignisobjekt und das Ereignis im Besitz ist ein automatisches Ereignis. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von Threads aufgerufen, die aktuell besitzen ein automatische-Ereignis, um ihn freigeben, wenn sie fertig sind, wenn die Sperrobjekt wiederverwendet werden. Wenn das Sperrobjekt nicht wiederverwendet werden, wird diese Funktion durch Sperren des Destruktors des Objekts aufgerufen werden.

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
