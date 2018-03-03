---
title: CCriticalSection Klasse | Microsoft Docs
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
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16364843ca5d85181b84e56f56b43ca4856a1667
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccriticalsection-class"></a>CCriticalSection-Klasse
Stellt einen "kritischen Abschnitt" – ein Synchronisierungsobjekt, das jeweils einem Thread zu einem Zeitpunkt auf eine Ressource oder einen Codeabschnitt ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>Member  
  
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
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Ruft einen Zeiger auf das interne **CRITICAL_SECTION** Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|Ein **CRITICAL_SECTION** Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Kritische Abschnitte sind nützlich, wenn nur ein Thread zu einem Zeitpunkt erfolgen kann, um Daten oder eine andere gesteuerte Ressource zu ändern. Hinzufügen von Knoten auf eine verknüpfte Liste wird z. B. ein Prozess, der nur von einem Thread zu einem Zeitpunkt zugelassen werden soll. Mithilfe einer `CCriticalSection` Objekt, das die verknüpfte Liste, zu steuern, nur einen Thread zu einem Zeitpunkt zur Liste zugreifen kann.  
  
> [!NOTE]
>  Die Funktionalität der `CCriticalSection` Klasse erfolgt durch einen tatsächlichen Win32 **CRITICAL_SECTION** Objekt.  
  
 Kritische Abschnitte werden verwendet, anstatt Mutexe (finden Sie unter [CMutex](../../mfc/reference/cmutex-class.md)) Wenn Geschwindigkeit ist wichtig, und die Ressource wird nicht über Prozessgrenzen hinweg verwendet werden.  
  
 Es gibt zwei Methoden für die Verwendung einer `CCriticalSection` Objekt: eigenständige und eingebettete in einer Klasse.  
  
-   Eigenständige Methode, um eine eigenständige verwenden `CCriticalSection` Objekt, das Erstellen der `CCriticalSection` Objekt, wenn es benötigt wird. Nach einer erfolgreichen Rückgabe aus dem Konstruktor, Sperren Sie explizit das Objekt mit einem Aufruf von [Sperre](#lock). Rufen Sie [Unlock](#unlock) Sie anschließend den Zugriff auf den kritischen Abschnitt. Diese Methode beim besseres an eine Person beim Lesen von Quellcodes, wird mehr fehleranfällig, wie Sie wissen müssen, zum Sperren und Entsperren des kritischen Abschnitts vor und nach dem Zugriff.  
  
     Mehr bevorzugte Methode ist die Verwendung der [CSingleLock](../../mfc/reference/csinglelock-class.md) Klasse. Sie hat auch ein `Lock` und `Unlock` -Methode, aber Sie müssen keine Gedanken machen, Entsperren die Ressource aus, wenn eine Ausnahme auftritt.  
  
-   Eingebettete Methode können Sie auch eine Klasse mit mehreren Threads freigeben, durch Hinzufügen einer `CCriticalSection`-Typ-Datenmember auf die Klassen und Sperren das Datenelement bei Bedarf.  
  
 Weitere Informationen zur Verwendung von `CCriticalSection` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Zugreifen oder aufgehoben eine `CCriticalSection` Objekt, das Erstellen einer [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Memberfunktionen. Wenn die `CCriticalSection` Objekt eigenständigen verwendet wird, rufen Sie die [Unlock](#unlock) Memberfunktion, diese freizugeben.  
  
 Fällt der Konstruktor zum Belegen des erforderlichen Speichers, eine Speicherausnahme (vom Typ [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) wird automatisch ausgelöst.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CCriticalSection::Lock](#lock).  
  
##  <a name="lock"></a>CCriticalSection::Lock  
 Rufen Sie diese Memberfunktion zum Zugriff auf die kritischen Abschnittsobjekt ein.  
  
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
 `Lock`ist ein blockierender Aufruf, der erst, dass Sie die kritischen Abschnittsobjekt signalisiert wird zurückgegeben werden (verfügbar).  
  
 Wenn zeitgesteuerte Wartevorgänge erforderlich sind, können Sie eine [CMutex](../../mfc/reference/cmutex-class.md) -Objekt anstelle einer `CCriticalSection` Objekt.  
  
 Wenn `Lock` nicht belegen kann die erforderlichen Systemspeicher, eine Speicherausnahme (vom Typ [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) wird automatisch ausgelöst.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die geschachtelte kritischen Abschnitt Ansatz durch Steuern des Zugriffs auf eine freigegebene Ressource (der statischen `_strShared` Objekt) mithilfe einer freigegebenen `CCriticalSection` Objekt. Die `SomeMethod` Funktion zeigt eine freigegebene Ressource auf sichere Weise aktualisieren.  
  
 [!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="m_sect"></a>CCriticalSection::m_sect  
 Enthält einen kritischen Abschnitt-Objekt, das von allen verwendet wird `CCriticalSection` Methoden.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 Ruft eine **CRITICAL_SECTION** Objekt.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Zeiger auf das interne abzurufen **CRITICAL_SECTION** Objekt.  
  
##  <a name="unlock"></a>CCriticalSection::Unlock  
 Versionen der `CCriticalSection` Objekt von einem anderen Thread verwendet werden.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CCriticalSection` Objekt wurde dem Thread gehört, und die Version erfolgreich war, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CCriticalSection` eigenständigen verwendet wird `Unlock` muss aufgerufen werden, sofort nach Abschluss der Verwendung der Ressource durch den kritischen Abschnitt gesteuert. Wenn eine [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt verwendet wird, `CCriticalSection::Unlock` wird aufgerufen, durch des Sperrenobjekt `Unlock` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CCriticalSection::Lock](#lock).  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMutex-Klasse](../../mfc/reference/cmutex-class.md)
