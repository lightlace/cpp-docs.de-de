---
title: CMultiLock Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock class
- synchronization objects, access control
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: bf70a1c56ebef194efa179cf8504770e94111cd8
ms.lasthandoff: 04/01/2017

---
# <a name="cmultilock-class"></a>CMultiLock-Klasse
Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|Erstellt ein `CMultiLock`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|Bestimmt, ob eine bestimmte Synchronisierungsobjekt, das im Array gesperrt ist.|  
|[CMultiLock::Lock](#lock)|Wartet auf das Array von Synchronisierungsobjekten.|  
|[CMultiLock::Unlock](#unlock)|Gibt alle im Besitz befindlichen Synchronisierungsobjekte frei.|  
  
## <a name="remarks"></a>Hinweise  
 `CMultiLock`eine Basisklasse verfügt nicht über.  
  
 Der Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), und [CEvent](../../mfc/reference/cevent-class.md), erstellen Sie entweder eine **CMultiLock** oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt gewartet werden soll, und lassen das Synchronisierungsobjekt. Verwenden Sie **CMultiLock** Wenn mehrere Objekte, die Sie zu einem bestimmten Zeitpunkt verwenden konnte. Verwendung `CSingleLock` Wenn müssen Sie nur auf ein Objekt zu einem Zeitpunkt zu warten.  
  
 Verwenden einer **CMultiLock** Objekt, das zuerst erstellt ein Array von die Synchronisierungsobjekte, die auf das gewartet werden soll. Rufen Sie als Nächstes die **CMultiLock** Objektkonstruktor innerhalb einer Memberfunktion in der gesteuerte Ressource-Klasse. Rufen Sie anschließend die [Sperre](#lock) Member-Funktion, um festzustellen, ob eine Ressource verfügbar ist (signalisiert). Wenn eine ist, fahren Sie mit dem Rest der Memberfunktion. Wenn keine Ressource verfügbar ist, warten Sie, bis eine angegebene Zeitspanne für eine Ressource freigegeben wird, oder Fehler zurück. Rufen Sie nach dem Verwenden einer Ressource abgeschlossen ist, entweder die [Unlock](#unlock) funktioniert, wenn die **CMultiLock** Objekt ist, erneut verwendet werden, oder die **CMultiLock** Objekt zerstört werden.  
  
 **CMultiLock** Objekte sind besonders hilfreich, wenn ein Thread eine große Anzahl von `CEvent` Objekten kann es zu reagieren. Erstellen Sie ein Array, das alle enthält die `CEvent` Zeiger, und rufen `Lock`. Dadurch wird den Thread wartet, bis eines der Ereignisse signalisiert wird.  
  
 Weitere Informationen zur Verwendung von **CMultiLock** Objekte finden Sie im Artikel [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CMultiLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="cmultilock"></a>CMultiLock::CMultiLock  
 Erstellt eine **CMultiLock** Objekt.  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `ppObjects`  
 Array von Zeigern, die alle Synchronisierungsobjekte, auf die gewartet werden. Nicht mit **NULL**.  
  
 `dwCount`  
 Anzahl der Objekte in `ppObjects`. Muss größer als 0 sein.  
  
 `bInitialLock`  
 Gibt an, ob zunächst versuchen, auf die angegebenen Objekte zuzugreifen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, nachdem Sie das Array von Synchronisierungsobjekten, auf die gewartet werden erstellt. Sie wird in der Regel aus vom Thread aufgerufen, die auf eines der Synchronisierungsobjekte auf das Freiwerden warten müssen.  
  
##  <a name="islocked"></a>CMultiLock::IsLocked  
 Bestimmt, ob das angegebene Objekt "nicht signalisiert" (nicht verfügbar).  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>Parameter  
 *dwItem*  
 Der Index im Array von Objekten, die für das Objekt, dessen Status abgefragt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Objekt gesperrt ist; andernfalls 0.  
  
##  <a name="lock"></a>CMultiLock::Lock  
 Mit dieser Funktion können Sie Zugriff auf eine oder mehrere Ressourcen gesteuert durch die Synchronisierungsobjekte, die **CMultiLock** Konstruktor.  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeOut*  
 Gibt die Zeitdauer Synchronisierungsobjekts Protokollpuffers warten (signalisiert). Wenn **UNENDLICHE**, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.  
  
 `bWaitForAll`  
 Gibt an, ob alle Objekte, die auf die gewartet zur gleichen Zeit vor der Rückgabe signalisiert werden müssen. Wenn **"false"**, `Lock` zurück, wenn die Objekte, auf die gewartet signalisiert wird.  
  
 `dwWakeMask`  
 Gibt andere Bedingungen, die zulässig sind, die Wartezeit abgebrochen. Eine vollständige Liste der verfügbaren Optionen für diesen Parameter finden Sie unter [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `Lock` fehlschlägt, wird - 1. Im Erfolgsfall gibt es einen der folgenden Werte zurück:  
  
-   Zwischen **WAIT_OBJECT_0** und **WAIT_OBJECT_0** + (Anzahl der Objekte - 1)  
  
     Wenn `bWaitForAll` ist **"true"**, werden alle Objekte (verfügbar) signalisiert. Wenn `bWaitForAll` ist **"false"**, den Rückgabewert - **WAIT_OBJECT_0** steht der Index im Array von Objekten des Objekts, das signalisiert wird, ().  
  
- **WAIT_OBJECT_0** + (Anzahl der Objekte)  
  
     Ein Ereignis, das im angegebenen `dwWakeMask` steht in der Eingabewarteschlange des Threads.  
  
-   Zwischen **WAIT_ABANDONED_0** und **WAIT_ABANDONED_0** + (Anzahl der Objekte - 1)  
  
     Wenn `bWaitForAll` ist **"true"**, alle Objekte signalisiert sind und mindestens eines der Objekte ist ein abgebrochenes Mutex-Objekt. Wenn `bWaitForAll` ist **"false"**, den Rückgabewert - **WAIT_ABANDONED_0** ist der Index im Array von Objekten von den abgebrochenes Mutex-Objekt, das den Wartevorgang erfüllt hat.  
  
- **WAIT_TIMEOUT**  
  
     Das Timeoutintervall, die im angegebenen *DwTimeOut* erfolglos den Wartevorgang abgelaufen ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bWaitForAll` ist **"true"**, `Lock` wird erfolgreich zurückgegeben, sobald die Synchronisierungsobjekte gleichzeitig signalisiert werden. Wenn `bWaitForAll` ist **"false"**, `Lock` wird zurückgegeben, sobald eine oder mehrere der Synchronisierungsobjekte signalisiert wird.  
  
 Wenn `Lock` ist nicht in der Lage, Rückgaben unverzüglich, wartet es nicht mehr als die Anzahl der Millisekunden, die im angegebenen der *DwTimeOut* Parameter vor der Rückgabe. Wenn *DwTimeOut* ist **UNENDLICHE**, `Lock` wird erst zurückgegeben, Zugriff auf ein Objekt erzielt wird, oder eine Bedingung angegeben wird, `dwWakeMask` erfüllt wurde. Andernfalls gilt: Wenn `Lock` wurde ein Synchronisierungsobjekt abrufen können, wird zurückgegeben, die erfolgreich; Wenn nicht der Fall, wird Fehler zurückgegeben.  
  
##  <a name="unlock"></a>CMultiLock::Unlock  
 Gibt das Synchronisierungsobjekt, das im Besitz von `CMultiLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Anzahl der Verweis zählt um freizugeben. Muss größer als 0 sein. Wenn die angegebene Menge Verweiszählerwert des Objekts überschreitet die maximale Anzahl führen würde, die Anzahl die nicht geändert, und die Funktion gibt **"false"**.  
  
 `lPrevCount`  
 Zeigt auf eine Variable, um die vorherige Anzahl für das Synchronisierungsobjekt zu empfangen. Wenn **NULL**, die vorherige Anzahl nicht zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem Sie `CMultiLock`den Destruktor.  
  
 Die erste Form der `Unlock` versucht, die von verwalteten Synchronisierungsobjekts Entsperren `CMultiLock`. Die zweite Form der `Unlock` versucht zum Entsperren der `CSemaphore` Objekte, die im Besitz von `CMultiLock`. Wenn `CMultiLock` besitzt eine nicht gesperrte `CSemaphore` -Objekt gibt die Funktion **"false"**ist, andernfalls gibt **"true"**. `lCount`und `lpPrevCount` stimmen exakt mit den Parametern des [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). Die zweite Form der `Unlock` selten gilt für Situationen multilock.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




