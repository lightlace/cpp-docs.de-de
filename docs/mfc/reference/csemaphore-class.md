---
title: CSemaphore-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: d5a0e4187107aaab7cedf4e7a0e2fc47b9f9f305
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502585"
---
# <a name="csemaphore-class"></a>CSemaphore-Klasse

Ein Objekt der Klasse `CSemaphore` stellt ein "Semaphor" dar – ein Synchronisierungs Objekt, das einer begrenzten Anzahl von Threads in einem oder mehreren Prozessen den Zugriff auf eine ermöglicht, zählt die Anzahl der Threads, die derzeit auf eine angegebene Ressource zugreifen.

## <a name="syntax"></a>Syntax

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSemaphore:: CSemaphore](#csemaphore)|Erstellt ein `CSemaphore`-Objekt.|

## <a name="remarks"></a>Hinweise

Semaphoren sind nützlich, um den Zugriff auf eine freigegebene Ressource zu steuern, die nur eine begrenzte Anzahl von Benutzern unterstützen kann. Die aktuelle Anzahl des `CSemaphore` -Objekts ist die Anzahl der zulässigen zusätzlichen Benutzer. Wenn die Anzahl 0 (null) erreicht, werden alle Versuche, die vom `CSemaphore` -Objekt gesteuerte Ressource zu verwenden, in eine System Warteschlange eingefügt, und es wird gewartet, bis Sie entweder ein Timeout oder eine Anzahl über 0 erreicht. Die maximale Anzahl von Benutzern, die gleichzeitig auf die kontrollierte Ressource zugreifen können, wird während der Erstellung `CSemaphore` des Objekts angegeben.

Um ein `CSemaphore` -Objekt zu verwenden, `CSemaphore` erstellen Sie das-Objekt, wenn es benötigt wird. Geben Sie den Namen des Semaphors an, auf das gewartet werden soll. Sie können dann auf das Semaphor zugreifen, wenn der Konstruktor zurückgibt. Aufrufen von [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) , wenn Sie mit dem Zugriff auf die kontrollierte Ressource abgeschlossen sind.

Eine alternative Methode zum verwenden `CSemaphore` von-Objekten besteht darin, der Klasse `CSemaphore` , die Sie steuern möchten, eine Variable vom Typ als Datenmember hinzuzufügen. Bei der Erstellung des kontrollierten Objekts wird der Konstruktor des `CSemaphore` Datenmembers aufgerufen, der die anfängliche Zugriffs Anzahl, die maximale Zugriffs Anzahl, den Namen des Semaphors (wenn er über Prozess Grenzen hinweg verwendet wird) und gewünschte Sicherheits Attribute angibt.

Um auf diese Weise auf `CSemaphore` Ressourcen zuzugreifen, die von-Objekten gesteuert werden, erstellen Sie zunächst eine Variable vom Typ [CSingleLock](../../mfc/reference/csinglelock-class.md) , oder geben Sie [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Access-Member-Funktion Ihrer Ressource ein. Anschließend wird die Member- `Lock` Funktion des Lock-Objekts aufgerufen (z. b. [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). An diesem Punkt erhält der Thread entweder Zugriff auf die Ressource, wartet, bis die Ressource freigegeben wird, und erhält Zugriff, oder es wird gewartet, bis die Ressource freigegeben und ein Timeout auftritt, und es wird nicht auf die Ressource zugegriffen. In jedem Fall wurde auf Ihre Ressource Thread sicher zugegriffen. Um die Ressource freizugeben, verwenden Sie die Member `Unlock` -Funktion des Lock-Objekts (z. b. [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)), oder lassen Sie zu, dass das Sperr Objekt den Gültigkeitsbereich verlässt.

Alternativ können Sie ein `CSemaphore` -Objekt eigenständig erstellen und darauf explizit zugreifen, bevor Sie versuchen, auf die kontrollierte Ressource zuzugreifen. Diese Methode ist für Personen, die den Quellcode lesen, übersichtlicher und fehleranfälliger.

Weitere Informationen zur Verwendung `CSemaphore` von Objekten finden Sie im Artikel [Multithreading: Verwenden der Synchronisierungs Klassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="csemaphore"></a>CSemaphore:: CSemaphore

Erstellt ein benanntes `CSemaphore` oder Unbenanntes Objekt.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parameter

*lInitialCount*<br/>
Die anfängliche Verwendungs Anzahl für das Semaphor. Muss größer als oder gleich 0 (null) und kleiner oder gleich *lmaxcount*sein.

*lMaxCount*<br/>
Die maximale Verwendungs Anzahl für das Semaphor. Muss größer als 0 sein.

*pstrName*<br/>
Der Name des Semaphors. Muss angegeben werden, wenn der Zugriff auf das Semaphor über Prozess Grenzen hinweg erfolgt. Gibt `NULL`an, dass das Objekt unbenannt wird. Wenn der Name mit einem vorhandenen Semaphor übereinstimmt, erstellt der Konstruktor `CSemaphore` ein neues-Objekt, das auf das Semaphor dieses Namens verweist. Wenn der Name mit einem vorhandenen Synchronisierungs Objekt übereinstimmt, bei dem es sich nicht um ein Semaphor handelt, tritt ein Fehler auf.

*lpsaattribute*<br/>
Sicherheits Attribute für das Semaphor-Objekt. Eine vollständige Beschreibung dieser Struktur finden Sie unter [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) im Windows SDK.

### <a name="remarks"></a>Hinweise

`CSemaphore` Erstellen Sie ein [CMultiLock](../../mfc/reference/cmultilock-class.md) -oder [CSingleLock](../../mfc/reference/csinglelock-class.md) -Objekt, und rufen Sie seine [Lock](../../mfc/reference/csinglelock-class.md#lock) -und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) -Member-Funktionen auf, um auf ein-Objekt zuzugreifen

> [!IMPORTANT]
>  Nachdem Sie das `CSemaphore` Objekt erstellt haben, verwenden Sie [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , um sicherzustellen, dass der Mutex nicht bereits vorhanden ist. Wenn der Mutex unerwartet vorhanden war, deutet dies möglicherweise darauf hin, dass ein nicht autorisierter Prozess besetzt wird und die Mutex böswillig verwenden könnte. In diesem Fall besteht das empfohlene sicherheitsbewusste Verfahren darin, das Handle zu schließen und den Vorgang fortzusetzen, als ob bei der Erstellung des Objekts ein Fehler aufgetreten ist.

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
