---
title: CMutex-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: a0d3be9a77435d8c607bacbc82b58cc95d04a805
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420647"
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

Mutexe sind hilfreich, wenn nur ein Thread zu einem Zeitpunkt erfolgen kann, um Daten oder eine andere gesteuerte Ressource zu ändern. Beispielsweise ist das Hinzufügen von Knoten zu einer verknüpften Liste ein Prozess, der nur von einem Thread gleichzeitig zugelassen werden soll. Mithilfe einer `CMutex` Objekt, das nur einen Thread zu einem Zeitpunkt Zugriff auf die Liste erhalten die verknüpfte Liste zu steuern.

Verwenden einer `CMutex` Objekt, das Erstellen der `CMutex` Objekt, wenn er benötigt wird. Geben Sie den Namen des Mutex gewartet werden soll, und, die Ihre Anwendung sollte zunächst besitzen. Anschließend können Sie den Mutex zugreifen, wenn den Konstruktor zurück. Rufen Sie [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) Sie abschließend den Zugriff auf gesteuerte Ressource.

Eine alternative Methode für die Verwendung von `CMutex` Objekten ist eine Variable des Typs hinzufügen `CMutex` als Datenmember der Klasse, die Sie steuern möchten. Rufen Sie während der Erstellung des kontrollierten-Objekts, den Konstruktor von den `CMutex` Datenmember, der angibt, ob das Mutex anfänglich gehört, den Namen des Mutex (falls sie über Prozessgrenzen hinweg verwendet wird), und des gewünschten Sicherheitsattribute.

Zum Zugriff auf Ressourcen durch gesteuert `CMutex` Objekte auf diese Weise erstellen Sie eine Variable vom Typ zuerst [CSingleLock](../../mfc/reference/csinglelock-class.md) oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in Access-Memberfunktion der Ressource. Rufen Sie dann des Sperrobjekt `Lock` Member-Funktion (z. B. [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). Der Thread wird an diesem Punkt wird entweder ein erhalten Sie Zugriff auf die Ressource abgerufen, warten, bis die Ressource freigegeben werden und erhalten Zugriff, oder warten, bis die Ressource freigegeben werden und das Timeout für den Zugriff auf die Ressource ein. In jedem Fall hat die Ressource auf threadsichere Weise erfolgt. Um die Ressource freizugeben, verwenden Sie des Sperrobjekt `Unlock` Member-Funktion (z. B. [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie das Sperrobjekt, das außerhalb des gültigen Bereichs liegen.

Weitere Informationen zur Verwendung von `CMutex` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

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

*bInitiallyOwn*<br/>
Gibt an, ob das Erstellen von Threads die `CMutex` Objekt ursprünglich hat Zugriff auf die Ressource, die vom Mutex gesteuert.

*Wert*<br/>
Name des `CMutex`-Objekts. Wenn eine andere Mutex mit dem gleichen Namen vorhanden ist, *Wert* müssen angegeben werden, wenn das Objekt über Prozessgrenzen hinweg verwendet werden soll. Wenn **NULL**, wird der Mutex unbenannt sein. Der Name einen vorhandenen Mutex übereinstimmt, der Konstruktor erstellt ein neues `CMutex` Objekt, das den Mutex mit diesem Namen verweist. Wenn der Name einer vorhandenen Synchronisierungsobjekt, die nicht auf ein Mutex ist übereinstimmt, schlägt die Erstellung fehl.

*lpsaAttribute*<br/>
Von Sicherheitsattributen für das Mutex-Objekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) im Windows SDK.

### <a name="remarks"></a>Hinweise

Zum Zugreifen auf oder release eine `CMutex` Objekt, das Erstellen einer [CMultiLock](../../mfc/reference/cmultilock-class.md) oder [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Member-Funktionen. Wenn die `CMutex` Objekt eigenständigen verwendet wird, rufen Sie die `Unlock` Member-Funktion, um es zu lösen.

> [!IMPORTANT]
>  Nach dem Erstellen der `CMutex` -Objekts [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) um sicherzustellen, dass das Mutex nicht bereits vorhanden ist. Wenn der Mutex unerwartet vorhanden war, kann dies bedeuten, ein nicht autorisierten Prozess ist squatting und möglicherweise beabsichtigt Mutex in böswilliger Absicht verwendet werden. Die empfohlene Vorgehensweise für sicherheitsorientierten werden in diesem Fall das Handle geschlossen und fortgesetzt, als wäre der Fehler beim Erstellen des Objekts.

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)



