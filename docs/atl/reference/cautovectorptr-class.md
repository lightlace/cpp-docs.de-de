---
title: CAutoVectorPtr-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d60a7f40fc90d5586d7a8a7d41cab81a4d97c85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054479"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr-Klasse

Diese Klasse stellt ein intelligenter Zeiger-Objekt, das mit der neuen Vektor dar und delete-Operator.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Zeigertyp.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Der Konstruktor.|
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAutoVectorPtr::Allocate](#allocate)|Rufen Sie diese Methode zum Belegen des Arbeitsspeichers, der das Array von Objekten, die auf den erforderlichen `CAutoVectorPtr`.|
|[CAutoVectorPtr::Attach](#attach)|Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.|
|[CAutoVectorPtr::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.|
|[CAutoVectorPtr::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts verweist eine `CAutoVectorPtr`.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoVectorPtr::operator T *](#operator_t__star)|Der Cast-Operator.|
|[CAutoVectorPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAutoVectorPtr::m_p](#m_p)|Die Zeiger-Membervariable.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zum Erstellen und verwalten einen intelligenten Zeiger, dadurch wird Schutz vor Speicherverluste durch Ressourcen automatisch freigegeben, wenn sie außerhalb des gültigen Bereichs liegt. `CAutoVectorPtr` ist vergleichbar mit `CAutoPtr`, der einzige Unterschied ist, dass `CAutoVectorPtr` verwendet [Vektor neue&#91; &#93; ](../../standard-library/new-operators.md#op_new_arr) und [Vektor löschen&#91; &#93; ](../../standard-library/new-operators.md#op_delete_arr) zum Zuordnen und Freigeben von Arbeitsspeicher anstelle der C++ **neue** und **löschen** Operatoren. Finden Sie unter [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) Wenn Auflistungsklassen von `CAutoVectorPtr` erforderlich sind.

Finden Sie unter [CAutoPtr](../../atl/reference/cautoptr-class.md) ein Beispiel der Verwendung einer intelligenten Zeiger-Klasse.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="allocate"></a>  CAutoVectorPtr::Allocate

Rufen Sie diese Methode zum Belegen des Arbeitsspeichers, der das Array von Objekten, die auf den erforderlichen `CAutoVectorPtr`.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parameter

*nElements*<br/>
Die Anzahl der Elemente im Array.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Speicher erfolgreich zugeordnet, "false" bei einem Fehler.

### <a name="remarks"></a>Hinweise

Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoVectorPtr::m_p](#m_p) Membervariable zeigt derzeit zu einem vorhandenen Wert; das heißt, ist es nicht gleich NULL.

##  <a name="attach"></a>  CAutoVectorPtr::Attach

Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Die `CAutoVectorPtr` Objekt übernimmt dann den Besitz des this-Zeigers.

### <a name="remarks"></a>Hinweise

Wenn eine `CAutoVectorPtr` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt. Wenn [CAutoVectorPtr::Detach](#detach) wird aufgerufen, der Programmierer ist erneut bei Verantwortung für die Freigabe alle zugeordneten Ressourcen.

Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoVectorPtr::m_p](#m_p) Membervariable zeigt derzeit zu einem vorhandenen Wert; das heißt, ist es nicht gleich NULL.

##  <a name="cautovectorptr"></a>  CAutoVectorPtr::CAutoVectorPtr

Der Konstruktor.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Einem vorhandenen Zeiger.

### <a name="remarks"></a>Hinweise

Die `CAutoVectorPtr` Objekt mit einem vorhandenen Zeiger erstellt werden kann, die in diesem Fall erfolgt die Übertragung des Besitzes des Zeigers.

##  <a name="dtor"></a>  CAutoVectorPtr:: ~ CAutoVectorPtr

Der Destruktor.

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei. Aufrufe [CAutoVectorPtr::Free](#free).

##  <a name="detach"></a>  CAutoVectorPtr::Detach

Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.

```
T* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Kopie des Zeigers.

### <a name="remarks"></a>Hinweise

Gibt den Besitz eines Zeigers, legt die [CAutoVectorPtr::m_p](#m_p) Membervariable für NULL-Werte und gibt eine Kopie des Zeigers zurück. Nach dem Aufruf `Detach`, es wird bis zu dem Programmierer, die eine kostenlose zugeordneten Ressourcen über den die `CAutoVectorPtr` Objekt möglicherweise zuvor Verantwortung angenommen haben.

##  <a name="free"></a>  CAutoVectorPtr::Free

Rufen Sie diese Methode zum Löschen eines Objekts verweist eine `CAutoVectorPtr`.

```
void Free() throw();
```

### <a name="remarks"></a>Hinweise

Das Objekt verweist die `CAutoVectorPtr` wird freigegeben, und die [CAutoVectorPtr::m_p](#m_p) Member-Variable auf NULL festgelegt ist.

##  <a name="m_p"></a>  CAutoVectorPtr::m_p

Die Zeiger-Membervariable.

```
T* m_p;
```

### <a name="remarks"></a>Hinweise

Diese Membervariable enthält Zeigerinformationen.

##  <a name="operator_eq"></a>  CAutoVectorPtr::operator =

Der Zuweisungsoperator.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf eine **CAutoVectorPtr\< T >**.

### <a name="remarks"></a>Hinweise

Der Zuweisungsoperator trennt die `CAutoVectorPtr` Objekt aus einem aktuellen Zeiger und fügt den neuen Zeiger *p*, an seiner Stelle.

##  <a name="operator_t__star"></a>  CAutoVectorPtr::operator T *

Der Cast-Operator.

```
operator T*() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.

## <a name="see-also"></a>Siehe auch

[CAutoPtr-Klasse](../../atl/reference/cautoptr-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
