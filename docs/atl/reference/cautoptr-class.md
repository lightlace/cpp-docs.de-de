---
title: CAutoPtr-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
ms.openlocfilehash: 7f4f446aa97f2bf3843b830bd7fb4c4a5d74ffdb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260161"
---
# <a name="cautoptr-class"></a>CAutoPtr-Klasse

Diese Klasse stellt einen intelligenten Zeiger-Objekt.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CAutoPtr
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Zeigertyp.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtr::CAutoPtr](#cautoptr)|Der Konstruktor.|
|[CAutoPtr::~CAutoPtr](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtr::Attach](#attach)|Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.|
|[CAutoPtr::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.|
|[CAutoPtr::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts verweist eine `CAutoPtr`.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtr::operator T *](#operator_t_star)|Der Cast-Operator.|
|[CAutoPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|
|[CAutoPtr::operator ->](#operator_ptr)|Der Zeiger-auf-Member-Operator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtr::m_p](#m_p)|Die Zeiger-Membervariable.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zum Erstellen und verwalten einen intelligenten Zeiger, dadurch wird Schutz vor Speicherverluste durch Ressourcen automatisch freigegeben, wenn sie außerhalb des gültigen Bereichs liegt.

Zudem `CAutoPtr`Kopierkonstruktor und der Zuweisung Operator übertragen den Besitz des Zeigers, kopieren Sie den Zeiger für die Quelle an den Ziel-Zeiger und den Zeiger für die Quelle auf NULL festlegen. Daher ist es unmöglich, zwei `CAutoPtr` Objekten jeweils den gleichen Zeiger speichern und dadurch die Möglichkeit, den gleichen Zeiger zweimal zu löschen.

`CAutoPtr` Außerdem vereinfacht die Erstellung von Sammlungen von Zeigern. Anstatt eine Auflistungsklasse ableiten und der Destruktor für die Außerkraftsetzung, es ist einfacher, stellen eine Auflistung von `CAutoPtr` Objekte. Wenn die Auflistung gelöscht wird, die `CAutoPtr` Objekte außerhalb des gültigen Bereichs wechseln und sich selbst automatisch zu löschen.

[CHeapPtr](../../atl/reference/cheapptr-class.md) und Varianten in die gleiche Weise wie `CAutoPtr`, außer dass sie die Belegung und Freigabe von Arbeitsspeicher mit verschiedenen Heapfunktionen anstelle der C++ **neue** und **löschen** Operatoren. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) ähnelt `CAutoPtr`, der einzige Unterschied, dass er verwendet **new []-Vektor** und **Vektor delete []** zum Zuordnen und Freigeben von Arbeitsspeicher.

Siehe auch [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) und [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) Wenn Arrays oder Listen von intelligenten Zeigern erforderlich sind.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

##  <a name="attach"></a>  CAutoPtr::Attach

Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Die `CAutoPtr` Objekt übernimmt dann den Besitz des this-Zeigers.

### <a name="remarks"></a>Hinweise

Wenn eine `CAutoPtr` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt. Wenn [CAutoPtr::Detach](#detach) wird aufgerufen, der Programmierer ist erneut bei Verantwortung für die Freigabe alle zugeordneten Ressourcen.

Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoPtr::m_p](#m_p) derzeit Datenmember verweist, zu einem vorhandenen Wert; das heißt, ist es nicht gleich NULL.

### <a name="example"></a>Beispiel

Siehe das Beispiel in der [CAutoPtr-Übersicht](../../atl/reference/cautoptr-class.md).

##  <a name="cautoptr"></a>  CAutoPtr::CAutoPtr

Der Konstruktor.

```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Einem vorhandenen Zeiger.

*TSrc*<br/>
Der Typ, der von einem anderen verwalteten `CAutoPtr`verwendet, um das aktuelle Objekt zu initialisieren.

### <a name="remarks"></a>Hinweise

Die `CAutoPtr` Objekt mit einem vorhandenen Zeiger erstellt werden kann, die in diesem Fall erfolgt die Übertragung des Besitzes des Zeigers.

### <a name="example"></a>Beispiel

Siehe das Beispiel in der [CAutoPtr-Übersicht](../../atl/reference/cautoptr-class.md).

##  <a name="dtor"></a>  CAutoPtr:: ~ CAutoPtr

Der Destruktor.

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei. Aufrufe [CAutoPtr::Free](#free).

##  <a name="detach"></a>  CAutoPtr::Detach

Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.

```
T* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Kopie des Zeigers.

### <a name="remarks"></a>Hinweise

Gibt den Besitz eines Zeigers, legt die [CAutoPtr::m_p](#m_p) Data-Member-Variable auf NULL, und gibt eine Kopie des Zeigers zurück. Nach dem Aufruf `Detach`, es wird bis zu dem Programmierer, die eine kostenlose zugeordneten Ressourcen über den die `CAutoPtr` Objekt möglicherweise bereits Reponsibility angenommen haben.

### <a name="example"></a>Beispiel

Siehe das Beispiel in der [CAutoPtr-Übersicht](../../atl/reference/cautoptr-class.md).

##  <a name="free"></a>  CAutoPtr::Free

Rufen Sie diese Methode zum Löschen eines Objekts verweist eine `CAutoPtr`.

```
void Free() throw();
```

### <a name="remarks"></a>Hinweise

Das Objekt verweist die `CAutoPtr` wird freigegeben, und die [CAutoPtr::m_p](#m_p) Data-Member-Variable auf NULL festgelegt ist.

##  <a name="m_p"></a>  CAutoPtr::m_p

Die Zeiger-Membervariable.

```
T* m_p;
```

### <a name="remarks"></a>Hinweise

Diese Membervariable enthält Zeigerinformationen.

##  <a name="operator_eq"></a>  CAutoPtr::operator =

Der Zuweisungsoperator.

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger.

*TSrc*<br/>
Ein Klassentyp.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf eine **CAutoPtr\< T >**.

### <a name="remarks"></a>Hinweise

Der Zuweisungsoperator trennt die `CAutoPtr` Objekt aus einem aktuellen Zeiger und fügt den neuen Zeiger *p*, an seiner Stelle.

### <a name="example"></a>Beispiel

Siehe das Beispiel in der [CAutoPtr-Übersicht](../../atl/reference/cautoptr-class.md).

##  <a name="operator_ptr"></a>  CAutoPtr::operator-&gt;

Der Zeiger-auf-Member-Operator.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des der [CAutoPtr::m_p](#m_p) Daten Membervariablen gespeichert.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse verweist die `CAutoPtr` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CAutoPtr` verweist auf NULL.

### <a name="example"></a>Beispiel

Siehe das Beispiel in der [CAutoPtr-Übersicht](../../atl/reference/cautoptr-class.md).

##  <a name="operator_t_star"></a>  CAutoPtr::operator T *

Der Cast-Operator.

```
operator T* () const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.

### <a name="example"></a>Beispiel

Siehe das Beispiel in der [CAutoPtr-Übersicht](../../atl/reference/cautoptr-class.md).

## <a name="see-also"></a>Siehe auch

[CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr-Klasse](../../atl/reference/cautovectorptr-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
