---
title: CSingleLock Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs: C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0dd07d79c97a9fb3368d20ee68df2332ba7ce5cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[CSingleLock::Unlock](#unlock)|Gibt ein Synchronisierungsobjekt frei.|  
  
## <a name="remarks"></a>Hinweise  
 `CSingleLock`eine Basisklasse verfügt nicht über.  
  
 Damit der Synchronisierungsklassen [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), und [CEvent](../../mfc/reference/cevent-class.md), müssen Sie erstellen entweder eine `CSingleLock` oder [CMultiLock](../../mfc/reference/cmultilock-class.md) Objekt gewartet werden soll, und lassen das Synchronisierungsobjekt. Verwendung `CSingleLock` Wenn müssen Sie nur auf ein Objekt zu einem Zeitpunkt zu warten. Verwenden Sie **CMultiLock** Wenn mehrere Objekte, die Sie zu einem bestimmten Zeitpunkt verwenden konnte.  
  
 Verwenden einer `CSingleLock` Objekt, dessen Konstruktor innerhalb einer Memberfunktion in der gesteuerte Ressource Klasse aufrufen. Rufen Sie anschließend die [IsLocked](#islocked) Member-Funktion, um festzustellen, ob die Ressource verfügbar ist. Wenn dies der Fall, fahren Sie mit der Rest der Memberfunktion. Wenn die Ressource nicht verfügbar ist, warten Sie, bis eine angegebene Zeitspanne für die Ressource freigegeben wird, oder Fehler zurück. Nach der Verwendung der Ressource abgeschlossen ist, rufen Sie entweder die [Unlock](#unlock) funktioniert, wenn die `CSingleLock` Objekt ist, erneut verwendet werden, oder die `CSingleLock` Objekt zerstört werden.  
  
 `CSingleLock`Objekte erfordern das Vorhandensein eines Objekts abgeleitet [CSyncObject](../../mfc/reference/csyncobject-class.md). Dies ist normalerweise ein Datenmember der Klasse für die gesteuerte Ressource. Weitere Informationen zur Verwendung von `CSingleLock` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
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
 Verweist auf das Synchronisierungsobjekt zugegriffen werden. Nicht mit **NULL**.  
  
 `bInitialLock`  
 Gibt an, ob zunächst versucht, Zugriff auf das angegebene Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird im Allgemeinen aus einer Access-Memberfunktion der gesteuerte Ressource aufgerufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>CSingleLock::IsLocked  
 Bestimmt, ob das Objekt zugeordnet der `CSingleLock` Objekt ist "nicht signalisiert" (nicht verfügbar).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Objekt gesperrt ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>CSingleLock::Lock  
 Mit dieser Funktion wird für den Zugriff auf die Ressource gesteuert durch die bereitgestellten Synchronisierungsobjekt, das die `CSingleLock` Konstruktor.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeOut*  
 Gibt die Zeitdauer Synchronisierungsobjekts Protokollpuffers warten (signalisiert). Wenn **UNENDLICHE**, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Synchronisierungsobjekt, das signalisiert wird, `Lock` erfolgreich zurückgegeben wird und der Thread wird jetzt das Objekt besitzt. Ist das Synchronisierungsobjekt "nicht signalisiert" (nicht verfügbar), `Lock` wartet darauf, dass das Synchronisierungsobjekt bis zur Anzahl der Millisekunden, die im angegebenen signalisiert werden die *DwTimeOut* Parameter. Wenn das Synchronisierungsobjekt, das nicht in die angegebene Zeitspanne Signalisierung `Lock` Fehler zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
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
 Die Anzahl der Zugriffe auf freizugeben. Muss größer als 0 sein. Wenn die angegebene Menge Verweiszählerwert des Objekts überschreitet die maximale Anzahl führen würde, die Anzahl die nicht geändert, und die Funktion gibt **"false"**.  
  
 `lPrevCount`  
 Zeigt auf eine Variable, um die vorherige Anzahl des Synchronisierungsobjekts empfangen. Wenn **NULL**, die vorherige Anzahl nicht zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem Sie `CSingleLock`den Destruktor.  
  
 Wenn Sie mehrere Zugriffsversuche ein Semaphor freigeben müssen, verwenden Sie die zweite Form der `Unlock` und geben Sie die Anzahl der Zugriffe auf freizugeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMultiLock-Klasse](../../mfc/reference/cmultilock-class.md)
