---
title: CRBTree-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18c8221b7e379d739dda3ebfa9cbc205d9f88af6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759544"
---
# <a name="crbtree-class"></a>CRBTree-Klasse

Diese Klasse stellt Methoden zum Erstellen und nutzen ein Rot-Schwarz-Baum.

## <a name="syntax"></a>Syntax

```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBTree
```

#### <a name="parameters"></a>Parameter

*K*  
Der Typ des Key-Element.

*V*  
Der Werttyp-Element.

*KTraits*  
Der Code, der zum Kopieren oder Verschieben von Hauptelementen verwendet wird. Finden Sie unter [CElementTraits-Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.

*VTraits*  
Der Code zum Kopieren oder verschieben Elemente mit dem Wert verwendet.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CRBTree::KINARGTYPE](#kinargtype)|Der Typ verwendet, wenn ein Schlüssel als Eingabeargument übergeben wird.|
|[CRBTree::KOUTARGTYPE](#koutargtype)|-Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.|
|[CRBTree::VINARGTYPE](#vinargtype)|Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.|
|[CRBTree::VOUTARGTYPE](#voutargtype)|Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.|

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[CRBTree::CPair-Klasse](#cpair_class)|Eine Klasse, die die Schlüssel-Wert-Elemente enthält.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRBTree:: ~ CRBTree](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Rufen Sie diese Methode, um die Position des Elements zu finden, die den nächsten Schlüssel verwendet.|
|[CRBTree::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer bestimmten Position in der Struktur abgerufen.|
|[CRBTree::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente in der Struktur zu erhalten.|
|[CRBTree::GetHeadPosition](#getheadposition)|Rufen Sie diese Methode, um den-Positionswerts für das Element am Anfang der Struktur abrufen.|
|[CRBTree::GetKeyAt](#getkeyat)|Rufen Sie diese Methode, um den Schlüssel aus einer bestimmten Position in der Struktur zu erhalten.|
|[CRBTree::GetNext](#getnext)|Rufen Sie diese Methode zum Abrufen der eines Zeigers auf ein Element in der `CRBTree` Objekt aus, und fahren Sie fort, der die Position zum nächsten Element.|
|[CRBTree::GetNextAssoc](#getnextassoc)|Rufen Sie diese Methode zum Abrufen des Schlüssels und Werts eines Elements in der Zuordnung gespeichert, und fahren Sie fort, der die Position zum nächsten Element.|
|[CRBTree::GetNextKey](#getnextkey)|Rufen Sie diese Methode zum Abrufen des Schlüssels eines Elements in der Struktur gespeichert, und fahren Sie fort, der die Position zum nächsten Element.|
|[CRBTree::GetNextValue](#getnextvalue)|Rufen Sie diese Methode rufen Sie den Wert eines Elements in der Struktur gespeichert, und fahren Sie fort, der die Position zum nächsten Element.|
|[CRBTree::GetPrev](#getprev)|Rufen Sie diese Methode zum Abrufen der eines Zeigers auf ein Element in der `CRBTree` Objekt aus, und klicken Sie dann die Position zum vorherigen Element zu aktualisieren.|
|[CRBTree::GetTailPosition](#gettailposition)|Rufen Sie diese Methode, um den-Positionswerts für das Element am Ende der Struktur abrufen.|
|[CRBTree::GetValueAt](#getvalueat)|Rufen Sie diese Methode zum Abrufen des Werts, der gespeichert wird, an der angegebenen Position in der `CRBTree` Objekt.|
|[CRBTree::IsEmpty](#isempty)|Rufen Sie diese Methode zum Prüfen auf eine leere Tree-Objekt.|
|[CRBTree::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CRBTree` Objekt.|
|[CRBTree::RemoveAt](#removeat)|Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CRBTree` Objekt.|
|[CRBTree::SetValueAt](#setvalueat)|Rufen Sie diese Methode zum Ändern des Werts, der gespeichert wird, an der angegebenen Position in der `CRBTree` Objekt.|

## <a name="remarks"></a>Hinweise

Ein Rot-Schwarz-Baum ist eine binäre Suche-Struktur, die eine zusätzliche verwendet von Informationen, die pro Knoten, um sicherzustellen, dass er bleibt "Ausbalanciert", die, die die Höhe der Struktur nicht werden unverhältnismäßig groß und die Leistung beeinträchtigen.

Diese Vorlagenklasse ist zur Verwendung von vorgesehen [CRBMap](../../atl/reference/crbmap-class.md) und [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Der Großteil der Methoden, die diese abgeleiteten Klassen bilden, werden von bereitgestellt `CRBTree`.

Eine umfassendere Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cpair_class"></a>  CRBTree::CPair-Klasse

Eine Klasse, die die Schlüssel-Wert-Elemente enthält.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Hinweise

Diese Klasse wird verwendet, von den Methoden [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), und [CRBTree::GetPrev](#getprev) Zugriff auf die Schlüssel-Wert-Elemente, die in der Struktur gespeichert.

Die Elemente sind wie folgt aus:

|||
|-|-|
|`m_key`|Der Datenmember, die das wichtigste Element gespeichert wird.|
|`m_value`|Der Datenmember, speichern das Value-Element.|

##  <a name="dtor"></a>  CRBTree:: ~ CRBTree

Der Destruktor.

```
~CRBTree() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei. Aufrufe [CRBTree::RemoveAll](#removeall) So löschen Sie alle Elemente.

##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter

Rufen Sie diese Methode, um die Position des Elements zu finden, die den nächsten Schlüssel verwendet.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parameter

*key*  
Ein Schlüssel-Wert.

### <a name="return-value"></a>Rückgabewert

Gibt den Positionswert des Elements, das den nächsten verfügbaren Schlüssel verwendet. Wenn keine Elemente mehr vorhanden sind, wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode vereinfacht die Struktur durchlaufen, ohne dass Positionswerte im Voraus berechnen.

##  <a name="getat"></a>  CRBTree::GetAt

Rufen Sie diese Methode, um das Element an einer bestimmten Position in der Struktur abgerufen.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parameter

*POS*  
Der Positionswert.

*key*  
Die Variable, die den Schlüssel erhält.

*Wert*  
Die Variable, die den Wert empfängt.

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Formen Geben Sie einen Zeiger auf eine [CPair](#cpair_class). Die dritte Form erhält einen Schlüssel und einen Wert für die angegebene Position.

### <a name="remarks"></a>Hinweise

Den-Positionswerts kann bestimmt werden, zuvor durch einen Aufruf einer Methode wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::GetTailPosition](#gettailposition).

Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

##  <a name="getcount"></a>  CRBTree::GetCount

Rufen Sie diese Methode, um die Anzahl der Elemente in der Struktur zu erhalten.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente, die in der Struktur gespeichert (jedes Schlüssel-Wert-Paar ist ein Element) zurück.

##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition

Rufen Sie diese Methode, um den-Positionswerts für das Element am Anfang der Struktur abrufen.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die Position für das Element am Anfang der Struktur zurück.

### <a name="remarks"></a>Hinweise

Der Rückgabewert von `GetHeadPosition` können mit Methoden verwendet werden, z. B. [CRBTree::GetKeyAt](#getkeyat) oder [CRBTree::GetNext](#getnext) die Struktur durchlaufen und Werte abrufen.

##  <a name="getkeyat"></a>  CRBTree::GetKeyAt

Rufen Sie diese Methode, um den Schlüssel aus einer bestimmten Position in der Struktur zu erhalten.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Positionswert.

### <a name="return-value"></a>Rückgabewert

Gibt den Schlüssel gespeichert, an der Position zurück *pos* in der Struktur.

### <a name="remarks"></a>Hinweise

Wenn *pos* ist kein gültiger Positionswert, Ergebnisse sind unvorhersehbar. Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

##  <a name="getnext"></a>  CRBTree::GetNext

Rufen Sie diese Methode zum Abrufen der eines Zeigers auf ein Element in der `CRBTree` Objekt aus, und fahren Sie fort, der die Position zum nächsten Element.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die nächste [CPair](#cpair_class) Wert in der Struktur.

### <a name="remarks"></a>Hinweise

Die *pos* Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte in der Struktur ist *pos* auf NULL festgelegt ist.

##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc

Rufen Sie diese Methode zum Abrufen des Schlüssels und Werts eines Elements in der Zuordnung gespeichert, und fahren Sie fort, der die Position zum nächsten Element.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*key*  
Der Vorlagenparameter, der den Typ des Schlüssels mit der Struktur angibt.

*Wert*  
Der Vorlagenparameter, der den Typ des Werts von der Struktur angibt.

### <a name="remarks"></a>Hinweise

Die *pos* Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte in der Struktur ist *pos* auf NULL festgelegt ist.

##  <a name="getnextkey"></a>  CRBTree::GetNextKey

Rufen Sie diese Methode zum Abrufen des Schlüssels eines Elements in der Struktur gespeichert, und fahren Sie fort, der die Position zum nächsten Element.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den nächsten Schlüssel in der Struktur zurück.

### <a name="remarks"></a>Hinweise

Aktualisiert die aktuelle Position-Indikator *pos*. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Position Zähler auf NULL festgelegt.

##  <a name="getnextvalue"></a>  CRBTree::GetNextValue

Rufen Sie diese Methode rufen Sie den Wert eines Elements in der Struktur gespeichert, und fahren Sie fort, der die Position zum nächsten Element.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den nächsten Wert in der Struktur zurück.

### <a name="remarks"></a>Hinweise

Aktualisiert die aktuelle Position-Indikator *pos*. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Position Zähler auf NULL festgelegt.

##  <a name="getprev"></a>  CRBTree::GetPrev

Rufen Sie diese Methode zum Abrufen der eines Zeigers auf ein Element in der `CRBTree` Objekt aus, und klicken Sie dann die Position zum vorherigen Element zu aktualisieren.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige [CPair](#cpair_class) Wert, der in der Struktur gespeichert.

### <a name="remarks"></a>Hinweise

Aktualisiert die aktuelle Position-Indikator *pos*. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Position Zähler auf NULL festgelegt.

##  <a name="gettailposition"></a>  CRBTree::GetTailPosition

Rufen Sie diese Methode, um den-Positionswerts für das Element am Ende der Struktur abrufen.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die Position für das Element am Ende der Struktur zurück.

### <a name="remarks"></a>Hinweise

Der Rückgabewert von `GetTailPosition` können mit Methoden verwendet werden, z. B. [CRBTree::GetKeyAt](#getkeyat) oder [CRBTree::GetPrev](#getprev) die Struktur durchlaufen und Werte abrufen.

##  <a name="getvalueat"></a>  CRBTree::GetValueAt

Rufen Sie diese Methode zum Abrufen des Werts, der gespeichert wird, an der angegebenen Position in der `CRBTree` Objekt.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den Wert gespeichert, an der angegebenen Position in der `CRBTree` Objekt.

##  <a name="isempty"></a>  CRBTree::IsEmpty

Rufen Sie diese Methode zum Prüfen auf eine leere Tree-Objekt.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Struktur leer ist, andernfalls FALSE.

##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE

Der Typ verwendet, wenn ein Schlüssel als Eingabeargument übergeben wird.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE

-Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="removeall"></a>  CRBTree::RemoveAll

Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CRBTree` Objekt.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Hinweise

Löscht die `CRBTree` Objekt, das der belegte Arbeitsspeicher zum Speichern der Elemente.

##  <a name="removeat"></a>  CRBTree::RemoveAt

Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CRBTree` Objekt.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="remarks"></a>Hinweise

Entfernt das Schlüssel/Wert-Paar, das an der angegebenen Position gespeichert. Der zum Speichern des Elements verwendete Arbeitsspeicher wird freigegeben. Die POSITION verweist *pos* ungültig, und behalten Sie während die POSITION der anderen Elemente in der Struktur gültig bleibt, sie sind nicht unbedingt die gleiche Reihenfolge.

##  <a name="setvalueat"></a>  CRBTree::SetValueAt

Rufen Sie diese Methode zum Ändern des Werts, der gespeichert wird, an der angegebenen Position in der `CRBTree` Objekt.

```
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Parameter

*POS*  
Der Position Zähler, der von einem vorherigen Aufruf von Methoden zurückgegeben wurde, z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*Wert*  
Der Wert, der zum Hinzufügen der `CRBTree` Objekt.

### <a name="remarks"></a>Hinweise

Ändert das Value-Element gespeichert wird, an der angegebenen Position in der `CRBTree` Objekt.

##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE

Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE

Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
