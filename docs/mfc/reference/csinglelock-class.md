---
title: CSingleLock-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock class
- threading [MFC], access control
- synchronization objects, access control
- threading [MFC], synchronization
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b1efc2daf1c3714446223cc69f9cc2a6a3401173
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csinglelock-class"></a>CSingleLock-Klasse
Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|Erstellt ein `CSingleLock`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|Bestimmt, ob das Objekt gesperrt ist.|  
|[CSingleLock::Lock](#lock)|Wartet auf ein Synchronisierungsobjekt.|  
|[CSingleLock::Unlock](#unlock)|Gibt ein Synchronisierungsobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CSingleLock`eine Basisklasse keinen.  
  
 Um der Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), und [CEvent](../../mfc/reference/cevent-class.md), müssen Sie entweder Erstellen einer `CSingleLock` oder [CMultiLock](../../mfc/reference/cmultilock-class.md) Objekt gewartet werden soll, und lassen das Synchronisierungsobjekt. Verwendung `CSingleLock` Wenn müssen Sie nur auf ein Objekt zu einem Zeitpunkt zu warten. Verwenden Sie **CMultiLock** Wenn mehrere Objekte, die Sie zu einem bestimmten Zeitpunkt verwenden können.  
  
 Verwenden einer `CSingleLock` Objekt, dessen Konstruktor innerhalb einer Memberfunktion in der gesteuerte Ressource-Klasse aufrufen. Rufen Sie dann die [IsLocked](#islocked) Member-Funktion, um festzustellen, ob die Ressource verfügbar ist. Wenn dies der Fall, fahren Sie mit den Rest der Memberfunktion. Wenn die Ressource nicht verfügbar ist, warten Sie, bis eine bestimmte Zeitspanne für die Ressource freigegeben werden oder zurückgeben Sie einen Fehler. Rufen Sie nach Abschluss der Verwendung der Ressource entweder der [Unlock](#unlock) ausgeführt werden, wenn der `CSingleLock` Ziel besteht darin, erneut verwendet werden, oder zulassen, die `CSingleLock` Objekt zerstört werden.  
  
 `CSingleLock`Objekte erfordern das Vorhandensein eines Objekts abgeleitet [CSyncObject](../../mfc/reference/csyncobject-class.md). Dies ist normalerweise ein Datenmember der gesteuerte Ressource-Klasse. Weitere Informationen zur Verwendung von `CSingleLock` Objekte finden Sie im Artikel [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CSingleLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="csinglelock"></a>CSingleLock::CSingleLock  
 Erstellt ein `CSingleLock`-Objekt.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `pObject`  
 Verweist auf das Synchronisierungsobjekt zugegriffen werden. Nicht **NULL**.  
  
 `bInitialLock`  
 Gibt an, ob zunächst versuchen, Zugriff auf das angegebene Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aus einer Access-Memberfunktion der gesteuerte Ressource aufgerufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities Nr.&19;](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>CSingleLock::IsLocked  
 Bestimmt, ob das Objekt zugeordnete der `CSingleLock` Objekt ist "nicht signalisiert" (nicht verfügbar).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt gesperrt ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&20;](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>CSingleLock::Lock  
 Rufen Sie diese Funktion für den Zugriff auf die Ressource, die vom Synchronisierungsobjekt gesteuert der `CSingleLock` Konstruktor.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeOut*  
 Gibt die Wartezeit für das Synchronisierungsobjekt verfügbar sein (signalisiert). Wenn **UNENDLICHE**, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Synchronisierungsobjekt, das signalisiert wird, `Lock` wird erfolgreich abgeschlossen, und der Thread wird jetzt das Objekt besitzt. Ist das Synchronisierungsobjekt "nicht signalisiert" (nicht verfügbar), `Lock` wartet darauf, dass das Synchronisierungsobjekt bis zur Anzahl der Millisekunden, die im angegebenen signalisiert werden die *DwTimeOut* Parameter. Wenn das Synchronisierungsobjekt nicht innerhalb der angegebenen Zeitspanne signalisiert wird, `Lock` Fehler zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>CSingleLock::Unlock  
 Gibt das Synchronisierungsobjekt, das im Besitz von `CSingleLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Anzahl der Zugriffe auf freigeben. Muss größer als 0 sein. Wenn die angegebene Menge Verweiszählerwert des Objekts, das Maximum überschritten würde, die Anzahl die nicht geändert, und die Funktion gibt **FALSE**.  
  
 `lPrevCount`  
 Verweist auf eine Variable, die die vorherige Anzahl von Synchronisierungsobjekts empfangen. Wenn **NULL**, die vorherige Anzahl nicht zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem `CSingleLock`Destruktor.  
  
 Wenn Sie mehr als eine Access-Zähler eines Semaphors freigeben müssen, verwenden Sie die zweite Form der `Unlock` und die Anzahl der Zugriffe auf die Version angeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMultiLock-Klasse](../../mfc/reference/cmultilock-class.md)

