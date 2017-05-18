---
title: CAtlMap Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3730827a56c47497db2fd8324f54c7ba88a584d6
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="catlmap-class"></a>CAtlMap-Klasse
Diese Klasse stellt Methoden zum Erstellen und Verwalten von Map-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>>
class CAtlMap
```  
  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Key-Element.  
  
 V  
 Der Wert-Elementtyp.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
 `VTraits`  
 Der Code kopieren oder verschieben Elemente mit dem Wert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|Typ verwendet, wenn ein Schlüssel, als Eingabeargument übergeben wird|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|-Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.|  
|[CAtlMap::VINARGTYPE](#vinargtype)|-Typ, wenn der Wert als Eingabeargument übergeben wird.|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|-Typ, wenn der Wert als ausgabeargument übergeben wird.|  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::CPair-Klasse](#cpair_class)|Eine Klasse, die die Schlüssel-Wert-Elemente enthält.|  

  
### <a name="cpair-data-members"></a>CPair-Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|Das Datenelement, das wichtigste Element speichern.|  
|[CPair::m_value](#m_value)|Der Datenmember, speichern das Value-Element.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|Der Konstruktor.|  
|[CAtlMap:: ~ CAtlMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|Rufen Sie diese Methode, um eine Bestätigung verursachen, wenn die `CAtlMap` ist ungültig.|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Rufen Sie diese Methode zum Deaktivieren der automatischen Auflösen von der `CAtlMap` Objekt.|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Rufen Sie diese Methode zum Aktivieren der automatischen Auflösen von der `CAtlMap` Objekt.|  
|[CAtlMap::GetAt](#getat)|Rufen Sie diese Methode, um das Element an der angegebenen Position in der Zuordnung zurück.|  
|[CAtlMap::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente in der Zuordnung ab.|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Rufen Sie diese Methode, um die Anzahl der Klassen in der Hashtabelle der Zuordnung zu bestimmen.|  
|[CAtlMap::GetKeyAt](#getkeyat)|Rufen Sie diese Methode zum Abrufen des Schlüssels an der angegebenen Position in der `CAtlMap` Objekt.|  
|[CAtlMap::GetNext](#getnext)|Rufen Sie diese Methode, um einen Zeiger auf das nächste Element erhalten Paar, in gespeichert dem `CAtlMap` Objekt.|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|  
|[CAtlMap::GetNextKey](#getnextkey)|Rufen Sie diese Methode zum Abrufen des nächsten aus der `CAtlMap` Objekt.|  
|[CAtlMap::GetNextValue](#getnextvalue)|Rufen Sie diese Methode zum Abrufen des nächsten Wert aus der `CAtlMap` Objekt.|  
|[CAtlMap::GetStartPosition](#getstartposition)|Rufen Sie diese Methode, um eine Zuordnung Iteration starten.|  
|[CAtlMap::GetValueAt](#getvalueat)|Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CAtlMap` Objekt.|  
|[CAtlMap::InitHashTable](#inithashtable)|Rufen Sie diese Methode, um die Hashtabelle zu initialisieren.|  
|[CAtlMap::IsEmpty](#isempty)|Rufen Sie diese Methode für ein Objekt leere Zuordnung testen.|  
|[CAtlMap::Lookup](#lookup)|Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CAtlMap` Objekt.|  
|[CAtlMap::Rehash](#rehash)|Rufen Sie diese Methode zum rehash der `CAtlMap` Objekt.|  
|[CAtlMap::RemoveAll](#removeall)|Rufen Sie diese Methode zum Entfernen aller Elemente aus der `CAtlMap` Objekt.|  
|[CAtlMap::RemoveAtPos](#removeatpos)|Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CAtlMap` Objekt.|  
|[CAtlMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen eines Elements aus der `CAtlMap` -Objekt, den Schlüssel.|  
|[CAtlMap::SetAt](#setat)|Rufen Sie diese Methode, um ein Element in der Zuordnung einzufügen.|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Rufen Sie diese Methode, um die optimale Auslastung der Festlegen der `CAtlMap` Objekt.|  
|[CAtlMap::SetValueAt](#setvalueat)|Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CAtlMap` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Ersetzt oder fügt ein neues Element auf der `CAtlMap`.|  

  
## <a name="remarks"></a>Hinweise  
 `CAtlMap`bietet Unterstützung für eine Zuordnung Array eines beliebigen angegebenen Typs, das Verwalten von Array von ungeordneten der wichtigsten Elemente und die zugehörigen Werte. Elemente (bestehend aus einem Schlüssel und Wert) befinden, mithilfe eines Hashalgorithmus, sodass eine große Menge Daten effizient gespeichert und abgerufen werden.  
  
 Die `KTraits` und `VTraits` Parameter sind Klassen, die alle zusätzlichen Code zum Kopieren oder Verschieben von Elementen enthalten.  
  
 Eine Alternative zum `CAtlMap` wird die [CRBMap](../../atl/reference/crbmap-class.md) Klasse. `CRBMap`auch werden die Schlüssel-Wert-Paare gespeichert, aber unterschiedliche Leistungsmerkmale aufweist. Die Zeit zum Einfügen eines Elements nach einem Schlüssel zu suchen, oder Löschen eines Schlüssels aus einem `CRBMap` Objekt ist der Reihenfolge *log(n)*, wobei *n* ist die Anzahl der Elemente. Für `CAtlMap`, alle diese Vorgänge in der Regel dauern Konstante zwar ungünstigsten Bestellung *n*. Daher in normalen Fall `CAtlMap` ist schneller.  
  
 Ein weiterer Unterschied zwischen `CRBMap` und `CAtlMap` wird deutlich, wenn die gespeicherte Elemente durchlaufen. In einer `CRBMap`, die Elemente in einer sortierten Reihenfolge besucht werden. In einer `CAtlMap`, die Elemente werden nicht sortiert und keine Reihenfolge abgeleitet werden kann.  
  
 Wenn eine kleine Anzahl von Elementen gespeichert werden muss, sollten Sie mithilfe der [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="assertvalid"></a>CAtlMap::AssertValid  
 Rufen Sie diese Methode, um eine Bestätigung verursachen, wenn die `CAtlMap` -Objekt ist ungültig.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds diese Methode ASSERT verursachen, wenn die `CAtlMap` -Objekt ist ungültig.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="catlmap"></a>CAtlMap::CAtlMap  
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
 `nBins`  
 Die Anzahl der Klassen, die Hinweise auf die gespeicherten Elemente. Finden Sie unter "Hinweise" weiter unten in diesem Thema eine Erläuterung der Klassen ein.  
  
 `fOptimalLoad`  
 Die optimale Auslastung-Verhältnis.  
  
 `fLoThreshold`  
 Der untere Schwellenwert für das Load-Verhältnis.  
  
 `fHiThreshold`  
 Der obere Schwellenwert für das Load-Verhältnis.  
  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 `CAtlMap`verweist auf alle gespeicherten Elemente durch Erstellen eines Indexes mithilfe eines Hashalgorithmus auf den Schlüssel. Dieser Index verweist auf ein "Bin" enthält einen Zeiger auf die gespeicherten Elemente. Wenn die Bin bereits verwendet wird, ist eine verknüpfte Liste erstellt, für den Zugriff auf die nachfolgenden Elemente. Durchlaufen eine Liste ist langsamer als der direkte Zugriff auf das richtige Element, und die Struktur der Zuordnung muss also Speicherbedarf für Leistung abwägen. Die Standardparameter wurden ausgewählt, um gute Ergebnisse in den meisten Fällen liefern.  
  
 Das Verhältnis der Auslastung ist das Verhältnis der Anzahl von Klassen, um die Anzahl der Elemente, die in der Map-Objekt gespeichert. Wenn die Struktur der Zuordnung neu berechnet wird, die *fOptimalLoad* Parameterwert berechnet die Anzahl der erforderlichen Klassen verwendet werden. Dieser Wert kann geändert werden, mit der [CAtlMap::SetOptimalLoad](#setoptimalload) Methode.  
  
 Die `fLoThreshold` Parameter ist der kleinere Wert, der das Verhältnis der Auslastungstest vor Erreichen `CAtlMap` berechnet die optimale Größe der Zuordnung neu.  
  
 Die `fHiThreshold` Parameter ist der obere Wert, der das Verhältnis der Auslastungstest vor dem Erreichen der `CAtlMap` Objekt wird die optimale Größe der Zuordnung neu zu berechnen.  
  
 Dieser Prozess zur erneuten Berechnung (bekannt als erneutes Hashing durchführen) ist standardmäßig aktiviert. Wenn Sie dabei ggf. deaktivieren, bei der Eingabe von großen Datenmengen auf einmal aufrufen möchten die [CAtlMap::DisableAutoRehash](#disableautorehash) Methode. Erneut aktivieren, mit der [CAtlMap::EnableAutoRehash](#enableautorehash) Methode.  
  
 Der `nBlockSize` -Parameter ist ein Maß für die Menge des Arbeitsspeichers, wenn ein neues Element erforderlich ist. Größere Blöcke reduziert Aufrufe an Arbeitsspeicher, aber mehr Ressourcen verwenden.  
  
 Bevor Daten gespeichert werden können, ist es notwendig, initialisieren die Hashtabelle mit einem Aufruf von [CAtlMap::InitHashTable](#inithashtable).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#72;](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlMap:: ~ CAtlMap  
 Der Destruktor.  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei.  
  
##  <a name="cpair_class"></a>CAtlMap::CPair-Klasse  
 Eine Klasse, die die Schlüssel-Wert-Elemente enthält.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse wird von den Methoden verwendet [CAtlMap::GetNext](#getnext) und [CAtlMap::Lookup](#lookup) Zugriff auf die Schlüssel-Wert-Elemente, die in der Mapping-Struktur gespeichert.  
  
##  <a name="disableautorehash"></a>CAtlMap::DisableAutoRehash  
 Rufen Sie diese Methode zum Deaktivieren der automatischen Auflösen von der `CAtlMap` Objekt.  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn automatisches erneutes Hashing durchführen aktiviert ist (Standardeinstellung), wird die Anzahl der Klassen in der Hashtabelle automatisch neu berechnet, wenn der Auslastungstest-Wert (das Verhältnis der Anzahl von Klassen, um die Anzahl der Elemente im Array gespeicherten) überschreitet die maximale oder minimale Werte, die zum Zeitpunkt der Erstellung die Zuordnung angegeben.  
  
 `DisableAutoRehash`ist besonders hilfreich, wenn eine große Anzahl von Elementen der Zuordnung auf einmal hinzugefügt werden. Anstelle den rehashing Prozess auslösen, jedes Mal, wenn die Grenzwerte überschritten werden, ist es effizienter Aufrufen `DisableAutoRehash`, Elemente hinzufügen und abschließend rufen [CAtlMap::EnableAutoRehash](#enableautorehash).  
  
##  <a name="enableautorehash"></a>CAtlMap::EnableAutoRehash  
 Rufen Sie diese Methode zum Aktivieren der automatischen Auflösen von der `CAtlMap` Objekt.  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn automatisches erneutes Hashing durchführen aktiviert ist (Standardeinstellung), wird die Anzahl der Klassen in der Hashtabelle automatisch neu berechnet, wenn der Auslastungstest-Wert (das Verhältnis der Anzahl von Klassen, um die Anzahl der Elemente im Array gespeicherten) überschreitet die maximale oder minimale Werte, die zum Zeitpunkt die Zuordnung erstellt wird.  
  
 **EnableAutoRefresh** wird am häufigsten verwendet, nach einem Aufruf von [CAtlMap::DisableAutoRehash](#disableautorehash).  
  
##  <a name="getat"></a>CAtlMap::GetAt  
 Rufen Sie diese Methode, um das Element an der angegebenen Position in der Zuordnung zurück.  
  
```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
 `key`  
 Der Vorlagenparameter, der den Schlüssel der Zuordnung angibt.  
  
 *value*  
 Der Vorlagenparameter, der den Wert der Zuordnung angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das aktuelle Paar von Schlüssel-Wert-Elementen, die in der Zuordnung gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
##  <a name="getcount"></a>CAtlMap::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Zuordnung ab.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente in der Map-Objekt zurück. Ein einzelnes Element ist ein Schlüssel-Wert-Paar.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="gethashtablesize"></a>CAtlMap::GetHashTableSize  
 Rufen Sie diese Methode, um die Anzahl der Klassen in der Hashtabelle der Zuordnung zu bestimmen.  
  
```
UINT GetHashTableSize() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Klassen in der Hashtabelle zurück. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erklärung.  
  
##  <a name="getkeyat"></a>CAtlMap::GetKeyAt  
 Rufen Sie diese Methode zum Abrufen des Schlüssels an der angegebenen Position in der `CAtlMap` Objekt.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den Schlüssel gespeichert, die an der angegebenen Position in der `CAtlMap` Objekt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getnext"></a>CAtlMap::GetNext  
 Rufen Sie diese Methode, um einen Zeiger auf das nächste Element erhalten Paar, in gespeichert dem `CAtlMap` Objekt.  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das nächste Paar von Schlüssel-Wert-Elementen, die in der Zuordnung gespeichert. Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Zuordnung zu `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextassoc"></a>CAtlMap::GetNextAssoc  
 Ruft das nächste Element durchlaufen werden können.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
 `key`  
 Der Vorlagenparameter, der den Schlüssel der Zuordnung angibt.  
  
 *value*  
 Der Vorlagenparameter, der den Wert der Zuordnung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Zuordnung zu `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextkey"></a>CAtlMap::GetNextKey  
 Rufen Sie diese Methode zum Abrufen des nächsten aus der `CAtlMap` Objekt.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Schlüssel in der Zuordnung zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Leistungsindikator `pos`. Wenn in der Zuordnung keine weiteren Einträge vorhanden sind, wird der Position Zähler auf NULL festgelegt.  
  
##  <a name="getnextvalue"></a>CAtlMap::GetNextValue  
 Rufen Sie diese Methode zum Abrufen des nächsten Wert aus der `CAtlMap` Objekt.  
  
```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Wert in der Zuordnung zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Leistungsindikator `pos`. Wenn in der Zuordnung keine weiteren Einträge vorhanden sind, wird der Position Zähler auf NULL festgelegt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getstartposition"></a>CAtlMap::GetStartPosition  
 Rufen Sie diese Methode, um eine Zuordnung Iteration starten.  
  
```
POSITION GetStartPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Startposition oder NULL zurückgegeben wird, wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine Zuordnung Iterationsbeginn durch Rückgabe einer **POSITION** -Wert, der an übergeben werden kann die `GetNextAssoc` Methode.  
  
> [!NOTE]
>  Die Reihenfolge der Iteration ist nicht vorhersagbar  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getvalueat"></a>CAtlMap::GetValueAt  
 Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CAtlMap` Objekt.  
  
```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den Wert gespeichert, die an der angegebenen Position in der `CAtlMap` Objekt.  
  
##  <a name="inithashtable"></a>CAtlMap::InitHashTable  
 Rufen Sie diese Methode, um die Hashtabelle zu initialisieren.  
  
```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```  
  
### <a name="parameters"></a>Parameter  
 `nBins`  
 Die Anzahl der Klassen, die von der Hashtabelle verwendet. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erklärung.  
  
 `bAllocNow`  
 Ein Flag Angabe, wenn Arbeitsspeicher zugewiesen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** bei der erfolgreichen Initialisierung **false** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 `InitHashTable`muss aufgerufen werden, bevor alle Elemente in der Hashtabelle gespeichert werden.  Wenn diese Methode nicht explizit aufgerufen wird, wird Sie aufgerufen automatisch beim ersten Hinzufügen eines Elements wird mithilfe der angegebenen Bin-Anzahl der **CAtlMap** Konstruktor.  Andernfalls die Zuordnung wird initialisiert mithilfe der neuen Bin Anzahl angegeben werden, indem die `nBins` Parameter.  
  
 Wenn die `bAllocNow` -Parameter false ist, der von der Hashtabelle benötigte Speicherplatz wird nicht zugewiesen werden, bis es zunächst erforderlich ist. Dies kann hilfreich, wenn sie nicht wissen, ob es sich bei die Zuordnung verwendet wird.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="isempty"></a>CAtlMap::IsEmpty  
 Rufen Sie diese Methode für ein Objekt leere Zuordnung testen.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist die Zuordnung leer ist, **false** andernfalls.  
  
##  <a name="kinargtype"></a>CAtlMap::KINARGTYPE  
 Typ verwendet, wenn ein Schlüssel als Eingabeargument übergeben wird.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CAtlMap::KOUTARGTYPE  
 -Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="lookup"></a>CAtlMap::Lookup  
 Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CAtlMap` Objekt.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 *value*  
 Variable, der gebundene Wert erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Form der Methode zurückgibt true, wenn der Schlüssel, andernfalls false gefunden wird. Die zweite und dritte Formulare zurückgeben, einen Zeiger auf eine [CPair](#cpair_class) das als eine Position für Aufrufe verwendet werden können [CAtlMap::GetNext](#getnext) und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 `Lookup`verwendet einen Hashalgorithmus finden schnell und einfach das Map-Element mit einem Schlüssel, der mit den angegebenen Schlüssel Parameter übereinstimmt.  
  
##  <a name="operator_at"></a>CAtlMap::operator\[\]  
 Ersetzt oder fügt ein neues Element auf der `CAtlMap`.  
  
```
V& operator[](kinargtype key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel des Elements, das Hinzufügen oder ersetzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den angegebenen Schlüssel zugeordnete Wert.  
  
### <a name="example"></a>Beispiel  
 Wenn der Schlüssel bereits vorhanden ist, wird das Element ersetzt. Wenn der Schlüssel nicht vorhanden ist, wird ein neues Element hinzugefügt. Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="rehash"></a>CAtlMap::Rehash  
 Rufen Sie diese Methode zum rehash der `CAtlMap` Objekt.  
  
```
void Rehash(UINT nBins = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nBins`  
 Die Anzahl der Klassen in der Hashtabelle verwenden. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erklärung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nBins` ist 0, `CAtlMap` berechnet eine angemessene Anzahl basierend auf der Anzahl der Elemente in der Zuordnung und die optimale Auslastung-Einstellung. Normalerweise die rehashing erfolgt automatisch, wenn Sie allerdings [CAtlMap::DisableAutoRehash](#disableautorehash) wurde aufgerufen wird, diese Methode führt die erforderlichen Größe ändern.  
  
##  <a name="removeall"></a>CAtlMap::RemoveAll  
 Rufen Sie diese Methode zum Entfernen aller Elemente aus der `CAtlMap` Objekt.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht das `CAtlMap` -Objekt, der belegte Arbeitsspeicher zum Speichern der Elemente.  
  
##  <a name="removeatpos"></a>CAtlMap::RemoveAtPos  
 Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CAtlMap` Objekt.  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="remarks"></a>Hinweise  
 Entfernt den Schlüssel/Wert-Paar an der angegebenen Position gespeichert. Der zum Speichern des Elements verwendete Arbeitsspeicher wird freigegeben. Die POSITION verweist `pos` ungültig, und während die POSITION der anderen Elemente in der Zuordnung gültig bleibt, sie müssen nicht unbedingt beibehalten die Reihenfolge.  
  
##  <a name="removekey"></a>CAtlMap::RemoveKey  
 Rufen Sie diese Methode zum Entfernen eines Elements aus der `CAtlMap` -Objekt, den Schlüssel.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Die entsprechenden Elementpaar, die Sie entfernen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn der Schlüssel gefunden und entfernt, **false** bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="setat"></a>CAtlMap::SetAt  
 Rufen Sie diese Methode, um ein Element in der Zuordnung einzufügen.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselwert, der zum Hinzufügen der `CAtlMap` Objekt.  
  
 *value*  
 Der hinzuzufügende Wert der `CAtlMap` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Schlüssel/Wert-Element-Paar in der `CAtlMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt`ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird. Wenn der Schlüssel nicht gefunden wird, wird ein neues Schlüssel/Wert-Paar erstellt.  
  
##  <a name="setoptimalload"></a>CAtlMap::SetOptimalLoad  
 Rufen Sie diese Methode, um die optimale Auslastung der Festlegen der `CAtlMap` Objekt.  
  
```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```  
  
### <a name="parameters"></a>Parameter  
 `fOptimalLoad`  
 Die optimale Auslastung-Verhältnis.  
  
 `fLoThreshold`  
 Der untere Schwellenwert für das Load-Verhältnis.  
  
 `fHiThreshold`  
 Der obere Schwellenwert für das Load-Verhältnis.  
  
 `bRehashNow`  
 Zeigt an, wenn die Hashtabelle neu berechnet werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert den Wert der optimale Auslastung der `CAtlMap` Objekt. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erläuterung der verschiedenen Parameter. Wenn `bRehashNow` true ist, und die Anzahl der Elemente außerhalb der minimalen und maximalen Werte, die Hashtabelle neu berechnet wird.  
  
##  <a name="setvalueat"></a>CAtlMap::SetValueAt  
 Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CAtlMap` Objekt.  
  
```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
 *value*  
 Der hinzuzufügende Wert der `CAtlMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ändert das Value-Element gespeichert, die an der angegebenen Position in der `CAtlMap` Objekt.  
  
##  <a name="vinargtype"></a>CAtlMap::VINARGTYPE  
 -Typ, wenn der Wert als Eingabeargument übergeben wird.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CAtlMap::VOUTARGTYPE  
 -Typ, wenn der Wert als ausgabeargument übergeben wird.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="m_key"></a>CAtlMap::CPair::m_key  
 Das Datenelement, das wichtigste Element speichern.  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Key-Element.  
  
##  <a name="m_value"></a>CAtlMap::CPair::m_value  
 Der Datenmember, speichern das Value-Element.  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>Parameter  
 *V*  
 Der Wert-Elementtyp.  
  
## <a name="see-also"></a>Siehe auch  
 [Marquee-Beispiel](../../visual-cpp-samples.md)   
 [UpdatePV-Beispiel](../../visual-cpp-samples.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

