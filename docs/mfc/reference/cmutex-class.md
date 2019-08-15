---
title: CMutex-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 65f7f4db9489de1c9a380d760ed5cab41bfdc2ec
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504519"
---
# <a name="cmutex-class"></a>CMutex-Klasse

Stellt einen "Mutex" dar – ein Synchronisierungs Objekt, das einem Thread den gegenseitigen Zugriff auf eine Ressource ermöglicht.

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

Mutexes sind hilfreich, wenn nur ein Thread gleichzeitig Daten oder eine andere kontrollierte Ressource ändern darf. Das Hinzufügen von Knoten zu einer verknüpften Liste ist beispielsweise ein Prozess, der nur jeweils von einem Thread zugelassen werden sollte. Wenn Sie ein `CMutex` -Objekt verwenden, um die verknüpfte Liste zu steuern, kann jeweils nur ein Thread Zugriff auf die Liste erhalten.

Um ein `CMutex` -Objekt zu verwenden, `CMutex` erstellen Sie das-Objekt, wenn es benötigt wird. Geben Sie den Namen des Mutex an, auf den gewartet werden soll, und der die Anwendung zunächst besitzen soll. Sie können dann auf den Mutex zugreifen, wenn der Konstruktor zurückgibt. Aufrufen von [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) , wenn Sie mit dem Zugriff auf die kontrollierte Ressource abgeschlossen sind.

Eine alternative Methode zum verwenden `CMutex` von-Objekten besteht darin, der Klasse `CMutex` , die Sie steuern möchten, eine Variable vom Typ als Datenmember hinzuzufügen. Beim Erstellen des kontrollierten Objekts wird der Konstruktor des `CMutex` Datenmembers aufgerufen, der angibt, ob der Mutex anfänglich gehört, der Name des Mutex (wenn er über Prozess Grenzen hinweg verwendet wird) und die gewünschten Sicherheits Attribute.

Um auf diese Weise auf `CMutex` Ressourcen zuzugreifen, die von-Objekten gesteuert werden, erstellen Sie zunächst eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) , oder geben Sie [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Access-Member-Funktion Ihrer Ressource ein. Anschließend wird die Member- `Lock` Funktion des Lock-Objekts aufgerufen (z. b. [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). An diesem Punkt erhält der Thread entweder Zugriff auf die Ressource, wartet, bis die Ressource freigegeben wird, und erhält Zugriff, oder es wird gewartet, bis die Ressource freigegeben und ein Timeout auftritt, und es wird nicht auf die Ressource zugegriffen. In jedem Fall wurde auf Ihre Ressource Thread sicher zugegriffen. Um die Ressource freizugeben, verwenden Sie die Member `Unlock` -Funktion des Lock-Objekts (z. b. [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie zu, dass das Sperr Objekt den Gültigkeitsbereich verlässt.

Weitere Informationen zur Verwendung von `CMutex` Objekten finden Sie im Artikel [Multithreading: Verwenden der Synchronisierungs Klassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="cmutex"></a>CMutex:: CMutex

Erstellt ein benanntes `CMutex` oder Unbenanntes Objekt.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parameter

*bInitiallyOwn*<br/>
Gibt an, ob der Thread `CMutex` , der das Objekt erstellt, anfänglich auf die vom Mutex gesteuerte Ressource zugreifen muss.

*Wert*<br/>
Name des `CMutex`-Objekts. Wenn ein anderer Mutex mit dem gleichen Namen vorhanden ist, muss *lpszname* angegeben werden, wenn das Objekt über Prozess Grenzen hinweg verwendet wird. Wenn der Wert **null**ist, wird der Mutex unbenannt. Wenn der Name mit einem vorhandenen Mutex übereinstimmt, erstellt der Konstruktor `CMutex` ein neues-Objekt, das auf den Mutex dieses Namens verweist. Wenn der Name mit einem vorhandenen Synchronisierungs Objekt übereinstimmt, bei dem es sich nicht um einen Mutex handelt, tritt ein Fehler auf.

*lpsaAttribute*<br/>
Sicherheits Attribute für das Mutex-Objekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) im Windows SDK.

### <a name="remarks"></a>Hinweise

`CMutex` Erstellen Sie ein [CMultiLock](../../mfc/reference/cmultilock-class.md) -oder [CSingleLock](../../mfc/reference/csinglelock-class.md) -Objekt, und rufen Sie seine [Lock](../../mfc/reference/csinglelock-class.md#lock) -und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) -Member-Funktionen auf, um auf ein-Objekt zuzugreifen Wenn das `CMutex` Objekt eigenständig verwendet wird, müssen Sie seine `Unlock` Member-Funktion aufzurufen, um es freizugeben.

> [!IMPORTANT]
>  Nachdem Sie das `CMutex` Objekt erstellt haben, verwenden Sie [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , um sicherzustellen, dass der Mutex nicht bereits vorhanden ist. Wenn der Mutex unerwartet vorhanden war, deutet dies möglicherweise darauf hin, dass ein nicht autorisierter Prozess besetzt wird und die Mutex böswillig verwenden könnte. In diesem Fall besteht das empfohlene sicherheitsbewusste Verfahren darin, das Handle zu schließen und den Vorgang fortzusetzen, als ob bei der Erstellung des Objekts ein Fehler aufgetreten ist.

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
