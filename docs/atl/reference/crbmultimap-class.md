---
title: CRBMultiMap-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
dev_langs:
- C++
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55a520a85b030338f420c5d6d6608d8609f44f2e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071088"
---
# <a name="crbmultimap-class"></a>CRBMultiMap-Klasse

Diese Klasse stellt eine Zuordnungsstruktur, die ermöglicht, dass jeder Schlüssel mit mehr als einem Wert, mit einer binären Rot-Schwarz-Struktur verknüpft werden kann.

## <a name="syntax"></a>Syntax

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>Parameter

*K*<br/>
Der Typ des Key-Element.

*V*<br/>
Der Werttyp-Element.

*KTraits*<br/>
Der Code, der zum Kopieren oder Verschieben von Hauptelementen verwendet wird. Finden Sie unter [CElementTraits-Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.

*VTraits*<br/>
Der Code zum Kopieren oder verschieben Elemente mit dem Wert verwendet.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Der Konstruktor.|
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Rufen Sie diese Methode, um die Position des ersten Elements mit einem vorhandenen Schlüssel zu finden.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Rufen Sie diese Methode, um einen bestimmten Schlüssel zugeordnete Wert zu erhalten, und aktualisieren Sie den Positionswert.|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Rufen Sie diese Methode, um das einem angegebenen Schlüssel zugeordnete Element zu erhalten, und aktualisieren Sie den Positionswert.|
|[CRBMultiMap::Insert](#insert)|Rufen Sie diese Methode zum Einfügen von einem Element-Paar in der Zuordnung.|
|[CRBMultiMap::RemoveKey](#removekey)|Rufen Sie diese Methode, um alle Elemente der Schlüssel-Wert für einen bestimmten Schlüssel zu entfernen.|

## <a name="remarks"></a>Hinweise

`CRBMultiMap` bietet Unterstützung für ein Array Zuordnung eines beliebigen angegebenen Typs, das ein geordnetes Array von wichtige Elemente und Werte verwalten. Im Gegensatz zu den [CRBMap](../../atl/reference/crbmap-class.md) -Klasse, jeder Schlüssel kann mehr als einem Wert zugeordnet werden.

Elemente (bestehend aus einem Schlüssel und Wert) befinden sich in einer binären Struktur-Struktur unter Verwendung der [CRBMultiMap::Insert](#insert) Methode. Elemente können entfernt werden, mithilfe der [CRBMultiMap::RemoveKey](#removekey) -Methode, die alle Elemente gelöscht, die mit den angegebenen Schlüssel übereinstimmen.

Die Struktur durchlaufen, wird Dank mit Methoden wie z. B. [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), und [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Zugriff auf die potenziell mehrere Werte pro Schlüssel möglich ist die Verwendung der [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), und [CRBMultiMap::GetNextWithKey ](#getnextwithkey) Methoden. Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap) eine Abbildung dieser in der Praxis.

Die *KTraits* und *VTraits* Parameter sind "traits"-Klassen, die alle zusätzlichen erforderlichen Code zum Kopieren oder Verschieben von Elementen enthalten.

`CRBMultiMap` stammt aus [CRBTree](../../atl/reference/crbtree-class.md), der eine binäre Struktur, die mit dem Rot-Schwarz-Algorithmus implementiert. Eine Alternative zum `CRBMultiMap` und `CRBMap` wird angeboten, indem die [CAtlMap](../../atl/reference/catlmap-class.md) Klasse. Wenn nur eine kleine Anzahl von Elementen gespeichert werden muss, erwägen Sie die Verwendung der [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.

Eine umfassendere Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="crbmultimap"></a>  CRBMultiMap::CRBMultiMap

Der Konstruktor.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Blockgröße.

### <a name="remarks"></a>Hinweise

Die *nBlockSize* -Parameter ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden. Der Standardwert wird Speicherplatz für 10 Elemente zu einem Zeitpunkt zugeordnet werden.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

##  <a name="dtor"></a>  CRBMultiMap:: ~ CRBMultiMap

Der Destruktor.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

##  <a name="findfirstwithkey"></a>  CRBMultiMap::FindFirstWithKey

Rufen Sie diese Methode, um die Position des ersten Elements mit einem vorhandenen Schlüssel zu finden.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.

### <a name="return-value"></a>Rückgabewert

Gibt die POSITION des ersten Elements der Schlüssel-Wert zurück, wenn der Schlüssel gefunden wird, NULL andernfalls.

### <a name="remarks"></a>Hinweise

Ein Schlüssel in der `CRBMultiMap` kann eine oder mehrere zugeordnete Werte aufweisen. Diese Methode wird die des ersten Werts (die in der Tat der einzige Wert sein kann) Schlüssel zugeordneten Positionswert dieser bestimmten bereit. Der Wert für die Position zurückgegeben kann dann verwendet werden, mit [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) oder [CRBMultiMap::GetNextWithKey](#getnextwithkey) zum Abrufen des Werts, und aktualisieren die Position.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="getnextvaluewithkey"></a>  CRBMultiMap::GetNextValueWithKey

Rufen Sie diese Methode, um einen bestimmten Schlüssel zugeordnete Wert zu erhalten, und aktualisieren Sie den Positionswert.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Wert für die Position, mit entweder einem Aufruf abgerufen [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) oder [CRBMultiMap::GetNextWithKey](#getnextwithkey), oder in einem vorherigen Aufruf von `GetNextValueWithKey`.

*key*<br/>
Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.

### <a name="return-value"></a>Rückgabewert

Gibt die Element-Paar, das dem angegebenen Schlüssel zugeordnet.

### <a name="remarks"></a>Hinweise

Zeigen Sie auf den nächsten Wert, der dem Schlüssel zugeordnete wird Wert für die Position aktualisiert. Wenn keine weitere Werte vorhanden sind, wird der Wert für die Position auf NULL festgelegt.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="getnextwithkey"></a>  CRBMultiMap::GetNextWithKey

Rufen Sie diese Methode, um das einem angegebenen Schlüssel zugeordnete Element zu erhalten, und aktualisieren Sie den Positionswert.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Wert für die Position, mit entweder einem Aufruf abgerufen [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) oder [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), oder in einem vorherigen Aufruf von `GetNextWithKey`.

*key*<br/>
Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.

### <a name="return-value"></a>Rückgabewert

Gibt die nächste [CRBTree::CPair Klasse](crbtree-class.md#cpair_class) dem angegebenen Schlüssel zugeordnete Element.

### <a name="remarks"></a>Hinweise

Zeigen Sie auf den nächsten Wert, der dem Schlüssel zugeordnete wird Wert für die Position aktualisiert. Wenn keine weitere Werte vorhanden sind, wird der Wert für die Position auf NULL festgelegt.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

##  <a name="insert"></a>  CRBMultiMap::Insert

Rufen Sie diese Methode zum Einfügen von einem Element-Paar in der Zuordnung.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüsselwert, Hinzufügen der `CRBMultiMap` Objekt.

*Wert*<br/>
Der Wert, der zum Hinzufügen der `CRBMultiMap` zugeordnete Objekt *Schlüssel*.

### <a name="return-value"></a>Rückgabewert

Gibt die Position eines Schlüssel/Wert-Element-Paar in der `CRBMultiMap` Objekt.

### <a name="remarks"></a>Hinweise

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="removekey"></a>  CRBMultiMap::RemoveKey

Rufen Sie diese Methode, um alle Elemente der Schlüssel-Wert für einen bestimmten Schlüssel zu entfernen.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Gibt den Schlüssel, der zu löschenden Elemente identifiziert.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Werte, die dem angegebenen Schlüssel zugeordnet.

### <a name="remarks"></a>Hinweise

`RemoveKey` Löscht alle Elemente der Schlüssel-Wert, der einen Schlüssel verfügen, die entspricht *Schlüssel*.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).

## <a name="see-also"></a>Siehe auch

[CRBTree-Klasse](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap-Klasse](../../atl/reference/catlmap-class.md)<br/>
[CRBMap-Klasse](../../atl/reference/crbmap-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
