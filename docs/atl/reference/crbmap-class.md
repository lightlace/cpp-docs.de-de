---
title: CRBMap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: e5dedb26544bb2755bc74894cf36a622f5141f89
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301505"
---
# <a name="crbmap-class"></a>CRBMap-Klasse

Diese Klasse stellt eine Zuordnungsstruktur, indem Sie eine binäre Rot-Schwarz-Baum.

## <a name="syntax"></a>Syntax

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMap::CRBMap](#crbmap)|Der Konstruktor.|
|[CRBMap::~CRBMap](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRBMap::Lookup](#lookup)|Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CRBMap` Objekt.|
|[CRBMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen eines Elements aus der `CRBMap` Objekt anhand des angegebenen Schlüssels.|
|[CRBMap::SetAt](#setat)|Rufen Sie diese Methode zum Einfügen von einem Element-Paar in der Zuordnung.|

## <a name="remarks"></a>Hinweise

`CRBMap` bietet Unterstützung für ein Array Zuordnung eines beliebigen angegebenen Typs, das ein geordnetes Array von wichtige Elemente und die zugehörigen Werte verwalten. Jeder Schlüssel kann nur einen zugeordneten Wert verfügen. Elemente (bestehend aus einem Schlüssel und Wert) befinden sich in einer binären Struktur-Struktur unter Verwendung der [CRBMap::SetAt](#setat) Methode. Elemente können entfernt werden, mithilfe der [CRBMap::RemoveKey](#removekey) -Methode, die das Element mit dem angegebenen Schlüssel-Wert werden gelöscht.

Die Struktur durchlaufen, wird Dank mit Methoden wie z. B. [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), und [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).

Die *KTraits* und *VTraits* Parameter sind "traits"-Klassen, die alle zusätzlichen erforderlichen Code zum Kopieren oder Verschieben von Elementen enthalten.

`CRBMap` stammt aus [CRBTree](../../atl/reference/crbtree-class.md), der eine binäre Struktur, die mit dem Rot-Schwarz-Algorithmus implementiert. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) ist eine Variante, die mehrere Werte für jeden Schlüssel zulässt. Es zu abgeleitet wird `CRBTree`, und so viele Funktionen mit `CRBMap`.

Eine Alternative für beide `CRBMap` und `CRBMultiMap` wird angeboten, indem die [CAtlMap](../../atl/reference/catlmap-class.md) Klasse. Wenn nur eine kleine Anzahl von Elementen gespeichert werden muss, erwägen Sie die Verwendung der [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.

Eine umfassendere Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="crbmap"></a>  CRBMap::CRBMap

Der Konstruktor.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Blockgröße.

### <a name="remarks"></a>Hinweise

Die *nBlockSize* -Parameter ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden. Der Standardwert wird Speicherplatz für 10 Elemente zu einem Zeitpunkt zugeordnet werden.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

##  <a name="dtor"></a>  CRBMap:: ~ CRBMap

Der Destruktor.

```
~CRBMap() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

##  <a name="lookup"></a>  CRBMap::Lookup

Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CRBMap` Objekt.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.

*value*<br/>
Variable, die den Wert der nachgeschlagenen empfängt.

### <a name="return-value"></a>Rückgabewert

Die erste Form der Methode gibt "true", wenn der Schlüssel gefunden wird, andernfalls "false" zurück. Die zweite und dritte Formulare Geben Sie einen Zeiger auf eine [CPair](crbtree-class.md#cpair_class).

### <a name="remarks"></a>Hinweise

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

##  <a name="removekey"></a>  CRBMap::RemoveKey

Rufen Sie diese Methode zum Entfernen eines Elements aus der `CRBMap` Objekt anhand des angegebenen Schlüssels.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Die entsprechenden auf das Element-Paar, die Sie entfernen möchten.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der Schlüssel gefunden und entfernt wurde, bei "false".

### <a name="remarks"></a>Hinweise

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

##  <a name="setat"></a>  CRBMap::SetAt

Rufen Sie diese Methode zum Einfügen von einem Element-Paar in der Zuordnung.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüsselwert, Hinzufügen der `CRBMap` Objekt.

*value*<br/>
Der Wert, der zum Hinzufügen der `CRBMap` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die Position eines Schlüssel/Wert-Element-Paar in der `CRBMap` Objekt.

### <a name="remarks"></a>Hinweise

`SetAt` ersetzt ein vorhandenes Element an, wenn ein passender Schlüssel gefunden wird. Wenn der Schlüssel nicht gefunden wird, wird ein neues Schlüssel/Wert-Paar erstellt.

Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[CRBTree-Klasse](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap-Klasse](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap-Klasse](../../atl/reference/crbmultimap-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
