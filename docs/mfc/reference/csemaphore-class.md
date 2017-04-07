---
title: CSemaphore-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, semaphores
- CSemaphore class
- semaphores
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
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
ms.openlocfilehash: 31de1e553ea2facea6b70c284aecdbf10e22c89f
ms.lasthandoff: 02/24/2017

---
# <a name="csemaphore-class"></a>CSemaphore-Klasse
Ein Objekt der Klasse `CSemaphore` stellt ein "Semaphor" dar – ein Synchronisierungsobjekt, das einer begrenzten Anzahl von Threads in einem oder mehreren Prozessen verwaltet den Zugriff auf die Anzahl der Threads, die gerade auf eine angegebene Ressource zugreifen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](#csemaphore)|Erstellt ein `CSemaphore`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Semaphoren sind hilfreich bei der Steuerung des Zugriffs auf eine freigegebene Ressource, die nur eine begrenzte Anzahl von Benutzern unterstützen kann. Die aktuelle Anzahl der `CSemaphore` -Objekt ist die Anzahl der zusätzlichen Benutzern zulässig. Wenn die Anzahl Null erreicht, alle Versuche, die Ressource gesteuert durch Verwenden der **CSemaphore** Objekt werden in einer Systemwarteschlange eingefügt und warten Sie, bis sie entweder zu einem Timeout oder die Anzahl übersteigt 0. Die maximale Anzahl von Benutzern, die gleichzeitig eine gesteuerte Ressource zugreifen kann während der Erstellung der angegeben ist die `CSemaphore` Objekt.  
  
 Verwenden einer **CSemaphore** Objekt, das Erstellen der `CSemaphore` Objekt, wenn es benötigt wird. Geben Sie den Namen der Semaphore zu warten und die Anwendung sollte anfänglich besitzen. Anschließend können Sie das Semaphor zugreifen, wenn der Konstruktor zurückgegeben. Rufen Sie [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) Sie zum Abschluss auf gesteuerte Ressource zugreifen.  
  
 Eine alternative Methode für die Verwendung von `CSemaphore` Objekte ist die Verwendung eine Variablen des Typs hinzufügen `CSemaphore` als Datenmember der Klasse, die Sie steuern möchten. Während der Erstellung des Objekts kontrollierten, rufen Sie den Konstruktor von den `CSemaphore` angeben der anfänglichen Datenmember zugreifen, Count, Access maximale Anzahl, Namen das Semaphor (Wenn sie über Prozessgrenzen hinweg verwendet wird), und des gewünschten Sicherheitsattribute.  
  
 Zum Zugriff auf Ressourcen gesteuert durch `CSemaphore` Objekte auf diese Weise zuerst erstellen Sie eine Variable des Typs [CSingleLock](../../mfc/reference/csinglelock-class.md) oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in Ihrer Ressource zugreifen-Memberfunktion. Rufen Sie dann des Sperrobjekt `Lock` Member-Funktion (z. B. [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). An diesem Punkt wird des Threads entweder Zugriff auf die Ressource warten, bis die Ressource freigegeben werden und Zugriff oder warten, für die Ressource freigegeben werden und das Timeout für den Zugriff auf die Ressource fehlschlägt. In jedem Fall ist die Ressource auf eine threadsichere Weise zugegriffen wurde. Um die Ressourcen freizugeben, verwenden Sie des Sperrobjekt `Unlock` Member-Funktion (z. B. [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.  
  
 Alternativ können Sie erstellen ein **CSemaphore** Objekt eigenständige, und es explizit beim Zugriff auf gesteuerte Ressource zugreifen. Diese Methode beim deutlicher an eine Person den Quellcode lesen wird anfälliger für Fehler.  
  
 Weitere Informationen zur Verwendung von **CSemaphore** Objekte finden Sie im Artikel [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="csemaphore"></a>CSemaphore::CSemaphore  
 Erstellt einen benannten oder unbenannten `CSemaphore` Objekt.  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lInitialCount-Parameter*  
 Die erste Verwendungsanzahl für das Semaphor. Muss größer als oder gleich 0 und kleiner als oder gleich `lMaxCount`.  
  
 `lMaxCount`  
 Die maximale Auslastung Anzahl für das Semaphor. Muss größer als 0 sein.  
  
 `pstrName`  
 Der Name des Semaphors. Muss angegeben werden, wenn das Semaphor über Prozessgrenzen hinweg erfolgen soll. Wenn `NULL,` wird das Objekt unbenannt sein. Wenn Sie ein vorhandenes Semaphor mit dem Namen übereinstimmt, erstellt der Konstruktor ein neues `CSemaphore` Objekt verweist auf die Semaphore mit diesem Namen. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf eine Semaphore ist übereinstimmt, schlägt die Erstellung fehl.  
  
 *lpsaAttributes*  
 Die Sicherheitsattribute für das Semaphorobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder freigegeben ein `CSemaphore` Objekt, einen [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperren](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Memberfunktionen.  
  
> [!IMPORTANT]
>  Nach dem Erstellen der `CSemaphore` -Objekts [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex noch nicht vorhanden war. Wenn der Mutex unerwartet vorhanden war, kann dies bedeuten, ein nicht autorisierten Prozess squatting ist und möglicherweise die Absicht, die den Mutex in böswilliger Absicht zu verwenden. In diesem Fall ist die empfohlene Vorgehensweise für die sicherheitsbewusste das Handle geschlossen und fortgesetzt, als wäre das Erstellen des Objekts ein Fehler aufgetreten.  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




