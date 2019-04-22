---
title: CAtlMap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: 1821532a4d5a3078202f180273b02945b8d8e4ba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774554"
---
# <a name="catlmap-class"></a>CAtlMap-Klasse

Diese Klasse stellt Methoden zum Erstellen und Verwalten von einem Map-Objekt.

## <a name="syntax"></a>Syntax

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
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

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CAtlMap::KINARGTYPE](#kinargtype)|Typ verwendet, wenn ein Schlüssel, als Eingabeargument übergeben wird|
|[CAtlMap::KOUTARGTYPE](#koutargtype)|-Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.|
|[CAtlMap::VINARGTYPE](#vinargtype)|Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.|
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.|

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[CAtlMap::CPair-Klasse](#cpair_class)|Eine Klasse, die die Schlüssel-Wert-Elemente enthält.|

### <a name="cpair-data-members"></a>CPair-Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPair::m_key](#m_key)|Der Datenmember, die das wichtigste Element gespeichert wird.|
|[CPair::m_value](#m_value)|Der Datenmember, speichern das Value-Element.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlMap::CAtlMap](#catlmap)|Der Konstruktor.|
|[CAtlMap::~CAtlMap](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlMap::AssertValid](#assertvalid)|Rufen Sie diese Methode, um eine ASSERTION verursacht, wenn die `CAtlMap` ist ungültig.|
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Rufen Sie diese Methode zum Deaktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.|
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Rufen Sie diese Methode zum Aktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.|
|[CAtlMap::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Zuordnung zurück.|
|[CAtlMap::GetCount](#getcount)|Rufen Sie diese Methode zum Abrufen der Anzahl der Elemente in der Zuordnung.|
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Rufen Sie diese Methode zum Ermitteln der Anzahl der Klassen in der Map-Hashtabelle.|
|[CAtlMap::GetKeyAt](#getkeyat)|Rufen Sie diese Methode zum Abrufen des Schlüssels an der angegebenen Position in der `CAtlMap` Objekt.|
|[CAtlMap::GetNext](#getnext)|Rufen Sie diese Methode, um einen Zeiger auf das nächste Element erhalten-Paar, in gespeichert der `CAtlMap` Objekt.|
|[CAtlMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|
|[CAtlMap::GetNextKey](#getnextkey)|Rufen Sie diese Methode zum Abrufen des nächsten Schlüssels aus der `CAtlMap` Objekt.|
|[CAtlMap::GetNextValue](#getnextvalue)|Rufen Sie diese Methode zum Abrufen des nächsten Wert aus der `CAtlMap` Objekt.|
|[CAtlMap::GetStartPosition](#getstartposition)|Rufen Sie diese Methode, um eine Zuordnung Iteration starten.|
|[CAtlMap::GetValueAt](#getvalueat)|Rufen Sie diese Methode zum Abrufen des Werts, der gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.|
|[CAtlMap::InitHashTable](#inithashtable)|Rufen Sie diese Methode, um die Hashtabelle zu initialisieren.|
|[CAtlMap::IsEmpty](#isempty)|Rufen Sie diese Methode für ein Objekt für die leere Zuordnung testen.|
|[CAtlMap::Lookup](#lookup)|Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CAtlMap` Objekt.|
|[CAtlMap::Rehash](#rehash)|Rufen Sie diese rehash-Methode der `CAtlMap` Objekt.|
|[CAtlMap::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CAtlMap` Objekt.|
|[CAtlMap::RemoveAtPos](#removeatpos)|Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CAtlMap` Objekt.|
|[CAtlMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen eines Elements aus der `CAtlMap` Objekt anhand des angegebenen Schlüssels.|
|[CAtlMap::SetAt](#setat)|Rufen Sie diese Methode zum Einfügen von einem Element-Paar in der Zuordnung.|
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Rufen Sie diese Methode, um die optimale Last legen die `CAtlMap` Objekt.|
|[CAtlMap::SetValueAt](#setvalueat)|Rufen Sie diese Methode zum Ändern des Werts, der gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Ersetzt oder fügt ein neues Element auf der `CAtlMap`.|

## <a name="remarks"></a>Hinweise

`CAtlMap` bietet Unterstützung für ein Array Zuordnung eines Typs, Verwalten von ungeordneten Bytearray wichtige Elemente und die zugehörigen Werte. Elemente (bestehend aus einem Schlüssel und Wert) werden gespeichert, wobei im verwendeten Hashalgorithmus, sodass eine große Menge von Daten effizient gespeichert und abgerufen werden.

Die *KTraits* und *VTraits* Parameter sind "traits"-Klassen, die alle zusätzlichen erforderlichen Code zum Kopieren oder Verschieben von Elementen enthalten.

Eine Alternative zum `CAtlMap` wird angeboten, indem die [CRBMap](../../atl/reference/crbmap-class.md) Klasse. `CRBMap` Außerdem werden die Schlüssel/Wert-Paare gespeichert, jedoch weist unterschiedliche Leistungsmerkmale. Die Zeit zum Einfügen eines Elements, suchen Sie nach einem Schlüssel, oder löschen ein Schlüssels aus einem `CRBMap` Objekt ist, der Reihenfolge *log(n)*, wobei *n* ist die Anzahl der Elemente. Für `CAtlMap`, alle diese Vorgänge in der Regel einen Konstanten Zeit dauern, dennoch Worst-Case-Szenarien möglicherweise eine Bestellung ist *n*. Aus diesem Grund in einem typischen Fall `CAtlMap` ist schneller.

Ein weiterer Unterschied zwischen `CRBMap` und `CAtlMap` wird offensichtlich, wenn die gespeicherte Elemente durchlaufen. In einem `CRBMap`, die Elemente in einer sortierten Reihenfolge besucht werden. In einem `CAtlMap`, die Elemente werden nicht sortiert werden und keine Reihenfolge abgeleitet werden kann.

Wenn eine kleine Anzahl von Elementen gespeichert werden muss, erwägen Sie die Verwendung der [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="assertvalid"></a>  CAtlMap::AssertValid

Rufen Sie diese Methode, um eine ASSERTION verursacht, wenn die `CAtlMap` -Objekt ist ungültig.

```
void AssertValid() const;
```

### <a name="remarks"></a>Hinweise

In der Debug-Builds: Diese Methode eine ASSERTION verursacht, wenn die `CAtlMap` -Objekt ist ungültig.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="catlmap"></a>  CAtlMap::CAtlMap

Der Konstruktor.

```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>Parameter

*nBins*<br/>
Die Anzahl der Klassen stellt Zeiger auf die gespeicherten Elemente. Finden Sie unter "Hinweise" weiter unten in diesem Thema finden Sie eine Erläuterung der Klassen ein.

*fOptimalLoad*<br/>
Das optimale Auslastung-Verhältnis.

*fLoThreshold*<br/>
Der untere Schwellenwert für die Load-Verhältnis.

*fHiThreshold*<br/>
Der obere Schwellenwert für die Load-Verhältnis.

*nBlockSize*<br/>
Die Blockgröße.

### <a name="remarks"></a>Hinweise

`CAtlMap` verweist auf alle gespeicherten Elemente, indem Sie zunächst einen Index, wobei im verwendeten Hashalgorithmus für den Schlüssel. Dieser Index verweist auf eine "Bin" der einen Zeiger auf die gespeicherten Elemente enthält. Wenn die "bin" bereits verwendet wird, wird eine verknüpfte Liste erstellt, für den Zugriff auf die nachfolgenden Elemente. Durchlaufen eine Liste ist langsamer als die direkten Zugriff auf das richtige Element, und die Struktur der Zuordnung muss also speicheranforderungen anhand der Leistung abwägen. Die Standardparameter wurden ausgewählt, um gute Ergebnisse in den meisten Fällen liefern.

Das Verhältnis der Auslastung ist das Verhältnis der Anzahl von Klassen, die Anzahl der Elemente in der Map-Objekt gespeichert. Wenn die Struktur der Zuordnung neu berechnet wird, die *fOptimalLoad* Parameterwert wird verwendet, um die Anzahl der erforderlichen Klassen zu berechnen. Dieser Wert kann geändert werden, mithilfe der [CAtlMap::SetOptimalLoad](#setoptimalload) Methode.

Die *fLoThreshold* -Parameter ist der niedrigere Wert, der das Load-Verhältnis, bevor erreichen kann `CAtlMap` berechnet die optimale Größe der Zuordnung neu.

Die *fHiThreshold* -Parameter ist der obere Wert, der das Load-Verhältnis, bevor erreichen kann die `CAtlMap` Objekts berechnet die optimale Größe der Zuordnung neu.

Hierzu eine neuberechnung (erneutes Hashing durchführen genannt) ist standardmäßig aktiviert. Wenn Sie dabei ggf. deaktivieren, wenn Sie große Datenmengen gleichzeitig Aufruf eingeben möchten die [CAtlMap::DisableAutoRehash](#disableautorehash) Methode. Reaktivieren sie mit der [CAtlMap::EnableAutoRehash](#enableautorehash) Methode.

Die *nBlockSize* -Parameter ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.

Bevor alle Daten gespeichert werden können, ist es erforderlich, initialisieren Sie die Hashtabelle mit einem Aufruf von [CAtlMap::InitHashTable](#inithashtable).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

##  <a name="dtor"></a>  CAtlMap:: ~ CAtlMap

Der Destruktor.

```
~CAtlMap() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

##  <a name="cpair_class"></a>  CAtlMap::CPair-Klasse

Eine Klasse, die die Schlüssel-Wert-Elemente enthält.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Hinweise

Diese Klasse wird verwendet, von den Methoden [CAtlMap::GetNext](#getnext) und [CAtlMap::Lookup](#lookup) Zugriff auf die Schlüssel-Wert-Elemente, die in der Zuordnungsstruktur gespeichert.

##  <a name="disableautorehash"></a>  CAtlMap::DisableAutoRehash

Rufen Sie diese Methode zum Deaktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.

```
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Hinweise

Wenn automatisches erneutes Hashing durchführen aktiviert ist (was sie in der Standardeinstellung ist), wird die Anzahl der Klassen in der Hashtabelle automatisch neu berechnet werden der Load-Wert (das Verhältnis der Anzahl von Klassen, die Anzahl der Elemente im Array gespeicherten) überschreitet die maximale oder minimale Werte zum Zeitpunkt die Zuordnung erstellt wurde angegeben.

`DisableAutoRehash` ist besonders hilfreich, wenn eine große Anzahl von Elementen der Karte auf einmal hinzugefügt werden. Anstelle den rehashing Prozess auslösen, jedes Mal, wenn die Grenzwerte überschritten werden, es ist jedoch effizienter aufzurufende `DisableAutoRehash`, fügen Sie Elemente hinzu und rufen Sie zum Schluss [CAtlMap::EnableAutoRehash](#enableautorehash).

##  <a name="enableautorehash"></a>  CAtlMap::EnableAutoRehash

Rufen Sie diese Methode zum Aktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.

```
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Hinweise

Wenn automatisches erneutes Hashing durchführen aktiviert ist (was sie in der Standardeinstellung ist), wird die Anzahl der Klassen in der Hashtabelle automatisch neu berechnet werden der Load-Wert (das Verhältnis der Anzahl von Klassen, die Anzahl der Elemente im Array gespeicherten) überschreitet die maximale oder minimale Werte zum Zeitpunkt die Zuordnung wurde angegeben.

`EnableAutoRefresh` wird am häufigsten verwendet, nach einem Aufruf von [CAtlMap::DisableAutoRehash](#disableautorehash).

##  <a name="getat"></a>  CAtlMap::GetAt

Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Zuordnung zurück.

```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

*key*<br/>
Der Vorlagenparameter, die den Typ des Schlüssels mit der Karte.

*value*<br/>
Der Vorlagenparameter, der den Typ des Werts von der Karte angibt.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das aktuelle Paar von Schlüssel/Wert-Elementen, die in der Zuordnung gespeichert.

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

##  <a name="getcount"></a>  CAtlMap::GetCount

Rufen Sie diese Methode zum Abrufen der Anzahl der Elemente in der Zuordnung.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente in der Map-Objekt zurück. Ein einzelnes Element ist ein Schlüssel/Wert-Paar.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="gethashtablesize"></a>  CAtlMap::GetHashTableSize

Rufen Sie diese Methode zum Ermitteln der Anzahl der Klassen in der Map-Hashtabelle.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Klassen in der Hashtabelle zurück. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) erläutert.

##  <a name="getkeyat"></a>  CAtlMap::GetKeyAt

Rufen Sie diese Methode zum Abrufen des Schlüssels an der angegebenen Position in der `CAtlMap` Objekt.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den Schlüssel gespeichert, an der angegebenen Position in der `CAtlMap` Objekt.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="getnext"></a>  CAtlMap::GetNext

Rufen Sie diese Methode, um einen Zeiger auf das nächste Element erhalten-Paar, in gespeichert der `CAtlMap` Objekt.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die nächsten Paar von Schlüssel/Wert-Elementen, die in der Zuordnung gespeicherten zurück. Die *pos* Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte in der Zuordnung *pos* auf NULL festgelegt ist.

##  <a name="getnextassoc"></a>  CAtlMap::GetNextAssoc

Ruft das nächste Element durchlaufen werden können.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

*key*<br/>
Der Vorlagenparameter, die den Typ des Schlüssels mit der Karte.

*value*<br/>
Der Vorlagenparameter, der den Typ des Werts von der Karte angibt.

### <a name="remarks"></a>Hinweise

Die *pos* Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte in der Zuordnung *pos* auf NULL festgelegt ist.

##  <a name="getnextkey"></a>  CAtlMap::GetNextKey

Rufen Sie diese Methode zum Abrufen des nächsten Schlüssels aus der `CAtlMap` Objekt.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den nächsten Schlüssel in der Zuordnung zurück.

### <a name="remarks"></a>Hinweise

Aktualisiert die aktuelle Position-Indikator *pos*. Wenn keine weiteren Einträge in der Zuordnung vorhanden sind, wird der Position Zähler auf NULL festgelegt.

##  <a name="getnextvalue"></a>  CAtlMap::GetNextValue

Rufen Sie diese Methode zum Abrufen des nächsten Wert aus der `CAtlMap` Objekt.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den nächsten Wert in der Zuordnung zurück.

### <a name="remarks"></a>Hinweise

Aktualisiert die aktuelle Position-Indikator *pos*. Wenn keine weiteren Einträge in der Zuordnung vorhanden sind, wird der Position Zähler auf NULL festgelegt.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="getstartposition"></a>  CAtlMap::GetStartPosition

Rufen Sie diese Methode, um eine Zuordnung Iteration starten.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt zurück, der die Anfangsposition oder NULL zurückgegeben wird, wenn die Zuordnung leer ist.

### <a name="remarks"></a>Hinweise

Aufruf dieser Methode eine Iteration für die Zuordnung zu starten, indem Sie eine POSITION zurückgegeben Wert übergeben werden kann, um die `GetNextAssoc` Methode.

> [!NOTE]
>  Die Sequenz der Iteration ist nicht vorhersagbar

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="getvalueat"></a>  CAtlMap::GetValueAt

Rufen Sie diese Methode zum Abrufen des Werts, der gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den Wert gespeichert, an der angegebenen Position in der `CAtlMap` Objekt.

##  <a name="inithashtable"></a>  CAtlMap::InitHashTable

Rufen Sie diese Methode, um die Hashtabelle zu initialisieren.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Parameter

*nBins*<br/>
Die Anzahl der Klassen, die von der Hashtabelle verwendet werden soll. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) erläutert.

*bAllocNow*<br/>
Ein Flag Hinweis darauf, wenn der Speicher zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, bei der erfolgreichen Initialisierung, bei "false".

### <a name="remarks"></a>Hinweise

`InitHashTable` muss aufgerufen werden, bevor alle Elemente in der Hashtabelle gespeichert werden.  Wenn diese Methode nicht explizit aufgerufen wird, aufgerufen wird automatisch beim ersten ein Element hinzugefügt wird, mit der Anzahl der "bin" gemäß der `CAtlMap` Konstruktor.  Andernfalls die Zuordnung wird initialisiert mithilfe der neuen Anzahl von "bin" gemäß der *nBins* Parameter.

Wenn die *bAllocNow* Parameter ist "false", die vom der Hashtabelle benötigte Speicher wird nicht zugewiesen werden, bis es zuerst erforderlich ist. Dies kann nützlich sein, wenn es ist nicht sicher sind, wenn die Zuordnung verwendet wird.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="isempty"></a>  CAtlMap::IsEmpty

Rufen Sie diese Methode für ein Objekt für die leere Zuordnung testen.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Zuordnung leer ist, andernfalls FALSE.

##  <a name="kinargtype"></a>  CAtlMap::KINARGTYPE

Der Typ verwendet, wenn ein Schlüssel als Eingabeargument übergeben wird.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CAtlMap::KOUTARGTYPE

-Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="lookup"></a>  CAtlMap::Lookup

Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CAtlMap` Objekt.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.

*value*<br/>
Variable, die den Wert der nachgeschlagenen empfängt.

### <a name="return-value"></a>Rückgabewert

Die erste Form der Methode gibt "true", wenn der Schlüssel gefunden wird, andernfalls "false" zurück. Die zweite und dritte Formulare Geben Sie einen Zeiger auf eine [CPair](#cpair_class) die als eine Position für Aufrufe verwendet werden können [CAtlMap::GetNext](#getnext) und so weiter.

### <a name="remarks"></a>Hinweise

`Lookup` verwendet einen Hashalgorithmus schnell und problemlos suchen des Map-Elements, das mit einem Schlüssel, der den angegebenen Schlüsselparameter genau übereinstimmt.

##  <a name="operator_at"></a>  CAtlMap::operator \[\]

Ersetzt oder fügt ein neues Element auf der `CAtlMap`.

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüssel des Elements, das Hinzufügen oder ersetzen.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den Wert, der dem angegebenen Schlüssel zugeordnet.

### <a name="example"></a>Beispiel

Wenn der Schlüssel bereits vorhanden ist, wird das Element ersetzt. Wenn der Schlüssel nicht vorhanden ist, wird ein neues Element hinzugefügt. Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="rehash"></a>  CAtlMap::Rehash

Rufen Sie diese rehash-Methode der `CAtlMap` Objekt.

```
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Parameter

*nBins*<br/>
Die neue Anzahl von Containern in der Hashtabelle verwendet werden soll. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) erläutert.

### <a name="remarks"></a>Hinweise

Wenn *nBins* ist 0 (null) `CAtlMap` berechnet eine angemessene Anzahl basierend auf der Anzahl der Elemente in der Zuordnung und der optimale Auslastung-Einstellung. Der rehashing Prozess erfolgt normalerweise automatisch, aber wenn [CAtlMap::DisableAutoRehash](#disableautorehash) wurde aufgerufen wird, diese Methode führt die erforderlichen Größe ändern.

##  <a name="removeall"></a>  CAtlMap::RemoveAll

Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CAtlMap` Objekt.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Hinweise

Löscht die `CAtlMap` Objekt, das der belegte Arbeitsspeicher zum Speichern der Elemente.

##  <a name="removeatpos"></a>  CAtlMap::RemoveAtPos

Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CAtlMap` Objekt.

```
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

### <a name="remarks"></a>Hinweise

Entfernt das Schlüssel/Wert-Paar, das an der angegebenen Position gespeichert. Der zum Speichern des Elements verwendete Arbeitsspeicher wird freigegeben. Die POSITION verweist *pos* ungültig, und behalten Sie während die POSITION der anderen Elemente in der Zuordnung gültig bleibt, sie sind nicht unbedingt die gleiche Reihenfolge.

##  <a name="removekey"></a>  CAtlMap::RemoveKey

Rufen Sie diese Methode zum Entfernen eines Elements aus der `CAtlMap` Objekt anhand des angegebenen Schlüssels.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Die entsprechenden auf das Element-Paar, die Sie entfernen möchten.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Schlüssel gefunden und entfernt wurde, bei "false".

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).

##  <a name="setat"></a>  CAtlMap::SetAt

Rufen Sie diese Methode zum Einfügen von einem Element-Paar in der Zuordnung.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüsselwert, Hinzufügen der `CAtlMap` Objekt.

*value*<br/>
Der Wert, der zum Hinzufügen der `CAtlMap` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die Position eines Schlüssel/Wert-Element-Paar in der `CAtlMap` Objekt.

### <a name="remarks"></a>Hinweise

`SetAt` ersetzt ein vorhandenes Element an, wenn ein passender Schlüssel gefunden wird. Wenn der Schlüssel nicht gefunden wird, wird ein neues Schlüssel/Wert-Paar erstellt.

##  <a name="setoptimalload"></a>  CAtlMap::SetOptimalLoad

Rufen Sie diese Methode, um die optimale Last legen die `CAtlMap` Objekt.

```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Parameter

*fOptimalLoad*<br/>
Das optimale Auslastung-Verhältnis.

*fLoThreshold*<br/>
Der untere Schwellenwert für die Load-Verhältnis.

*fHiThreshold*<br/>
Der obere Schwellenwert für die Load-Verhältnis.

*bRehashNow*<br/>
Flag zum angeben, wenn die Hashtabelle neu berechnet werden sollen.

### <a name="remarks"></a>Hinweise

Diese Methode definiert den Wert für eine optimale Auslastung für die `CAtlMap` Objekt. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erläuterung der verschiedenen Parameter. Wenn *bRehashNow* ist "true", und die Anzahl von Elementen außerhalb der minimalen und maximalen Werte, die Hashtabelle neu berechnet.

##  <a name="setvalueat"></a>  CAtlMap::SetValueAt

Rufen Sie diese Methode zum Ändern des Werts, der gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.

```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parameter

*pos*<br/>
Der Position Zähler, der von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).

*value*<br/>
Der Wert, der zum Hinzufügen der `CAtlMap` Objekt.

### <a name="remarks"></a>Hinweise

Ändert das Value-Element gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.

##  <a name="vinargtype"></a>  CAtlMap::VINARGTYPE

Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CAtlMap::VOUTARGTYPE

Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

##  <a name="m_key"></a>  CAtlMap::CPair::m_key

Der Datenmember, die das wichtigste Element gespeichert wird.

```
const K m_key;
```

### <a name="parameters"></a>Parameter

*K*<br/>
Der Typ des Key-Element.

##  <a name="m_value"></a>  CAtlMap::CPair::m_value

Der Datenmember, speichern das Value-Element.

```
V  m_value;
```

### <a name="parameters"></a>Parameter

*V*<br/>
Der Werttyp-Element.

## <a name="see-also"></a>Siehe auch

[Marquee-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
