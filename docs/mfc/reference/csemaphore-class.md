---
title: CSemaphore-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8794c2625e3ecda442cc0e7a1079ede148ed8e9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074812"
---
# <a name="csemaphore-class"></a>CSemaphore-Klasse

Ein Objekt der Klasse `CSemaphore` stellt ein "Semaphor" – ein Synchronisierungsobjekt, das einer begrenzten Anzahl von Threads in einem oder mehreren Prozessen eine verwaltet den Zugriff auf die Anzahl der Threads, die derzeit auf eine angegebene Ressource ermöglicht.

## <a name="syntax"></a>Syntax

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|Erstellt ein `CSemaphore`-Objekt.|

## <a name="remarks"></a>Hinweise

Semaphoren sind hilfreich bei der Steuerung des Zugriffs auf eine freigegebene Ressource, die nur eine begrenzte Anzahl von Benutzern unterstützen kann. Die aktuelle Anzahl von der `CSemaphore` Objekt ist die Anzahl der zusätzlichen Benutzer zulässig. Wenn die Anzahl auf 0 (null) erreicht, alle Versuche, die die Ressource, gesteuert durch Verwenden der `CSemaphore` Objekt in einer Systemwarteschlange eingefügt werden, und warten Sie, bis sie entweder einen Timeout beendet oder übersteigt die Anzahl 0. Die maximale Anzahl von Benutzern, die gleichzeitig eine gesteuerte Ressource zugreifen kann während der Erstellung der angegeben wird die `CSemaphore` Objekt.

Verwenden einer `CSemaphore` Objekt, das Erstellen der `CSemaphore` Objekt, wenn er benötigt wird. Geben Sie den Namen der Semaphore, die auf die gewartet werden soll, und, die Ihre Anwendung sollte zunächst besitzen. Anschließend können Sie das Semaphor zugreifen, wenn Sie den Konstruktor zurück. Rufen Sie [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) Sie abschließend den Zugriff auf gesteuerte Ressource.

Eine alternative Methode für die Verwendung von `CSemaphore` Objekten ist eine Variable des Typs hinzufügen `CSemaphore` als Datenmember der Klasse, die Sie steuern möchten. Rufen Sie den Konstruktor der während der Erstellung des kontrollierten-Objekts, das `CSemaphore` Datenmember angeben der anfänglichen Zugriff auf die Anzahl, maximale Zugriffsversuche, Name, der das Semaphor (sofern er über Prozessgrenzen hinweg verwendet wird), und der gewünschten Sicherheitsattribute.

Zum Zugriff auf Ressourcen durch gesteuert `CSemaphore` Objekte auf diese Weise erstellen Sie eine Variable vom Typ zuerst [CSingleLock](../../mfc/reference/csinglelock-class.md) oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in Access-Memberfunktion der Ressource. Rufen Sie dann des Sperrobjekt `Lock` Member-Funktion (z. B. [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). Der Thread wird an diesem Punkt wird entweder ein erhalten Sie Zugriff auf die Ressource abgerufen, warten, bis die Ressource freigegeben werden und erhalten Zugriff, oder warten, bis die Ressource freigegeben werden und das Timeout für den Zugriff auf die Ressource ein. In jedem Fall hat die Ressource auf threadsichere Weise erfolgt. Um die Ressource freizugeben, verwenden Sie des Sperrobjekt `Unlock` Member-Funktion (z. B. [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.

Alternativ können Sie erstellen eine `CSemaphore` Objekt eigenständige, und es explizit zugreifen, bevor Sie versuchen, auf die gesteuerte Ressource zugreifen. Diese Methode, bei der deutlicher an eine Person beim Lesen von Quellcodes, ist anfälliger für Fehler.

Weitere Informationen zur Verwendung von `CSemaphore` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="csemaphore"></a>  CSemaphore::CSemaphore

Erstellt einen benannten oder unbenannten `CSemaphore` Objekt.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parameter

*lInitialCount-Parameter*<br/>
Die Verwendungsanzahl der ersten für das Semaphor. Muss größer als oder gleich 0 und kleiner als oder gleich *lMaxCount*.

*lMaxCount*<br/>
Die maximale Auslastung-Anzahl für das Semaphor. Muss größer als 0 sein.

*pstrName*<br/>
Der Name des das Semaphor. Muss angegeben werden, wenn das Semaphor über Prozessgrenzen hinweg zugegriffen wird. Wenn `NULL`, wird das Objekt unbenannt sein. Der Name ein vorhandenes Semaphor übereinstimmt, der Konstruktor erstellt ein neues `CSemaphore` Objekt, das das Semaphor mit diesem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf eine Semaphore ist übereinstimmt, schlägt die Erstellung fehl.

*lpsaAttributes*<br/>
Von Sicherheitsattributen für das Semaphorobjekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) im Windows SDK.

### <a name="remarks"></a>Hinweise

Zum Zugreifen auf oder release eine `CSemaphore` Objekt, das Erstellen einer [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Member-Funktionen.

> [!IMPORTANT]
>  Nach dem Erstellen der `CSemaphore` -Objekts [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex nicht bereits vorhanden ist. Wenn der Mutex unerwartet vorhanden war, kann dies bedeuten, ein nicht autorisierten Prozess ist squatting und möglicherweise beabsichtigt Mutex in böswilliger Absicht verwendet werden. Die empfohlene Vorgehensweise für sicherheitsorientierten werden in diesem Fall das Handle geschlossen und fortgesetzt, als wäre der Fehler beim Erstellen des Objekts.

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

