---
title: CCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e5147faaf0170a10295006f12d7e95f5dfd3e8d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380697"
---
# <a name="ccriticalsection-class"></a>CCriticalSection-Klasse

Stellt einen "kritischen Abschnitt" – ein Synchronisierungsobjekt, das jeweils einem Thread gleichzeitig Zugriff auf eine Ressource oder einen Codeabschnitt ermöglicht.

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
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Ruft einen Zeiger auf das interne CRITICAL_SECTION-Objekt ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CCriticalSection::m_sect](#m_sect)|Ein Objekt CRITICAL_SECTION.|

## <a name="remarks"></a>Hinweise

Kritische Abschnitte sind nützlich, wenn nur ein Thread zu einem Zeitpunkt erfolgen kann, um Daten oder eine andere gesteuerte Ressource zu ändern. Beispielsweise ist das Hinzufügen von Knoten zu einer verknüpften Liste ein Prozess, der nur von einem Thread gleichzeitig zugelassen werden soll. Mithilfe einer `CCriticalSection` Objekt, das nur einen Thread zu einem Zeitpunkt Zugriff auf die Liste erhalten die verknüpfte Liste zu steuern.

> [!NOTE]
>  Die Funktionalität der `CCriticalSection` Klasse wird durch ein tatsächliches CRITICAL_SECTION-Win32-Objekt bereitgestellt.

Kritische Abschnitte werden verwendet, anstatt Mutexe (finden Sie unter [CMutex](../../mfc/reference/cmutex-class.md)) Wenn hohe Rendergeschwindigkeit wichtig ist und die Ressource wird nicht über Prozessgrenzen hinweg verwendet werden.

Es gibt zwei Methoden für die Verwendung einer `CCriticalSection` Objekt: eigenständige und in einer Klasse eingebettet.

- Eigenständige Methode für eine eigenständige `CCriticalSection` Objekt, das Erstellen der `CCriticalSection` Objekt, wenn er benötigt wird. Nach einer erfolgreichen Rückgabe aus dem Konstruktor, Sperren Sie explizit das Objekt mit einem Aufruf von [Sperre](#lock). Rufen Sie [Unlock](#unlock) Sie abschließend den Zugriff auf den kritischen Abschnitt. Diese Methode, bei der deutlicher an eine Person beim Lesen von Quellcodes, ist anfälliger für Fehler, wie Sie merken müssen, Sperren und entsperren den kritischen Abschnitt vor und nach dem Zugriff.

     Eine weitere bevorzugte Methode ist die Verwendung der [CSingleLock](../../mfc/reference/csinglelock-class.md) Klasse. Es verfügt auch über eine `Lock` und `Unlock` -Methode, aber Sie müssen keine Gedanken um die Ressource entsperren, wenn eine Ausnahme auftritt.

- Embedded-Methode, Sie können auch eine Klasse mit mehreren Threads freigeben, durch das Hinzufügen einer `CCriticalSection`-Typ-Datenmember auf die Klasse und den Datenmember, die bei Bedarf zu sperren.

Weitere Informationen zur Verwendung von `CCriticalSection` Objekte finden Sie im Artikel [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Anforderungen

**Header:** afxmt.h

##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection

Erstellt ein `CCriticalSection`-Objekt.

```
CCriticalSection();
```

### <a name="remarks"></a>Hinweise

Zum Zugreifen auf oder release eine `CCriticalSection` Objekt, das Erstellen einer [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt, und rufen die [Sperre](../../mfc/reference/csinglelock-class.md#lock) und [Unlock](../../mfc/reference/csinglelock-class.md#unlock) Memberfunktionen. Wenn die `CCriticalSection` Objekt eigenständigen verwendet wird, rufen Sie die [Unlock](#unlock) Member-Funktion, um es zu lösen.

Wenn der Konstruktor ein Fehler auftritt, den erforderlichen Speicher eine Memory-Ausnahme zuzuordnen (des Typs [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) wird automatisch ausgelöst.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CCriticalSection::Lock](#lock).

##  <a name="lock"></a>  CCriticalSection::Lock

Rufen Sie diese Memberfunktion zum Zugriff auf das Objekt des kritischen Abschnitts.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Parameter

*dwTimeout*<br/>
`Lock` Wert dieses Parameters wird ignoriert.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

`Lock` ist ein blockierender Aufruf, der erst Objekt des kritischen Abschnitts signalisiert wird, beendet wird (verfügbar).

Wenn zeitgesteuerte Wartevorgänge erforderlich sind, können Sie eine [CMutex](../../mfc/reference/cmutex-class.md) Objekt, sondern mit einem `CCriticalSection` Objekt.

Wenn `Lock` nicht benötigten Speicher eine Memory-Ausnahme kann (des Typs [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) wird automatisch ausgelöst.

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt den geschachtelten kritischen Abschnitt Ansatz durch Steuern des Zugriffs auf eine freigegebene Ressource (die statische `_strShared` Objekt) Verwendung einer freigegebenen `CCriticalSection` Objekt. Die `SomeMethod` Funktion demonstriert das Aktualisieren einer freigegebenen Ressource auf sichere Weise.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

##  <a name="m_sect"></a>  CCriticalSection::m_sect

Enthält einen kritischen Abschnitt-Objekt, das von allen verwendet wird `CCriticalSection` Methoden.

```
CRITICAL_SECTION m_sect;
```

##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *

Ruft ein Objekt CRITICAL_SECTION ab.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um einen Zeiger auf das interne CRITICAL_SECTION-Objekt abzurufen.

##  <a name="unlock"></a>  CCriticalSection::Unlock

Versionen der `CCriticalSection` Objekt für die Verwendung von einem anderen Thread.

```
BOOL Unlock();
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CCriticalSection` Objekt wurde dem Thread gehört, und die Veröffentlichung war erfolgreich, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn die `CCriticalSection` verwendeten eigenständigen `Unlock` muss aufgerufen werden, sofort nach Abschluss der Verwendung der Ressource durch den kritischen Abschnitt gesteuert. Wenn eine [CSingleLock](../../mfc/reference/csinglelock-class.md) Objekt verwendet wird, `CCriticalSection::Unlock` wird durch des Sperrobjekt aufgerufen `Unlock` Member-Funktion.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CCriticalSection::Lock](#lock).

## <a name="see-also"></a>Siehe auch

[CSyncObject-Klasse](../../mfc/reference/csyncobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMutex-Klasse](../../mfc/reference/cmutex-class.md)
