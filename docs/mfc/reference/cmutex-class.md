---
title: CMutex Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3bde85e64fe8593ec2637e767e8c3c70d3b8200
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038076"
---
# <a name="cmutex-class"></a>CMutex-Klasse
Stellt einen "Mutex" dar – ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|Erstellt ein `CMutex`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Mutexe sind nützlich, wenn nur ein Thread zu einem Zeitpunkt erfolgen kann, um Daten oder eine andere gesteuerte Ressource zu ändern. Hinzufügen von Knoten auf eine verknüpfte Liste wird z. B. ein Prozess, der nur von einem Thread zu einem Zeitpunkt zugelassen werden soll. Mithilfe einer `CMutex` Objekt, das die verknüpfte Liste, zu steuern, nur einen Thread zu einem Zeitpunkt zur Liste zugreifen kann.  
  
 Verwenden einer `CMutex` Objekt, das Erstellen der `CMutex` Objekt, wenn es benötigt wird. Geben Sie den Namen des Mutex auf das gewartet werden soll, und Ihre Anwendung sollte anfänglich besitzen. Anschließend können Sie Mutex zugreifen, wenn Sie den Konstruktor zurück. Rufen Sie [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) nach abgeschlossener gesteuerte Ressource zugreifen.  
  
 Eine alternative Methode für die Verwendung von `CMutex` Objekte ist die Verwendung eine Variablen des Typs hinzufügen `CMutex` als Datenmember der Klasse, die Sie steuern möchten. Während der Erstellung des Objekts kontrollierten, rufen Sie den Konstruktor von den `CMutex` Datenmember, die angibt, ob das Mutex anfänglich gehört, den Namen des Mutex (sofern er über Prozessgrenzen hinweg verwendet wird) und des gewünschten Sicherheitsattribute.  
  
 Den Zugriff auf Ressourcen gesteuert durch `CMutex` Objekte auf diese Weise zuerst erstellen Sie eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) oder Typ [CMultiLock](../../mfc/reference/cmultilock-class.md) in Ihrer Ressource zugreifen-Memberfunktion. Rufen Sie anschließend des Sperrenobjekt `Lock` Member-Funktion (z. B. [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). An diesem Punkt wird des Threads entweder auf die Ressource zugreifen, warten Sie, bis die Ressource freigegeben werden, und erhalten Zugriff oder warten Sie auf die Ressource freigegeben wird und das Timeout wegen eines Fehlers beim Zugriff auf die Ressource haben. In jedem Fall wurde die Ressource auf threadsichere Weise zugegriffen wurde. Um die Ressource freizugeben, verwenden Sie des Sperrenobjekt `Unlock` Member-Funktion (z. B. [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.  
  
 Weitere Informationen zur Verwendung von `CMutex` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmt.h  
  
##  <a name="cmutex"></a>  CMutex::CMutex  
 Erstellt einen benannten oder unbenannten `CMutex` Objekt.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *bInitiallyOwn*  
 Gibt an, ob der Thread erstellen die `CMutex` Objekt ursprünglich hat Zugriff auf die Ressource, die vom Mutex gesteuert.  
  
 *Wert*  
 Name des `CMutex`-Objekts. Wenn eine andere Mutex mit dem gleichen Namen vorhanden ist, *Wert* muss angegeben werden, wenn das Objekt über Prozessgrenzen hinweg verwendet werden soll. Wenn **NULL**, wird der Mutex unbenannte sein. Der Name ein vorhandenes Mutex übereinstimmt, der Konstruktor erstellt ein neues `CMutex` Objekt das Mutex mit diesem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf ein Mutex ist übereinstimmt, schlägt die Erstellung fehl.  
  
 *lpsaAttribute*  
 Die Sicherheitsattribute für den Mutex-Objekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Zugreifen oder aufgehoben eine `CMutex` Objekt, das Erstellen einer [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Member-Funktionen. Wenn die `CMutex` Objekt eigenständigen verwendet wird, rufen Sie die `Unlock` Memberfunktion, diese freizugeben.  
  
> [!IMPORTANT]
>  Nach dem Erstellen der `CMutex` -Objekts [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex nicht bereits vorhanden war. Wenn das Mutex unerwartet vorhanden war, kann dies bedeuten, ein Rogue-Prozess ist squatting und möglicherweise beabsichtigten Mutex in böswilliger Absicht verwendet werden. In diesem Fall ist die empfohlene Vorgehensweise für die-Lösung auf das Handle geschlossen und fortgesetzt, als wäre es ein Fehler wurde beim Erstellen des Objekts.  
  
## <a name="see-also"></a>Siehe auch  
 [CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



