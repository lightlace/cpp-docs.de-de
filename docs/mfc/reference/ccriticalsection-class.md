---
title: CCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, critical section
- CCriticalSection class
- critical sections
- synchronization classes, CCriticalSection class
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
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
ms.openlocfilehash: 25d4b124d089441503e9cb457e648695fc54660d
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccriticalsection-class"></a>CCriticalSection-Klasse
Stellt einen "kritischen Abschnitt" dar – ein Synchronisierungsobjekt, das jeweils einem Thread gleichzeitig Zugriff auf eine Ressource oder einen Codeabschnitt ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Erstellt ein `CCriticalSection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|Verwenden Sie für den Zugriff auf die `CCriticalSection` Objekt.|  
|[CCriticalSection::Unlock](#unlock)|Gibt das `CCriticalSection`-Objekt frei.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Ruft einen Zeiger auf die interne **CRITICAL_SECTION** Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|Ein **CRITICAL_SECTION** Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Kritische Abschnitte sind nützlich, wenn jeweils nur ein Thread erfolgen kann, um Daten oder eine andere gesteuerte Ressource zu ändern. Hinzufügen von Knoten zu einer verknüpften Liste ist beispielsweise ein Prozess, der nur von einem Thread zu einem Zeitpunkt werden darf. Mit einem `CCriticalSection` -Objekt, das die verknüpfte Liste steuern nur jeweils ein Thread auf die Liste zugreifen kann.  
  
> [!NOTE]
>  Die Funktionalität der `CCriticalSection` Klasse erfolgt durch eine tatsächliche Win32 **CRITICAL_SECTION** Objekt.  
  
 Kritische Abschnitte werden verwendet, anstatt Mutexe (finden Sie unter [CMutex](../../mfc/reference/cmutex-class.md)) Wenn Rendergeschwindigkeit wichtig ist und die Ressource wird nicht über Prozessgrenzen hinweg verwendet werden.  
  
 Es gibt zwei Methoden für die Verwendung einer `CCriticalSection` Objekt: eigenständige und eingebettete in einer Klasse.  
  
-   Eigenständige Methode für eine eigenständige `CCriticalSection` Objekt, das Erstellen der `CCriticalSection` Objekt, wenn es benötigt wird. Nach einer erfolgreichen Rückgabe aus dem Konstruktor, explizit sperren, das Objekt mit einem Aufruf von [Sperren](#lock). Rufen Sie [Unlock](#unlock) erfolgt beim Zugriff auf den kritischen Abschnitt. Diese Methode beim deutlicher an eine Person beim Lesen von Quellcodes, wird mehr fehleranfällig, wie Sie daran denken müssen, Sperren und entsperren den kritischen Abschnitt vor und nach dem Zugriff.  
  
     Eine bessere Lösung Methode ist die Verwendung der [CSingleLock](../../mfc/reference/csinglelock-class.md) Klasse. Verfügt auch über eine `Lock` und `Unlock` Methode, aber Sie brauchen zum Entsperren der Ressourcenanbieters, wenn eine Ausnahme auftritt.  
  
-   Embedded-Methode können Sie auch eine Klasse mit mehreren Threads freigeben, durch Hinzufügen einer `CCriticalSection`-Typ-Datenmember auf die Klasse und den Datenmember bei Bedarf zu sperren.  
  
 Weitere Informationen zur Verwendung von `CCriticalSection` Objekte finden Sie im Artikel [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 Erstellt ein `CCriticalSection`-Objekt.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder freigegeben ein `CCriticalSection` Objekt, einen [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperren](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Memberfunktionen. Wenn die `CCriticalSection` Objekt eigenständigen verwendet wird, rufen Sie seine [Unlock](#unlock) Member-Funktion, um es zu lösen.  
  
 Schlägt der Konstruktor zum Zuweisen des erforderlichen Arbeitsspeichers, eine Ausnahme Arbeitsspeichers (des Typs [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) wird automatisch ausgelöst.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CCriticalSection::Lock](#lock).  
  
##  <a name="lock"></a>CCriticalSection::Lock  
 Rufen Sie diese Memberfunktion zum Zugriff auf das Objekt des kritischen Abschnitts.  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTimeout`  
 `Lock`der Wert dieses Parameters wird ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `Lock`ist ein blockierender Aufruf, der erst Objekt des kritischen Abschnitts signalisiert wird, zurückgegeben wird (verfügbar).  
  
 Wenn zeitgesteuerte Wartevorgänge erforderlich sind, können Sie eine [CMutex](../../mfc/reference/cmutex-class.md) -Objekt anstelle einer `CCriticalSection` Objekt.  
  
 Wenn `Lock` nicht die erforderlichen Systemressourcen, eine Ausnahme Arbeitsspeichers Speicher (des Typs [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) wird automatisch ausgelöst.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die geschachtelte kritischen Abschnitt Ansatz durch Steuern des Zugriffs auf eine freigegebene Ressource (die statische `_strShared` Objekt) mithilfe eines gemeinsamen `CCriticalSection` Objekt. Die `SomeMethod` Funktion zeigt, wie eine freigegebene Ressource auf sichere Weise.  
  
 [!code-cpp[NVC_MFC_Utilities&#11;](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="m_sect"></a>CCriticalSection::m_sect  
 Enthält ein kritisches Abschnittsobjekt, mit dem alle `CCriticalSection` Methoden.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 Ruft eine **CRITICAL_SECTION** Objekt.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Zeiger auf die interne abzurufen **CRITICAL_SECTION** Objekt.  
  
##  <a name="unlock"></a>CCriticalSection::Unlock  
 Versionen der `CCriticalSection` Objekt von einem anderen Thread verwendet werden.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CCriticalSection` Objekt wurde von dem Thread gehört, und die Veröffentlichung erfolgreich war, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CCriticalSection` verwendeten eigenständigen `Unlock` muss aufgerufen werden, sofort nach Abschluss der Verwendung der Ressource durch den kritischen Abschnitt gesteuert. Wenn ein [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt verwendet wird, `CCriticalSection::Unlock` wird durch des Sperrobjekt aufgerufen `Unlock` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CCriticalSection::Lock](#lock).  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMutex-Klasse](../../mfc/reference/cmutex-class.md)

