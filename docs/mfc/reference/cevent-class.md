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
ms.openlocfilehash: fbf2d834163199107aae44bd5723ceff79e36f91
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506687"
---
# <a name="cevent-class"></a>CEvent-Klasse

Stellt ein Ereignis dar, bei dem es sich um ein Synchronisierungs Objekt handelt, das einem Thread ermöglicht, einen anderen zu benachrichtigen, dass ein Ereignis aufgetreten

## <a name="syntax"></a>Syntax

```
class CEvent : public CSyncObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CEvent:: CEvent](#cevent)|Erstellt ein `CEvent`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CEvent::PulseEvent](#pulseevent)|Legt das Ereignis auf verfügbar (signalisiert) fest, gibt wartende Threads frei und legt das Ereignis auf nicht verfügbar (nicht signalisiert) fest.|
|[CEvent::ResetEvent](#resetevent)|Legt das Ereignis auf "nicht verfügbar" (nicht signalisiert) fest.|
|[CEvent::SetEvent](#setevent)|Legt das Ereignis auf verfügbar (signalisiert) fest und gibt alle wartenden Threads frei.|
|[CEvent::Unlock](#unlock)|Gibt das Ereignis Objekt frei.|

## <a name="remarks"></a>Hinweise

Ereignisse sind nützlich, wenn ein Thread wissen muss, wann seine Aufgabe durchgeführt werden muss. Beispielsweise muss ein Thread, der Daten in ein Datenarchiv kopiert, benachrichtigt werden, wenn neue Daten verfügbar sind. Wenn Sie den `CEvent` Kopier Thread mithilfe eines-Objekts benachrichtigen, wenn neue Daten verfügbar sind, kann der Thread seine Aufgabe so schnell wie möglich ausführen.

`CEvent`-Objekte haben zwei Typen: manuell und automatisch.

Ein automatisches `CEvent` Objekt kehrt automatisch in einen nicht signalisierten Zustand (nicht verfügbar) zurück, nachdem mindestens ein Thread freigegeben wurde. Standardmäßig wird ein `CEvent` -Objekt automatisch ausgeführt, es `TRUE` sei denn, Sie übergeben bei der Erstellung für den *bManualReset* -Parameter.

Ein manuelles `CEvent` Objekt verbleibt in dem Zustand, der von [SetEvent](#setevent) oder [ResetEvent](#resetevent) festgelegt wird, bis die andere Funktion aufgerufen wird. Wenn Sie ein manuelles `CEvent` Objekt erstellen möchten, übergeben `TRUE` Sie für den `bManualReset` -Parameter während der Erstellung.

Um ein `CEvent` -Objekt zu verwenden, `CEvent` erstellen Sie das-Objekt, wenn es erforderlich ist. Geben Sie den Namen des Ereignisses an, auf das gewartet werden soll, und geben Sie außerdem an, dass die Anwendung das Ereignis anfänglich besitzen soll. Sie können dann auf das-Ereignis zugreifen, wenn der Konstruktor zurückgibt. Aufrufen von [SetEvent](#setevent) zum signalisieren (verfügbar machen) des Ereignis Objekts und anschließendes Aufrufen von [Unlock](#unlock) , wenn Sie mit dem Zugriff auf die kontrollierte Ressource abgeschlossen sind.

Eine alternative Methode zum verwenden `CEvent` von-Objekten besteht darin, der Klasse `CEvent` , die Sie steuern möchten, eine Variable vom Typ als Datenmember hinzuzufügen. Beim Erstellen des kontrollierten Objekts wird der Konstruktor des `CEvent` Datenmembers aufgerufen und angegeben, ob das Ereignis anfänglich signalisiert wird, und es wird auch der Typ des gewünschten Ereignis Objekts angegeben, der Name des Ereignisses (wenn es Prozess übergreifend verwendet wird). Grenzen) und alle gewünschten Sicherheits Attribute.

Um auf eine auf diese Weise von `CEvent` einem-Objekt gesteuerte Ressource zuzugreifen, erstellen Sie zunächst eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) , oder geben Sie [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Zugriffsmethode der Ressource ein. Anschließend wird die `Lock` -Methode des Lock-Objekts aufgerufen (z. b. [CMultiLock:: Lock](../../mfc/reference/cmultilock-class.md#lock)). An diesem Punkt erhält der Thread entweder Zugriff auf die Ressource, wartet, bis die Ressource freigegeben wird, und erhält Zugriff, oder er wartet darauf, dass die Ressource freigegeben wird, ein Timeout und kann nicht auf die Ressource zugreifen. In jedem Fall wurde auf Ihre Ressource Thread sicher zugegriffen. Um die Ressource freizugeben, `SetEvent` verwenden Sie, um das Ereignis Objekt zu signalisieren, `Unlock` und verwenden Sie dann die-Methode des Sperr Objekts (z. b. [CMultiLock:: Unlock](../../mfc/reference/cmultilock-class.md#unlock)), oder lassen Sie das Sperr Objekt den Gültigkeitsbereich verlassen.

Weitere Informationen zur Verwendung `CEvent` von Objekten finden [Sie unter Multithreading: Verwenden der Synchronisierungs Klassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="cevent"></a>CEvent:: CEvent

Erstellt ein benanntes `CEvent` oder Unbenanntes Objekt.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parameter

*bInitiallyOwn*<br/>
TRUE gibt an, dass der Thread `CMultilock` für `CSingleLock` das-Objekt oder das-Objekt aktiviert ist. Andernfalls müssen alle Threads, die auf die Ressource zugreifen möchten, warten.

*bManualReset*<br/>
TRUE gibt an, dass das Ereignis Objekt ein manuelles Ereignis ist, da das Ereignis Objekt andernfalls ein automatisches Ereignis ist.

*Wert*<br/>
Name des `CEvent`-Objekts. Muss angegeben werden, wenn das-Objekt über Prozess Grenzen hinweg verwendet wird. Wenn der Name mit einem vorhandenen Ereignis übereinstimmt, erstellt der Konstruktor `CEvent` ein neues-Objekt, das auf das-Ereignis dieses Namens verweist. Wenn der Name mit einem vorhandenen Synchronisierungs Objekt übereinstimmt, das kein Ereignis ist, tritt bei der Erstellung ein Fehler auf. Wenn der Wert NULL ist, ist der Name NULL.

*lpsaAttribute*<br/>
Sicherheits Attribute für das Ereignis Objekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) im Windows SDK.

### <a name="remarks"></a>Hinweise

`CEvent` Erstellen Sie ein [CMultiLock](../../mfc/reference/cmultilock-class.md) -oder [CSingleLock](../../mfc/reference/csinglelock-class.md) -Objekt, und rufen Sie seine [Lock](../../mfc/reference/csinglelock-class.md#lock) -und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) -Member-Funktionen auf, um auf ein-Objekt zuzugreifen

Um den Zustand eines `CEvent` -Objekts in "signalisiert" (Threads müssen nicht gewartet werden) zu ändern, wird " [SetEvent](#setevent) " oder " [PulseEvent](#pulseevent)" aufgerufen. Um den Zustand eines `CEvent` -Objekts auf nicht signalisiert festzulegen (Threads müssen warten), wenden Sie [ResetEvent](#resetevent)an.

> [!IMPORTANT]
>  Nachdem Sie das `CEvent` Objekt erstellt haben, verwenden Sie [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , um sicherzustellen, dass der Mutex nicht bereits vorhanden ist. Wenn der Mutex unerwartet vorhanden war, deutet dies möglicherweise darauf hin, dass ein nicht autorisierter Prozess besetzt wird und die Mutex böswillig verwenden könnte. In diesem Fall besteht das empfohlene sicherheitsbewusste Verfahren darin, das Handle zu schließen und den Vorgang fortzusetzen, als ob bei der Erstellung des Objekts ein Fehler aufgetreten ist.

##  <a name="pulseevent"></a>CEvent::P ulcevent

Legt den Zustand des Ereignisses auf "signalisiert (verfügbar)" fest, gibt alle wartenden Threads frei und setzt Sie automatisch auf "nicht signalisiert" (nicht verfügbar) zurück.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn das Ereignis manuell ist, werden alle wartenden Threads freigegeben, das Ereignis ist auf "nicht signalisiert" `PulseEvent` festgelegt, und es wird zurückgegeben. Wenn das Ereignis automatisch erfolgt, wird ein einzelner Thread freigegeben, das Ereignis ist auf "nicht signalisiert" `PulseEvent` festgelegt, und es wird zurückgegeben.

Wenn keine Threads warten oder sofort keine Threads freigegeben werden können, wird `PulseEvent` der Zustand des Ereignisses auf nicht signalisiert festgelegt, und es wird zurückgegeben.

`PulseEvent`verwendet die zugrunde liegende `PulseEvent` Win32-Funktion, die vorübergehend aus dem Wartezustand durch einen asynchronen Prozedur aufrufim Kernel Modus entfernt werden kann. `PulseEvent` Daher ist unzuverlässig und sollte von neuen Anwendungen nicht verwendet werden. Weitere Informationen finden Sie unter der [pulsetevent-Funktion](/windows/win32/api/winbase/nf-winbase-pulseevent).

##  <a name="resetevent"></a>CEvent:: rebuildervent

Legt den Zustand des Ereignisses auf "nicht signalisiert" fest, bis die Funktion " [SetEvent](#setevent) " explizit auf "signalisiert" festgelegt ist.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Dies bewirkt, dass alle Threads, die auf dieses Ereignis zugreifen möchten, warten.

Diese Member-Funktion wird von automatischen Ereignissen nicht verwendet.

##  <a name="setevent"></a>CEvent:: Log Vent

Legt den Zustand des Ereignisses auf signalisiert fest und gibt alle wartenden Threads frei.

```
BOOL SetEvent();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich war, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn das Ereignis manuell ist, bleibt das Ereignis signalisiert, bis [reantevent](#resetevent) aufgerufen wird. In diesem Fall können mehrere Threads freigegeben werden. Wenn das Ereignis automatisch erfolgt, bleibt das Ereignis signalisiert, bis ein einzelner Thread freigegeben wird. Das System legt dann den Status des Ereignisses auf "nicht signalisiert" fest. Wenn keine Threads warten, bleibt der Status signalisiert, bis ein Thread freigegeben wird.

##  <a name="unlock"></a>CEvent:: Unlock

Gibt das Ereignis Objekt frei.

```
BOOL Unlock();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Thread dem Ereignis Objekt gehört und das Ereignis ein automatisches Ereignis ist. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion wird von Threads aufgerufen, die derzeit ein automatisches Ereignis besitzen, um es freizugeben, wenn das Sperr Objekt wieder verwendet werden soll. Wenn das Lock-Objekt nicht wieder verwendet werden soll, wird diese Funktion vom Dekonstruktor des Lock-Objekts aufgerufen.

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
