---
title: CHeapPtrBase-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: f183bb21d6a23b4e8ac4284894cfa2fcc7bb1dfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538153"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase-Klasse

Diese Klasse bildet die Grundlage für mehrere Klassen von smart-Heap-Zeiger.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Objekttyp, auf dem Heap gespeichert werden.

*Zuweisung*<br/>
Die Speicher-Allocation-Klasse verwenden. Standardmäßig werden die CRT-Routinen zum Zuordnen und Freigeben von Arbeitsspeicher verwendet.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Rufen Sie diese Methode, um Speicher zu belegen.|
|[CHeapPtrBase::Attach](#attach)|Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.|
|[CHeapPtrBase::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.|
|[CHeapPtrBase::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts verweist eine `CHeapPtrBase`.|
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtrBase::operator T *](#operator_t_star)|Der Cast-Operator.|
|[CHeapPtrBase::operator &](#operator_amp)|Die & Operator.|
|[CHeapPtrBase::operator ->](#operator_ptr)|Der Zeiger-auf-Member-Operator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|Die Zeiger-Membervariable.|

## <a name="remarks"></a>Hinweise

Diese Klasse bildet die Grundlage für mehrere Klassen von smart-Heap-Zeiger. Die abgeleiteten Klassen, z. B. [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), ihre eigenen Konstruktoren und Operatoren hinzufügen. Diese Klassen Beispiele für die Implementierung wird angezeigt.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes

Rufen Sie diese Methode, um Speicher zu belegen.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Speicher erfolgreich belegt, "false" andernfalls.

### <a name="remarks"></a>Hinweise

Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CHeapPtrBase::m_pData](#m_pdata) Membervariable zeigt derzeit zu einem vorhandenen Wert; das heißt, ist es nicht gleich NULL.

##  <a name="attach"></a>  CHeapPtrBase::Attach

Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.

```
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Parameter

*pData*<br/>
Die `CHeapPtrBase` Objekt übernimmt dann den Besitz des this-Zeigers.

### <a name="remarks"></a>Hinweise

Wenn eine `CHeapPtrBase` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt.

Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CHeapPtrBase::m_pData](#m_pdata) Membervariable zeigt derzeit zu einem vorhandenen Wert; das heißt, ist es nicht gleich NULL.

##  <a name="dtor"></a>  CHeapPtrBase:: ~ CHeapPtrBase

Der Destruktor.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="detach"></a>  CHeapPtrBase::Detach

Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.

```
T* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Kopie des Zeigers.

### <a name="remarks"></a>Hinweise

Gibt den Besitz eines Zeigers, legt die [CHeapPtrBase::m_pData](#m_pdata) Membervariable für NULL-Werte und gibt eine Kopie des Zeigers zurück.

##  <a name="free"></a>  CHeapPtrBase::Free

Rufen Sie diese Methode zum Löschen eines Objekts verweist eine `CHeapPtrBase`.

```
void Free() throw();
```

### <a name="remarks"></a>Hinweise

Das Objekt verweist die `CHeapPtrBase` wird freigegeben, und die [CHeapPtrBase::m_pData](#m_pdata) Member-Variable auf NULL festgelegt ist.

##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData

Die Zeiger-Membervariable.

```
T* m_pData;
```

### <a name="remarks"></a>Hinweise

Diese Membervariable enthält Zeigerinformationen.

##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;

Die & Operator.

```
T** operator&() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Adresse des Objekts verweist die `CHeapPtrBase` Objekt.

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator-&gt;

Der Zeiger-auf-Member-Operator.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des der [CHeapPtrBase::m_pData](#m_pdata) Membervariablen gespeichert.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse verweist die `CHeapPtrBase` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CHeapPtrBase` verweist auf NULL.

##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T *

Der Cast-Operator.

```
operator T*() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt [CHeapPtrBase::m_pData](#m_pdata).

##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes

Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die neue Menge von Arbeitsspeicher zugeordnet werden soll, in Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Speicher erfolgreich belegt, "false" andernfalls.

## <a name="see-also"></a>Siehe auch

[CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
