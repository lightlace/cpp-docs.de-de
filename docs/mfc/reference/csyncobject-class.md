---
title: CSyncObject Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcc5290b08b6a0b6159c1ba9b0b5b05d02a178ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122068"
---
# <a name="csyncobject-class"></a>CSyncObject-Klasse
Eine rein virtuelle Klasse, welche die Funktionalität bereitstellt, die alle Synchronisierungsobjekte in Win32 gemeinsam haben.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|Erstellt ein `CSyncObject`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|Verschafft sich Zugriff auf das Synchronisierungsobjekt.|  
|[CSyncObject::Unlock](#unlock)|Verschafft sich Zugriff auf das Synchronisierungsobjekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::operator HANDLE](#operator_handle)|Bietet Zugriff auf das Synchronisierungsobjekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|Das Handle an die zugrunde liegenden Synchronisierungsobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class Library stellt mehrere Klassen abgeleitet `CSyncObject`. Hierbei handelt es sich [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), und [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Informationen zum verwenden, die alle Synchronisierungsobjekte, finden Sie im Artikel [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="csyncobject"></a>  CSyncObject::CSyncObject  
 Erstellt ein Synchronisierungsobjekt, das mit dem angegebenen Namen.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Parameter  
 *pstrName*  
 Der Name des Objekts. Wenn der Wert NULL, *PstrName* NULL.  
  
##  <a name="lock"></a>  CSyncObject::Lock  
 Mit dieser Funktion wird für den Zugriff auf die Ressource, die durch das Synchronisierungsobjekt gesteuert.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeout*  
 Gibt die Zeitdauer in Millisekunden zu warten, bis das Synchronisierungsobjekt verfügbar sein (signalisiert). Wenn INFINITE `Lock` wird gewartet, bis das Objekt vor der Rückgabe signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Synchronisierungsobjekt, das signalisiert wird, `Lock` erfolgreich zurückgegeben wird und der Thread wird jetzt das Objekt besitzt. Ist das Synchronisierungsobjekt "nicht signalisiert" (nicht verfügbar), `Lock` wartet darauf, dass das Synchronisierungsobjekt bis zur Anzahl der Millisekunden, die im angegebenen signalisiert werden die *DwTimeOut* Parameter. Wenn das Synchronisierungsobjekt, das nicht in die angegebene Zeitspanne Signalisierung `Lock` Fehler zurückgegeben.  
  
##  <a name="m_hobject"></a>  CSyncObject::m_hObject  
 Das Handle an die zugrunde liegenden Synchronisierungsobjekt.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>  CSyncObject::operator HANDLE  
 Verwenden Sie diesen Operator das Handle des abzurufenden der `CSyncObject` Objekt.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle des Synchronisierungsobjekts; Andernfalls wird NULL verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Handle verwenden, Windows-APIs direkt aufrufen.  
  
##  <a name="unlock"></a>  CSyncObject::Unlock  
 Die Deklaration von `Unlock` ohne Parameter ist eine reine virtuelle Funktion, und muss von allen Klassen ableiten von überschrieben werden `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lCount*  
 Durch die standardmäßige Implementierung verwendet nicht.  
  
 *lpPrevCount*  
 Durch die standardmäßige Implementierung verwendet nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer die Standardimplementierung gibt "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung der Deklaration mit zwei Parametern immer gibt "true" zurück. Diese Funktion wird aufgerufen, um den Zugriff auf das Synchronisierungsobjekt, das im Besitz des aufrufenden Threads freizugeben. Die zweite Deklaration halber Synchronisierungsobjekte z. B. Semaphoren, die mehr als ein Zugriff auf eine gesteuerte Ressource zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



