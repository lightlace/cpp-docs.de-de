---
title: CSyncObject-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject class
- synchronization classes, CSyncObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a1f0c8ddfbfaf129bb18c14d36b998dd37d35899
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csyncobject-class"></a>CSyncObject-Klasse
Eine rein virtuelle Klasse, welche die Funktionalität bereitstellt, die alle Synchronisierungsobjekte in Win32 gemeinsam haben.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|Erstellt ein `CSyncObject`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|Erhält Zugriff auf das Synchronisierungsobjekt.|  
|[CSyncObject::Unlock](#unlock)|Erhält Zugriff auf das Synchronisierungsobjekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::operator HANDLE](#operator_handle)|Bietet Zugriff auf das Synchronisierungsobjekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|Das Handle für das zugrunde liegende Synchronisierungsobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class Library stellt mehrere Klassen, die von abgeleiteten `CSyncObject`. Dies sind [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), und [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Informationen zur Verwendung von die Synchronisierungsobjekte, finden Sie im Artikel [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="csyncobject"></a>CSyncObject::CSyncObject  
 Erstellt ein Synchronisierungsobjekt, das mit dem angegebenen Namen.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Parameter  
 `pstrName`  
 Der Name des Objekts. Wenn **NULL**, *PstrName* NULL.  
  
##  <a name="lock"></a>CSyncObject::Lock  
 Rufen Sie diese Funktion für den Zugriff auf die Ressource, die durch das Synchronisierungsobjekt gesteuert.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTimeout`  
 Gibt die Zeitspanne in Millisekunden, für die Synchronisierungsobjekt zur Verfügung stehen (signalisiert). Wenn **UNENDLICHE**, `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Synchronisierungsobjekt, das signalisiert wird, `Lock` wird erfolgreich abgeschlossen, und der Thread wird jetzt das Objekt besitzt. Ist das Synchronisierungsobjekt "nicht signalisiert" (nicht verfügbar), `Lock` wartet darauf, dass das Synchronisierungsobjekt bis zur Anzahl der Millisekunden, die im angegebenen signalisiert werden die *DwTimeOut* Parameter. Wenn das Synchronisierungsobjekt nicht innerhalb der angegebenen Zeitspanne signalisiert wird, `Lock` Fehler zurückgegeben.  
  
##  <a name="m_hobject"></a>CSyncObject::m_hObject  
 Das Handle für das zugrunde liegende Synchronisierungsobjekt.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>CSyncObject::operator HANDLE  
 Verwenden Sie diesen Operator das Handle des Abrufen der `CSyncObject` Objekt.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle des Synchronisierungsobjekts; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Handle verwenden, Windows-APIs direkt aufrufen.  
  
##  <a name="unlock"></a>CSyncObject::Unlock  
 Die Deklaration von `Unlock` ohne Parameter ist eine reine virtuelle Funktion und muss von der alle von abgeleiteten Klassen überschrieben werden `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Durch die standardmäßige Implementierung verwendet nicht.  
  
 `lpPrevCount`  
 Durch die standardmäßige Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Standardmäßige Implementierung gibt immer **TRUE**.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die standardmäßige Implementierung der Deklaration mit zwei Parametern immer **TRUE**. Diese Funktion wird aufgerufen, um den Zugriff auf das Synchronisierungsobjekt, das im Besitz des aufrufenden Threads freizugeben. Die zweite Deklaration wird für Synchronisierungsobjekte z. B. Semaphoren bereitgestellt, die mehr als ein Zugriff auf eine gesteuerte Ressource zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




