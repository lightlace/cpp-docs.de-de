---
title: CMutex Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex class
- synchronization classes, CMutex class
- synchronization objects, mutex
- mutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
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
ms.openlocfilehash: 159f2e02dfe44d74ebcaad687a23cef734b61fc9
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmutex-class"></a>CMutex-Klasse
Stellt einen "Mutex" dar – ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|Erstellt ein `CMutex`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Mutexe sind hilfreich, wenn jeweils nur ein Thread erfolgen kann, um Daten oder eine andere gesteuerte Ressource zu ändern. Hinzufügen von Knoten zu einer verknüpften Liste ist beispielsweise ein Prozess, der nur von einem Thread zu einem Zeitpunkt werden darf. Mit einem `CMutex` -Objekt, das die verknüpfte Liste steuern nur jeweils ein Thread auf die Liste zugreifen kann.  
  
 Verwenden einer `CMutex` Objekt, das Erstellen der `CMutex` Objekt, wenn es benötigt wird. Geben Sie den Namen des Mutex gewartet werden soll, und Ihre Anwendung sollte anfänglich besitzen. Anschließend können Sie Mutex zugreifen, wenn der Konstruktor zurückgegeben. Rufen Sie [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) Sie zum Abschluss auf gesteuerte Ressource zugreifen.  
  
 Eine alternative Methode für die Verwendung von `CMutex` Objekte ist die Verwendung eine Variablen des Typs hinzufügen `CMutex` als Datenmember der Klasse, die Sie steuern möchten. Während der Erstellung des gesteuerten Objekts rufen Sie den Konstruktor von den `CMutex` -Datenmember, die angibt, ob das Mutex anfänglich gehört, den Namen des Mutex (falls sie über Prozessgrenzen hinweg verwendet wird) und des gewünschten Sicherheitsattribute.  
  
 Zum Zugriff auf Ressourcen gesteuert durch `CMutex` Objekte auf diese Weise zuerst erstellen Sie eine Variable des Typs [CSingleLock](../../mfc/reference/csinglelock-class.md) oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in Ihrer Ressource zugreifen-Memberfunktion. Rufen Sie dann des Sperrobjekt `Lock` Member-Funktion (z. B. [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). An diesem Punkt wird des Threads entweder Zugriff auf die Ressource warten, bis die Ressource freigegeben werden und Zugriff oder warten, für die Ressource freigegeben werden und das Timeout für den Zugriff auf die Ressource fehlschlägt. In jedem Fall ist die Ressource auf eine threadsichere Weise zugegriffen wurde. Um die Ressourcen freizugeben, verwenden Sie des Sperrobjekt `Unlock` Member-Funktion (z. B. [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.  
  
 Weitere Informationen zur Verwendung von `CMutex` Objekte finden Sie im Artikel [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="cmutex"></a>CMutex::CMutex  
 Erstellt einen benannten oder unbenannten `CMutex` Objekt.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bInitiallyOwn`  
 Gibt an, ob das Erstellen von Threads die `CMutex` Objekt Anfangs hat Zugriff auf die Ressource, die vom Mutex gesteuert.  
  
 `lpszName`  
 Name des `CMutex`-Objekts. Wenn eine andere Mutex mit dem gleichen Namen vorhanden ist, `lpszName` muss angegeben werden, wenn das Objekt über Prozessgrenzen hinweg verwendet werden soll. Wenn **NULL**, wird der Mutex unbenannt sein. Wenn der Name ein vorhandenen Mutex übereinstimmt, erstellt der Konstruktor ein neues `CMutex` Objekt, das den Mutex mit dem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf ein Mutex ist übereinstimmt, schlägt die Erstellung fehl.  
  
 `lpsaAttribute`  
 Die Sicherheitsattribute für das Mutexobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder freigegeben ein `CMutex` Objekt, einen [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperren](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Memberfunktionen. Wenn die `CMutex` Objekt eigenständigen verwendet wird, rufen Sie seine `Unlock` Member-Funktion, um es zu lösen.  
  
> [!IMPORTANT]
>  Nach dem Erstellen der `CMutex` -Objekts [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex noch nicht vorhanden war. Wenn der Mutex unerwartet vorhanden war, kann dies bedeuten, ein nicht autorisierten Prozess squatting ist und möglicherweise die Absicht, die den Mutex in böswilliger Absicht zu verwenden. In diesem Fall ist die empfohlene Vorgehensweise für die sicherheitsbewusste das Handle geschlossen und fortgesetzt, als wäre das Erstellen des Objekts ein Fehler aufgetreten.  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




