---
title: CMultiLock-Klasse | Microsoft-Dokumentation
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a58d59d8e4d7a1c542dee80295dd8eef6c8be338
ms.lasthandoff: 02/24/2017

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
|[CMultiLock::Unlock](#unlock)|Gibt alle Synchronisierungsobjekte im Besitz befindlichen frei.|  
  
## <a name="remarks"></a>Hinweise  
 `CMultiLock`eine Basisklasse keinen.  
  
 Der Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), und [CEvent](../../mfc/reference/cevent-class.md), erstellen Sie entweder eine **CMultiLock** oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt gewartet werden soll, und lassen das Synchronisierungsobjekt. Verwenden Sie **CMultiLock** Wenn mehrere Objekte, die Sie zu einem bestimmten Zeitpunkt verwenden können. Verwendung `CSingleLock` Wenn müssen Sie nur auf ein Objekt zu einem Zeitpunkt zu warten.  
  
 Verwenden einer **CMultiLock** Objekt erstellen Sie zunächst ein Array von die Synchronisierungsobjekte, die auf das gewartet werden soll. Anschließend rufen Sie die **CMultiLock** Objektkonstruktor innerhalb einer Memberfunktion in der gesteuerte Ressource-Klasse. Rufen Sie dann die [Sperren](#lock) Member-Funktion, um festzustellen, ob eine Ressource verfügbar ist (signalisiert). Wenn eine ist, fahren Sie mit dem Rest der Memberfunktion. Wenn keine Ressource verfügbar ist, warten Sie, bis eine bestimmte Zeitspanne für eine Ressource freigegeben werden oder zurückgeben Sie einen Fehler. Rufen Sie nach Abschluss der Verwendung einer Ressource entweder die [Unlock](#unlock) funktioniert, wenn die **CMultiLock** Ziel besteht darin, erneut verwendet werden, oder zulassen, die **CMultiLock** Objekt zerstört werden.  
  
 **CMultiLock** Objekte sind besonders hilfreich, wenn ein Thread eine große Anzahl von `CEvent` Objekten kann es zu reagieren. Erstellen Sie ein Array mit allen der `CEvent` Zeiger, und rufen `Lock`. Dadurch wird den Thread wartet, bis eines der Ereignisse signalisiert wird.  
  
 Weitere Informationen zur Verwendung von **CMultiLock** Objekte finden Sie im Artikel [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CMultiLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="a-namecmultilocka--cmultilockcmultilock"></a><a name="cmultilock"></a>CMultiLock::CMultiLock  
 Erstellt eine **CMultiLock** Objekt.  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `ppObjects`  
 Array von Zeigern auf die Synchronisierungsobjekte, auf die gewartet werden soll. Nicht **NULL**.  
  
 `dwCount`  
 Anzahl der Objekte in `ppObjects`. Muss größer als 0 sein.  
  
 `bInitialLock`  
 Gibt an, ob zunächst versuchen, auf die angegebenen Objekte zuzugreifen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, nachdem das Array von Synchronisierungsobjekte, auf die gewartet. In der Regel ist von dem Thread aufgerufen, die für eines der Synchronisierungsobjekte zur Verfügung warten muss.  
  
##  <a name="a-nameislockeda--cmultilockislocked"></a><a name="islocked"></a>CMultiLock::IsLocked  
 Bestimmt, ob das angegebene Objekt nicht signalisiert ist (nicht verfügbar).  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>Parameter  
 *dwItem*  
 Der Index im Array von Objekten zurück, die das Objekt, dessen Status abgefragt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Objekt gesperrt ist; andernfalls 0.  
  
##  <a name="a-namelocka--cmultilocklock"></a><a name="lock"></a>CMultiLock::Lock  
 Rufen Sie diese Funktion für den Zugriff auf eine oder mehrere Ressourcen gesteuert durch die Synchronisierungsobjekte, die **CMultiLock** Konstruktor.  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeOut*  
 Gibt die Wartezeit für das Synchronisierungsobjekt verfügbar sein (signalisiert). Wenn **UNENDLICHE**, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.  
  
 `bWaitForAll`  
 Gibt an, ob alle Objekte, auf die gewartet zur gleichen Zeit vor der Rückgabe signalisiert werden müssen. Wenn **FALSE**, `Lock` zurück, wenn eines der Objekte, auf die gewartet signalisiert wird.  
  
 `dwWakeMask`  
 Gibt andere Situationen, die den Wartevorgang abgebrochen. Eine vollständige Liste der verfügbaren Optionen für diesen Parameter, finden Sie unter [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `Lock` fehlschlägt, wird – 1. Bei erfolgreicher Ausführung gibt die folgenden Werte zurück:  
  
-   Zwischen **WAIT_OBJECT_0** und **WAIT_OBJECT_0** + (Anzahl der Objekte – 1)  
  
     Wenn `bWaitForAll` ist **TRUE**, werden alle Objekte (verfügbar) signalisiert. Wenn `bWaitForAll` ist **FALSE**, der Rückgabewert – **WAIT_OBJECT_0** ist der Index im Array von Objekten des Objekts, das signalisiert wird (verfügbar).  
  
- **WAIT_OBJECT_0** + (Anzahl der Objekte)  
  
     Ein Ereignis im angegebenen `dwWakeMask` steht in der Eingabewarteschlange des Threads.  
  
-   Zwischen **WAIT_ABANDONED_0** und **WAIT_ABANDONED_0** + (Anzahl der Objekte – 1)  
  
     Wenn `bWaitForAll` ist **TRUE**alle Objekte signalisiert werden und mindestens eines der Objekte ist ein abgebrochenes Mutex-Objekt. Wenn `bWaitForAll` ist **FALSE**, der Rückgabewert – **WAIT_ABANDONED_0** ist der Index im Array von Objekten des abgebrochenen Mutex-Objekt, das den Wartevorgang erfüllt hat.  
  
- **WAIT_TIMEOUT**  
  
     Das Timeoutintervall in angegebenen *DwTimeOut* erfolglos den Wartevorgang abgelaufen ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bWaitForAll` ist **TRUE**, `Lock` erfolgreich zurückgegeben wird, als die Synchronisierungsobjekte gleichzeitig signalisiert werden. Wenn `bWaitForAll` ist **FALSE**, `Lock` zurück, sobald eine oder mehrere der Synchronisierungsobjekte signalisiert wird.  
  
 Wenn `Lock` kann nicht sofort zurückkehren, wartet es nicht mehr als die angegebene Anzahl von Millisekunden die *DwTimeOut* Parameter vor der Rückgabe. Wenn *DwTimeOut* ist **UNENDLICHE**, `Lock` wird erst zurückgegeben, Zugriff auf ein Objekt erlangt ist oder eine Bedingung angegeben `dwWakeMask` wurde erreicht. Andernfalls gilt: Wenn `Lock` wurde ein Synchronisierungsobjekt abrufen können, wird zurückgegeben, die erfolgreich, wenn nicht, wird Fehler zurückgegeben.  
  
##  <a name="a-nameunlocka--cmultilockunlock"></a><a name="unlock"></a>CMultiLock::Unlock  
 Gibt das Synchronisierungsobjekt, das im Besitz von `CMultiLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Anzahl der Verweis zählt zum Freigeben. Muss größer als 0 sein. Wenn die angegebene Menge Verweiszählerwert des Objekts, das Maximum überschritten würde, die Anzahl die nicht geändert, und die Funktion gibt **FALSE**.  
  
 `lPrevCount`  
 Verweist auf eine Variable, die die vorherige Anzahl für das Synchronisierungsobjekt zu erhalten. Wenn **NULL**, die vorherige Anzahl nicht zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem `CMultiLock`Destruktor.  
  
 Die erste Form der `Unlock` versucht, die von verwalteten Synchronisierungsobjekts Entsperren `CMultiLock`. Die zweite Form der `Unlock` versucht, nicht Entsperren der `CSemaphore` Objekte `CMultiLock`. Wenn `CMultiLock` besitzt eine nicht gesperrte `CSemaphore` -Objekt gibt die Funktion **FALSE**ist, andernfalls wird **TRUE**. `lCount`und `lpPrevCount` sind genau identisch mit den Parametern des [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). Die zweite Form der `Unlock` ist nur selten auf multilock Situationen anwendbar.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




