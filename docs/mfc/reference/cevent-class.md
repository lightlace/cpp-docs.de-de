---
title: CEvent-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEvent
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, event
- synchronization classes, CEvent class
- CEvent class
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9edadeec87cf04ae6166c173c65463d1509eb1d8
ms.lasthandoff: 02/24/2017

---
# <a name="cevent-class"></a>CEvent-Klasse
Stellt ein Ereignis-ein Synchronisierungsobjekt, das es einem Thread ermöglicht anderen darüber zu benachrichtigen, die ein Ereignis aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CEvent : public CSyncObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEvent::CEvent](#cevent)|Erstellt ein `CEvent`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEvent::PulseEvent](#pulseevent)|Legt die verfügbaren (Signal), wartenden Threads frei, und das Ereignis zur Verfügung ("nicht signalisiert").|  
|[CEvent::ResetEvent](#resetevent)|Legt das-Ereignis zur Verfügung ("nicht signalisiert").|  
|[CEvent::SetEvent](#setevent)|Legt das-Ereignis für die (signalisiert) verfügbar, und alle wartenden Threads frei.|  
|[CEvent::Unlock](#unlock)|Gibt das Ereignisobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ereignisse sind hilfreich, wenn ein Thread bei seiner Aufgaben benötigen. Beispielsweise muss ein Thread, der Daten an ein Datenarchiv kopiert darüber informiert werden, wenn neue Daten verfügbar sind. Mithilfe einer `CEvent` -Objekt, das die kopieren-Thread zu benachrichtigen, wenn neue Daten verfügbar ist, werden der Thread seine Aufgabe so bald wie möglich ausführen kann.  
  
 `CEvent`Objekte verfügen über zwei Typen: manuelle und automatische.  
  
 Eine automatische `CEvent` Objekt wird automatisch in eine (nicht verfügbar) nicht signalisierten Zustand zurück, nachdem Sie mindestens einen Thread freigegeben wird. In der Standardeinstellung eine `CEvent` Objekt erfolgt automatisch, es sei denn, Sie übergeben `TRUE` für die `bManualReset` Parameter während der Erstellung.  
  
 Eine manuelle `CEvent` Objekt verbleibt im Status festlegen, indem Sie [SetEvent](#setevent) oder [ResetEvent](#resetevent) , bis die andere Funktion aufgerufen wird. Erstellen Sie eine manuelle `CEvent` Objekt, und übergeben `TRUE` für die `bManualReset` Parameter während der Erstellung.  
  
 Verwenden einer `CEvent` Objekt, das Erstellen der `CEvent` Objekt, wenn es erforderlich ist. Geben Sie den Namen des Ereignisses zu warten, und auch angeben, dass die Anwendung anfänglich zugeordnet werden soll. Sie können dann das Ereignis, wenn der Konstruktor gibt zugreifen. Rufen Sie [SetEvent](#setevent) auf Signal (verfügbar machen) die Ereignisobjekt und rufen dann [Unlock](#unlock) nach erfolgter gesteuerte Ressource zugreifen.  
  
 Eine alternative Methode für die Verwendung von `CEvent` Objekte ist die Verwendung eine Variablen des Typs hinzufügen `CEvent` als Datenmember der Klasse, die Sie steuern möchten. Während der Erstellung des Objekts kontrollierten, rufen Sie den Konstruktor von den `CEvent` -Datenmember und geben an, ob das Ereignis ursprünglich signalisiert wird, und auch Specifythe Ereignisobjekt werden soll, den Namen des Ereignisses (Wenn sie über Prozessgrenzen hinweg verwendet wird), und alle Sicherheitsattribute werden soll.  
  
 Zugriff auf eine Ressource gesteuert durch eine `CEvent` Objekt auf diese Weise erstellen Sie zunächst eine Variable des Typs [CSingleLock](../../mfc/reference/csinglelock-class.md) oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Access-Methode der Ressource. Rufen Sie dann die `Lock` -Methode des Sperren-Objekts (z. B. [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). Der Thread zu diesem Zeitpunkt wird entweder Zugriff auf die Ressource, warten auf die Ressource freigegeben werden und Zugriff oder warten Sie, bis die Ressource freigegeben werden, Timeout und zu einem Fehler beim Zugriff auf die Ressource. In jedem Fall ist die Ressource auf eine threadsichere Weise zugegriffen wurde. Um die Ressourcen freizugeben, rufen `SetEvent` signalisieren das Ereignisobjekt, und verwenden Sie dann die `Unlock` -Methode des Sperren-Objekts (z. B. [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), oder lassen Sie das Sperrobjekt außerhalb des gültigen Bereichs liegen.  
  
 Weitere Informationen zur Verwendung von `CEvent` Objekte finden Sie unter [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#45;](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities&#46;](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="a-nameceventa--ceventcevent"></a><a name="cevent"></a>CEvent::CEvent  
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
 Wenn **TRUE**, den Thread für die **CMultilock** oder `CSingleLock` -Objekt aktiviert ist. Andernfalls müssen alle Threads, die auf die Ressource zugreifen möchte warten.  
  
 *bManualReset*  
 Wenn **TRUE**, gibt an, dass das Ereignisobjekt eines manuellen Ereignisses ist, andernfalls ist das Ereignisobjekt ein automatisches Ereignis.  
  
 `lpszName`  
 Name des `CEvent`-Objekts. Muss angegeben werden, wenn das Objekt über Prozessgrenzen hinweg verwendet werden soll. Wenn Sie ein vorhandenes Ereignis mit dem Namen übereinstimmt, erstellt der Konstruktor ein neues `CEvent` Objekt, das das Ereignis mit dem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf ein Ereignis ist übereinstimmt, schlägt die Erstellung fehl. Wenn **NULL**, wird der Name null sein.  
  
 `lpsaAttribute`  
 Die Sicherheitsattribute für das Ereignisobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder freigegeben ein `CEvent` Objekt, einen [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperren](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Memberfunktionen.  
  
 So ändern Sie den Status einer `CEvent` auf die Signalisierung (Threads müssen nicht warten), rufen Sie [SetEvent](#setevent) oder [PulseEvent](#pulseevent). Zum Festlegen des Status von einem `CEvent` Objekt, das nicht signalisiert (Threads warten müssen), rufen Sie [ResetEvent](#resetevent).  
  
> [!IMPORTANT]
>  Nach dem Erstellen der `CEvent` -Objekts [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex noch die nicht vorhanden ist. Wenn der Mutex unerwartet vorhanden war, kann dies bedeuten, ein nicht autorisierten Prozess squatting ist und möglicherweise die Absicht, die den Mutex in böswilliger Absicht zu verwenden. In diesem Fall ist die empfohlene Vorgehensweise für die sicherheitsbewusste das Handle geschlossen und fortgesetzt, als wäre das Erstellen des Objekts ein Fehler aufgetreten.  
  
##  <a name="a-namepulseeventa--ceventpulseevent"></a><a name="pulseevent"></a>CEvent::PulseEvent  
 Legt den Zustand des Ereignisses auf signalisiert (verfügbar) und setzt sie auf "nicht signalisiert" (nicht verfügbar) automatisch alle wartenden Threads frei.  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Ereignis auf manuell eingestellt ist, werden alle wartenden Threads freigegeben, wird das Ereignis zu "nicht signalisiert", und `PulseEvent` gibt. Das Ereignis automatisch ist, ein einzelnen Thread freigegeben wird, wird das Ereignis zu "nicht signalisiert", und `PulseEvent` gibt.  
  
 Wenn keine Threads warten, oder keine Threads können, sofort freigegeben werden `PulseEvent` legt den Zustand des Ereignisses auf "nicht signalisiert" fest und gibt zurück.  
  
 `PulseEvent`Mithilfe der zugrunde liegende Win32- `PulseEvent` -Funktion, die von einem asynchronen im Kernelmodus aus den Wartezustand vorübergehend entfernt werden kann. Aus diesem Grund `PulseEvent` nicht zuverlässig ist und nicht durch neue Anwendungen verwendet werden. Weitere Informationen finden Sie unter der [PulseEvent Funktion](http://msdn.microsoft.com/library/windows/desktop/ms684914).  
  
##  <a name="a-namereseteventa--ceventresetevent"></a><a name="resetevent"></a>CEvent::ResetEvent  
 Legt den Zustand des Ereignisses auf nicht signalisiert, bis explizit signalisiert durch Festlegen der [SetEvent](#setevent) Member-Funktion.  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies bewirkt, dass alle Threads, die Zugriff auf dieses Ereignis warten möchte.  
  
 Diese Memberfunktion ist nicht durch automatische Ereignisse verwendet.  
  
##  <a name="a-nameseteventa--ceventsetevent"></a><a name="setevent"></a>CEvent::SetEvent  
 Legt den Zustand des Ereignisses, das signalisiert, alle wartenden Threads freigegeben.  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Funktion erfolgreich war, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ereignis auf manuell eingestellt ist, wird das Ereignis signalisiert, bis bleiben [ResetEvent](#resetevent) aufgerufen wird. Mehrere Threads kann in diesem Fall freigegeben werden. Wenn das Ereignis auf automatisch festgelegt ist, bleibt das Ereignis signalisiert, bis ein einzelner Thread freigegeben wird. Das System wird der Zustand des Ereignisses auf "nicht signalisiert" festgelegt. Wenn keine wartenden Threads vorhanden sind, bleibt der Zustand signalisiert, bis ein Thread freigegeben wird.  
  
##  <a name="a-nameunlocka--ceventunlock"></a><a name="unlock"></a>CEvent::Unlock  
 Gibt das Ereignisobjekt.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Thread das Ereignisobjekt und das Ereignis gehören ist ein automatisches Ereignis. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion heißt von Threads, die aktuell besitzen ein automatisches Ereignis, um ihn freizugeben, wenn sie fertig sind, wenn die Sperrobjekt wiederverwendet werden. Wenn das Sperrobjekt nicht wiederverwendet werden, wird diese Funktion durch das Sperrobjekt Destruktor aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


