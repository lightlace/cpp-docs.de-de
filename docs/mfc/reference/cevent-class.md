---
title: CEvent Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
dev_langs: C++
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0646e703f172777817aa569fa28d3430624ccae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cevent-class"></a>CEvent-Klasse
Stellt ein Ereignis dar-ein Synchronisierungsobjekt, die es einem Thread ermöglicht anderen darüber zu benachrichtigen, die ein Ereignis aufgetreten ist.  
  
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
|[CEvent::PulseEvent](#pulseevent)|Legt das Ereignis verfügbar (signalisiert), wartenden Threads frei, und das Ereignis auf nicht verfügbar ("nicht signalisiert").|  
|[CEvent::ResetEvent](#resetevent)|Legt das Ereignis zur Verfügung ("nicht signalisiert").|  
|[CEvent::SetEvent](#setevent)|Legt das Ereignis für die (signalisierten) verfügbar, und alle wartenden Threads frei.|  
|[CEvent::Unlock](#unlock)|Gibt das Ereignisobjekt frei.|  
  
## <a name="remarks"></a>Hinweise  
 Ereignisse sind nützlich, wenn ein Thread seine Aufgabe ausführt wann muss. Beispielsweise muss ein Thread, der Daten an ein Datenarchiv kopiert darüber informiert werden, wenn neue Daten verfügbar sind. Mithilfe einer `CEvent` Objekt, das die Kopie-Thread zu benachrichtigen, wenn neue Daten verfügbar ist, werden der Thread seine Aufgabe so bald wie möglich ausführen kann.  
  
 `CEvent`Objekte verfügen über zwei Arten: Manuelles und automatisches.  
  
 Eine automatische `CEvent` Objekt wird automatisch in einen nicht signalisierten (nicht verfügbar) Zustand zurückkehrt, mindestens einen Thread freigegeben ist. Wird standardmäßig ein `CEvent` Objekt erfolgt automatisch, es sei denn, Sie übergeben `TRUE` für die `bManualReset` Parameter während der Erstellung.  
  
 Eine manuelle `CEvent` Objekt verbleibt im Status "festlegen, indem" [SetEvent](#setevent) oder [ResetEvent](#resetevent) , bis die andere Funktion aufgerufen wird. So erstellen eine manuelle `CEvent` Objekt, und übergeben `TRUE` für die `bManualReset` Parameter während der Erstellung.  
  
 Verwenden einer `CEvent` Objekt, das Erstellen der `CEvent` Objekt, wenn dies erforderlich ist. Geben Sie den Namen des Ereignisses, das Sie verwenden möchten, gewartet werden soll, und auch angeben, dass die Anwendung zunächst besitzen sollen. Sie können dann das Ereignis, wenn der Konstruktor gibt zugreifen. Rufen Sie [SetEvent](#setevent) , Signal (verfügbar machen) das Ereignisobjekt und rufen Sie dann [Unlock](#unlock) nach abgeschlossener gesteuerte Ressource zugreifen.  
  
 Eine alternative Methode für die Verwendung von `CEvent` Objekte ist die Verwendung eine Variablen des Typs hinzufügen `CEvent` als Datenmember der Klasse, die Sie steuern möchten. Während der Erstellung des Objekts kontrollierten, rufen Sie den Konstruktor von den `CEvent` -Datenmember und angegeben, ob das Ereignis ursprünglich signalisiert wird, und auch Specifythe Ereignisobjekt soll, den Namen des Ereignisses (wenn es über Prozess-verwendet werden soll Grenzen), und alle gewünschten Sicherheitsattribute.  
  
 Zugriff auf eine Ressource gesteuert, indem Sie eine `CEvent` Objekt auf diese Weise erstellen Sie zunächst eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) oder Typ [CMultiLock](../../mfc/reference/cmultilock-class.md) in die Zugriffsmethode der Ressource. Rufen Sie anschließend die `Lock` -Methode des Objekts Sperre (z. B. [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). Der Thread an diesem Punkt wird entweder Zugriff auf die Ressource, warten auf die Ressource freigegeben werden, und erhalten Zugriff oder warten Sie, bis die Ressource freigegeben wird, einen Timeout beendet und Fehler beim Zugriff auf die Ressource. In jedem Fall wurde die Ressource auf threadsichere Weise zugegriffen wurde. Aufrufen, um die Ressource freizugeben, `SetEvent` das Ereignisobjekt zu signalisieren und dann mithilfe der `Unlock` -Methode des Objekts Sperre (z. B. [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.  
  
 Weitere Informationen zur Verwendung von `CEvent` anzuzeigen, [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="cevent"></a>CEvent::CEvent  
 Erstellt einen benannten oder unbenannten `CEvent` Objekt.  
  
```  
CEvent(
    BOOL bInitiallyOwn = FALSE,  
    BOOL bManualReset = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bInitiallyOwn`  
 Wenn **"true"**, den Thread für die **CMultilock** oder `CSingleLock` Objekt aktiviert ist. Andernfalls müssen alle Threads, die Zugriff auf die Ressource endversatz warten.  
  
 *bManualReset*  
 Wenn **"true"**, gibt an, dass das Ereignisobjekt eines manuellen Ereignisses ist, andernfalls ist das Ereignisobjekt automatische Ereignis.  
  
 `lpszName`  
 Name des `CEvent`-Objekts. Muss angegeben werden, wenn das Objekt über Prozessgrenzen hinweg verwendet werden soll. Ein vorhandenes Ereignis mit dem Namen übereinstimmt, der Konstruktor erstellt ein neues `CEvent` Objekt, das das Ereignis mit diesem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf ein Ereignis ist übereinstimmt, schlägt die Erstellung fehl. Wenn **NULL**, wird der Name null sein.  
  
 `lpsaAttribute`  
 Die Sicherheitsattribute für das Ereignisobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder aufgehoben eine `CEvent` Objekt, das Erstellen einer [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Member-Funktionen.  
  
 So ändern Sie den Status des eine `CEvent` auf die Signalisierung Objekts (Threads müssen nicht warten), rufen Sie [SetEvent](#setevent) oder [PulseEvent](#pulseevent). Zum Festlegen des Status von einem `CEvent` Objekt auf "nicht signalisiert" (Threads warten müssen), rufen Sie [ResetEvent](#resetevent).  
  
> [!IMPORTANT]
>  Nach dem Erstellen der `CEvent` -Objekts [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex bereits noch nicht gab. Wenn das Mutex unerwartet vorhanden war, kann dies bedeuten, ein Rogue-Prozess ist squatting und möglicherweise beabsichtigten Mutex in böswilliger Absicht verwendet werden. In diesem Fall ist die empfohlene Vorgehensweise für die-Lösung auf das Handle geschlossen und fortgesetzt, als wäre es ein Fehler wurde beim Erstellen des Objekts.  
  
##  <a name="pulseevent"></a>CEvent::PulseEvent  
 Legt den Zustand des Ereignisses auf die Signalisierung (verfügbar), alle wartenden Threads frei und setzt sie auf "nicht signalisiert" (nicht verfügbar) automatisch zurück.  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Ereignis auf manuell eingestellt ist, werden alle wartenden Threads freigegeben ist, das Ereignis zu "nicht signalisiert", und `PulseEvent` zurückgibt. Das Ereignis automatisch ist, ein einzelnen Thread freigegeben ist, wird das Ereignis zu "nicht signalisiert", und `PulseEvent` zurückgibt.  
  
 Wenn keine Threads warten, oder keine Threads sofort freigegeben werden können `PulseEvent` legt den Zustand des Ereignisses auf "nicht signalisiert" fest und gibt zurück.  
  
 `PulseEvent`verwendet die zugrunde liegenden Win32 `PulseEvent` -Funktion, die von einem asynchronen Prozeduraufruf Kernel-Modus von den Wartezustand vorübergehend entfernt werden kann. Aus diesem Grund `PulseEvent` nicht zuverlässig ist und nicht durch neue Anwendungen verwendet werden. Weitere Informationen finden Sie unter der [PulseEvent Funktion](http://msdn.microsoft.com/library/windows/desktop/ms684914).  
  
##  <a name="resetevent"></a>CEvent::ResetEvent  
 Legt den Zustand des Ereignisses auf "nicht signalisiert", bis explizit festlegen von signalisiert der [SetEvent](#setevent) Memberfunktion.  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies bewirkt, dass alle Threads, die auf dieses Ereignis warten möchte.  
  
 Diese Memberfunktion wird durch automatische Ereignisse nicht verwendet.  
  
##  <a name="setevent"></a>CEvent::SetEvent  
 Legt fest, dass der Zustand des Ereignisses, das signalisiert, alle wartenden Threads freigegeben.  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Funktion erfolgreich war, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ereignis auf manuell eingestellt ist, wird das Ereignis signalisiert, bis bleiben [ResetEvent](#resetevent) aufgerufen wird. Mehrere Threads kann in diesem Fall aufgehoben werden. Wenn das Ereignis automatisch erfolgt, bleibt das Ereignis signalisiert, bis ein einziger Thread freigegeben wird. Das System wird der Zustand des Ereignisses auf "nicht signalisiert" festgelegt. Wenn keine Threads warten, bleibt der Zustand signalisiert, bis ein Thread freigegeben wird.  
  
##  <a name="unlock"></a>CEvent::Unlock  
 Gibt das Ereignisobjekt frei.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Thread der Besitzer das Ereignisobjekt und das Ereignis ist ein automatische Ereignis; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion heißt von Threads, die aktuell besitzen ein automatisches Ereignis, um ihn freizugeben, nachdem sie fertig sind, wenn ihre Sperrobjekt wiederverwendet werden. Wenn das Sperrenobjekt nicht wiederverwendet werden, wird diese Funktion von der Sperre Destruktor des Objekts aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

