---
title: CSemaphore Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
dev_langs: C++
helpviewer_keywords: CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0184d013b0a36aeb77bebbba9f6e4ecef47b7f85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="csemaphore-class"></a>CSemaphore-Klasse
Ein Objekt der Klasse `CSemaphore` stellt ein "Semaphor" dar – ein Synchronisierungsobjekt, das einer begrenzten Anzahl von Threads in einem oder mehreren Prozessen ein verwaltet den Zugriff auf die Anzahl der Threads, die momentan auf eine angegebene Ressource ermöglicht.  
  
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
 Semaphoren eignen sich in Steuern des Zugriffs auf eine freigegebene Ressource, die nur eine begrenzte Anzahl von Benutzern unterstützen kann. Die aktuelle Anzahl der `CSemaphore` Objekt ist die Anzahl der zusätzlichen Benutzern zulässig. Wenn die Anzahl 0 (null) erreicht, alle Versuche, die vom gesteuerte Ressource verwenden die **CSemaphore** Objekt in einer Systemwarteschlange eingefügt werden, und warten Sie, bis sie entweder einen Timeout beendet oder die Anzahl übersteigt 0. Die maximale Anzahl von Benutzern an, die gleichzeitig eine gesteuerte Ressource zugreifen kann, wird während der Erstellung der angegeben die `CSemaphore` Objekt.  
  
 Verwenden einer **CSemaphore** Objekt, das Erstellen der `CSemaphore` Objekt, wenn es benötigt wird. Geben Sie den Namen der Semaphore warten soll und Ihrer Anwendung sollten anfangs besitzen. Anschließend können Sie das Semaphor zugreifen, wenn Sie den Konstruktor zurück. Rufen Sie [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) nach abgeschlossener gesteuerte Ressource zugreifen.  
  
 Eine alternative Methode für die Verwendung von `CSemaphore` Objekte ist die Verwendung eine Variablen des Typs hinzufügen `CSemaphore` als Datenmember der Klasse, die Sie steuern möchten. Während der Erstellung des Objekts kontrollierten, rufen Sie den Konstruktor von den `CSemaphore` Datenmember angeben der anfänglichen Zugriff auf Anzahl, maximale Zugriffsversuche, Name des das Semaphor (sofern er über Prozessgrenzen hinweg verwendet wird) und des gewünschten Sicherheitsattribute.  
  
 Den Zugriff auf Ressourcen gesteuert durch `CSemaphore` Objekte auf diese Weise zuerst erstellen Sie eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) oder Typ [CMultiLock](../../mfc/reference/cmultilock-class.md) in Ihrer Ressource zugreifen-Memberfunktion. Rufen Sie anschließend des Sperrenobjekt `Lock` Member-Funktion (z. B. [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). An diesem Punkt wird des Threads entweder auf die Ressource zugreifen, warten Sie, bis die Ressource freigegeben werden, und erhalten Zugriff oder warten Sie auf die Ressource freigegeben wird und das Timeout wegen eines Fehlers beim Zugriff auf die Ressource haben. In jedem Fall wurde die Ressource auf threadsichere Weise zugegriffen wurde. Um die Ressource freizugeben, verwenden Sie des Sperrenobjekt `Unlock` Member-Funktion (z. B. [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.  
  
 Alternativ können Sie erstellen eine **CSemaphore** Objekt eigenständigen, und es explizit vor dem Versuch, den Zugriff auf gesteuerte Ressource zugreifen. Diese Methode beim besseres an eine Person beim Lesen von Quellcodes, wird mehr fehleranfällig.  
  
 Weitere Informationen zur Verwendung von **CSemaphore** Objekte finden Sie im Artikel [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Die anfängliche Verwendungszähler für das Semaphor. Muss größer als oder gleich 0 und kleiner als oder gleich `lMaxCount`.  
  
 `lMaxCount`  
 Die maximale Auslastung Anzahl für das Semaphor. Muss größer als 0 sein.  
  
 `pstrName`  
 Der Name des das Semaphor. Muss angegeben werden, wenn das Semaphor über Prozessgrenzen hinweg zugegriffen wird. Wenn `NULL`, wird das Objekt unbenannte sein. Der Name einer vorhandenen Semaphore übereinstimmt, der Konstruktor erstellt ein neues `CSemaphore` Objekt, das auf das Semaphor mit diesem Namen. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf eine Semaphore ist übereinstimmt, schlägt die Erstellung fehl.  
  
 *lpsaAttributes*  
 Die Sicherheitsattribute für das Semaphorobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder aufgehoben eine `CSemaphore` Objekt, das Erstellen einer [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Member-Funktionen.  
  
> [!IMPORTANT]
>  Nach dem Erstellen der `CSemaphore` -Objekts [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex nicht bereits vorhanden war. Wenn das Mutex unerwartet vorhanden war, kann dies bedeuten, ein Rogue-Prozess ist squatting und möglicherweise beabsichtigten Mutex in böswilliger Absicht verwendet werden. In diesem Fall ist die empfohlene Vorgehensweise für die-Lösung auf das Handle geschlossen und fortgesetzt, als wäre es ein Fehler wurde beim Erstellen des Objekts.  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



