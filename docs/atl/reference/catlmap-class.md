---
title: CAtlMap Klasse | Microsoft Docs
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9166e8f7804a3138d3e891fbe15b54cb0e270811
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catlmap-class"></a>CAtlMap-Klasse
Diese Klasse stellt Methoden zum Erstellen und verwalten einen Map-Objekt.  
  
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
 Der Werttyp-Element.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.  
  
 `VTraits`  
 Der Code zum Kopieren oder verschieben Wertelemente verwendet.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|Typ verwendet, wenn ein Schlüssel, als Eingabeargument übergeben wird|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Der Typ verwendet, wenn eine Taste als ausgabeargument zurückgegeben wird.|  
|[CAtlMap::VINARGTYPE](#vinargtype)|Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.|  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::CPair-Klasse](#cpair_class)|Eine Klasse, die die Schlüssel und Wert Elemente enthält.|  

  
### <a name="cpair-data-members"></a>CPair-Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|Das Datenelement, das Schlüsselelement speichern.|  
|[CPair::m_value](#m_value)|Das Datenelement, speichern die Value-Element.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|Der Konstruktor.|  
|[CAtlMap:: ~ CAtlMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|Rufen Sie diese Methode, um eine ASSERTION verursachen, wenn die `CAtlMap` ist ungültig.|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Rufen Sie diese Methode zum Deaktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Rufen Sie diese Methode zum Aktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.|  
|[CAtlMap::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Zuordnung zurück.|  
|[CAtlMap::GetCount](#getcount)|Rufen Sie diese Methode zum Abrufen der Anzahl von Elementen in der Zuordnung.|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Rufen Sie diese Methode, um die Anzahl der Klassen in der Hashtabelle der Zuordnung zu bestimmen.|  
|[CAtlMap::GetKeyAt](#getkeyat)|Rufen Sie diese Methode zum Abrufen des Schlüssels gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.|  
|[CAtlMap::GetNext](#getnext)|Rufen Sie diese Methode, um einen Zeiger auf das nächste Element erhalten Paar, in gespeichert der `CAtlMap` Objekt.|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element für die Iteration an.|  
|[CAtlMap::GetNextKey](#getnextkey)|Rufen Sie diese Methode zum Abrufen der nächsten Schlüssels aus der `CAtlMap` Objekt.|  
|[CAtlMap::GetNextValue](#getnextvalue)|Rufen Sie diese Methode zum Abrufen des nächsten Wert aus der `CAtlMap` Objekt.|  
|[CAtlMap::GetStartPosition](#getstartposition)|Rufen Sie diese Methode, um eine Zuordnung Iteration starten.|  
|[CAtlMap::GetValueAt](#getvalueat)|Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CAtlMap` Objekt.|  
|[CAtlMap::InitHashTable](#inithashtable)|Rufen Sie diese Methode, um die Hashtabelle zu initialisieren.|  
|[CAtlMap::IsEmpty](#isempty)|Rufen Sie diese Methode für ein Objekt leere Zuordnung testen.|  
|[CAtlMap::Lookup](#lookup)|Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CAtlMap` Objekt.|  
|[CAtlMap::Rehash](#rehash)|Rufen Sie diese Methode zum rehash der `CAtlMap` Objekt.|  
|[CAtlMap::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CAtlMap` Objekt.|  
|[CAtlMap::RemoveAtPos](#removeatpos)|Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CAtlMap` Objekt.|  
|[CAtlMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen eines Elements aus der `CAtlMap` Objekt anhand des angegebenen Schlüssels.|  
|[CAtlMap::SetAt](#setat)|Rufen Sie diese Methode zum Einfügen von einer Element-Paar in der Zuordnung.|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Rufen Sie diese Methode, um die optimale Auslastung der Festlegen der `CAtlMap` Objekt.|  
|[CAtlMap::SetValueAt](#setvalueat)|Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CAtlMap` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Ersetzt oder fügt ein neues Element auf der `CAtlMap`.|  

  
## <a name="remarks"></a>Hinweise  
 `CAtlMap`bietet Unterstützung für ein Mapping-Array eines angegebenen Typs, verwalten eine nicht geordnete Array von Schlüsselelemente und die zugehörigen Werte. Elemente (bestehend aus einem Schlüssel und Wert) werden mithilfe eines Hashalgorithmus, sodass eine große Menge von Daten effizient gespeichert und abgerufen werden gespeichert.  
  
 Die `KTraits` und `VTraits` Parameter sind Traits-Klassen, die keinen zusätzlichen Code erforderlich, um die Elemente kopiert oder verschoben enthalten.  
  
 Eine Alternative zum `CAtlMap` angeboten wird, durch die [CRBMap](../../atl/reference/crbmap-class.md) Klasse. `CRBMap`Außerdem speichert die Schlüssel-/Wertpaaren, aber unterschiedlichen Leistungsmerkmale aufweist. Die Zeit zum Einfügen eines Elements nach einem Schlüssel zu suchen, oder löschen ein Schlüssels aus einem `CRBMap` Objekt weist Reihenfolge *log(n)*, wobei  *n*  ist die Anzahl der Elemente. Für `CAtlMap`, alle diese Vorgänge dauern in der Regel einen Konstanten Zeit, obwohl Worst-Case-Szenarien Bestellung können  *n* . Aus diesem Grund in einen typischen Fall `CAtlMap` ist schneller.  
  
 Ein weiterer Unterschied zwischen `CRBMap` und `CAtlMap` wird offensichtlich, wenn die gespeicherte Elemente durchlaufen. In einem `CRBMap`, die Elemente in einer sortierten Reihenfolge besucht werden. In einem `CAtlMap`, die Elemente werden nicht sortiert und die Reihenfolge nicht abgeleitet werden kann.  
  
 Wenn eine kleine Anzahl von Elementen gespeichert werden muss, können Sie verwenden die [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="assertvalid"></a>CAtlMap::AssertValid  
 Rufen Sie diese Methode, um eine ASSERTION verursachen, wenn die `CAtlMap` -Objekt ist ungültig.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Hinweise  
 In der Debug-Builds: Diese Methode eine ASSERTION verursachen, wenn die `CAtlMap` -Objekt ist ungültig.  
  
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
 Die Anzahl der Klassen, die Zeiger auf die gespeicherten Elemente bereitstellen. Siehe "Hinweise" weiter unten in diesem Thema eine Erläuterung der Klassen an.  
  
 `fOptimalLoad`  
 Die optimale Auslastung-Verhältnis.  
  
 `fLoThreshold`  
 Der untere Schwellenwert für die Load-Verhältnis.  
  
 `fHiThreshold`  
 Der obere Schwellenwert für die Load-Verhältnis.  
  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 `CAtlMap`verweist auf all ihre gespeicherten Elemente, indem zunächst erstellt einen Index mit dem eines Hashalgorithmus auf den Schlüssel. Dieser Index verweist auf eine "Bin" enthält einen Zeiger auf die gespeicherten Elemente. Wenn die "bin" bereits verwendet wird, ist eine verknüpfte Liste erstellt, um die nachfolgenden Elemente zuzugreifen. Eine Liste durchlaufen ist langsamer als die direkten Zugriff auf das richtige Element, und daher muss die Struktur der Zuordnung speicheranforderungen gegenüber der Leistung abwägen. Die Standardparameter wurden ausgewählt, um gute Ergebnisse in den meisten Fällen zu gewähren.  
  
 Das Verhältnis der Auslastungstest ist das Verhältnis der Anzahl von Klassen, die Anzahl der Elemente in der Map-Objekt gespeichert. Wenn die Struktur der Zuordnung neu berechnet wird, die *fOptimalLoad* Parameterwert wird verwendet, um die Berechnung der Anzahl der Klassen, die erforderlich sind. Dieser Wert kann geändert werden, mithilfe der [CAtlMap::SetOptimalLoad](#setoptimalload) Methode.  
  
 Die `fLoThreshold` Parameter ist der niedrigere Wert, der das Load-Verhältnis, bevor erreichen kann `CAtlMap` berechnet die optimale Größe der Zuordnung neu.  
  
 Die `fHiThreshold` Parameter ist der obere Wert, der das Load-Verhältnis, bevor erreichen kann die `CAtlMap` Objekt berechnet die optimale Größe der Zuordnung neu.  
  
 Dabei neuberechnung (erneutes Hashing durchführen genannt) ist standardmäßig aktiviert. Wenn Sie vielleicht dieses Vorgangs zu deaktivieren, bei der Eingabe von großen Datenmengen auf einmal Aufruf möchten der [CAtlMap::DisableAutoRehash](#disableautorehash) Methode. Erneut aktivieren, mit der [CAtlMap::EnableAutoRehash](#enableautorehash) Methode.  
  
 Die `nBlockSize` Parameter ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.  
  
 Bevor Daten gespeichert werden können, ist es zum Initialisieren der Hashtabelle mit einem Aufruf von [CAtlMap::InitHashTable](#inithashtable).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlMap:: ~ CAtlMap  
 Der Destruktor.  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei.  
  
##  <a name="cpair_class"></a>CAtlMap::CPair-Klasse  
 Eine Klasse, die die Schlüssel und Wert Elemente enthält.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem Sie die Methoden [CAtlMap::GetNext](#getnext) und [CAtlMap::Lookup](#lookup) Zugriff auf die Schlüssel und Wert Elemente, die in der Zuordnungsstruktur gespeichert.  
  
##  <a name="disableautorehash"></a>CAtlMap::DisableAutoRehash  
 Rufen Sie diese Methode zum Deaktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn automatisches erneutes Hashing durchführen aktiviert ist (er befindet sich in der Standardeinstellung), wird die Anzahl der Klassen in der Hashtabelle automatisch neu berechnet werden der Load-Wert (das Verhältnis der Anzahl von Klassen, die Anzahl der Elemente im Array gespeicherten) überschreitet die maximale oder minimale Werte zum Zeitpunkt der Erstellung die Zuordnung angegeben.  
  
 `DisableAutoRehash`ist besonders hilfreich, wenn eine große Anzahl von Elementen der Zuordnung auf einmal hinzugefügt werden. Anstelle den rehashing Prozess auslösenden, jedes Mal, wenn die Grenzwerte überschritten werden, es ist jedoch effizienter Aufrufen `DisableAutoRehash`, fügen Sie die Elemente hinzu und rufen Sie schließlich [CAtlMap::EnableAutoRehash](#enableautorehash).  
  
##  <a name="enableautorehash"></a>CAtlMap::EnableAutoRehash  
 Rufen Sie diese Methode zum Aktivieren der automatischen erneutes Hashing Durchführen von der `CAtlMap` Objekt.  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn automatisches erneutes Hashing durchführen aktiviert ist (er befindet sich in der Standardeinstellung), wird die Anzahl der Klassen in der Hashtabelle automatisch neu berechnet werden der Load-Wert (das Verhältnis der Anzahl von Klassen, die Anzahl der Elemente im Array gespeicherten) überschreitet die maximale oder minimale Werte angegeben, die zum Zeitpunkt die Zuordnung erstellt wird.  
  
 **EnableAutoRefresh** werden am häufigsten verwendet, nach einem Aufruf von [CAtlMap::DisableAutoRehash](#disableautorehash).  
  
##  <a name="getat"></a>CAtlMap::GetAt  
 Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Zuordnung zurück.  
  
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
 Vorlagenparameter, den Typ des Schlüssels der Zuordnung angibt.  
  
 *Wert*  
 Der Vorlagenparameter, den Typ des Werts der Zuordnung angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das aktuelle Paar von Schlüssel/Wert-Elementen, die in der Zuordnung gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
##  <a name="getcount"></a>CAtlMap::GetCount  
 Rufen Sie diese Methode zum Abrufen der Anzahl von Elementen in der Zuordnung.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente in der Map-Objekt zurück. Ein einzelnes Element ist ein Schlüssel/Wert-Paar.  
  
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
 Rufen Sie diese Methode zum Abrufen des Schlüssels gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den Schlüssel gespeichert werden, an der angegebenen Position in der `CAtlMap` Objekt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getnext"></a>CAtlMap::GetNext  
 Rufen Sie diese Methode, um einen Zeiger auf das nächste Element erhalten Paar, in gespeichert der `CAtlMap` Objekt.  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das nächste Paar von Schlüssel/Wert-Elementen, die in der Zuordnung gespeichert. Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Zuordnung ist `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextassoc"></a>CAtlMap::GetNextAssoc  
 Ruft das nächste Element für die Iteration an.  
  
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
 Vorlagenparameter, den Typ des Schlüssels der Zuordnung angibt.  
  
 *Wert*  
 Der Vorlagenparameter, den Typ des Werts der Zuordnung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Zuordnung ist `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextkey"></a>CAtlMap::GetNextKey  
 Rufen Sie diese Methode zum Abrufen der nächsten Schlüssels aus der `CAtlMap` Objekt.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Schlüssel in der Zuordnung zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Indikator `pos`. Wenn keine weiteren Einträge in der Zuordnung vorhanden sind, wird der Zähler der Position auf NULL festgelegt.  
  
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
 Aktualisiert die aktuelle Position Indikator `pos`. Wenn keine weiteren Einträge in der Zuordnung vorhanden sind, wird der Zähler der Position auf NULL festgelegt.  
  
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
 Rufen Sie diese Methode, um eine Zuordnung Iterationsbeginn wird durch Zurückgeben einer **POSITION** -Wert, der übergeben werden kann die `GetNextAssoc` Methode.  
  
> [!NOTE]
>  Die Sequenz Iteration ist nicht vorhersagbar  
  
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
 Gibt einen Verweis auf den Wert gespeichert, an der angegebenen Position in der `CAtlMap` Objekt.  
  
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
 Ein Flag-Hinweis, wenn Speicher belegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** erfolgreich während der Initialisierung, **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 `InitHashTable`muss aufgerufen werden, bevor alle Elemente in der Hashtabelle gespeichert werden.  Wenn diese Methode nicht explizit aufgerufen wird, aufgerufen wird automatisch beim ersten ein Element hinzugefügt wird, die Anzahl der "bin" angegeben werden, indem Sie mit der **CAtlMap** Konstruktor.  Hingegen die Zuordnung wird so initialisiert, mithilfe der neuen "bin" Anzahl gemäß der `nBins` Parameter.  
  
 Wenn die `bAllocNow` Parameter auf "false" festgelegt ist, der von der Hashtabelle benötigte Arbeitsspeicher nicht zugeordnet werden, bis er zuerst erforderlich ist. Dies kann nützlich sein, wenn es ist unsicher, ob die Zuordnung verwendet werden soll.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="isempty"></a>CAtlMap::IsEmpty  
 Rufen Sie diese Methode für ein Objekt leere Zuordnung testen.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Zuordnung leer ist, ist **"false"** andernfalls.  
  
##  <a name="kinargtype"></a>CAtlMap::KINARGTYPE  
 Der Typ verwendet, wenn ein Schlüssel, als Eingabeargument übergeben wird.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CAtlMap::KOUTARGTYPE  
 Der Typ verwendet, wenn eine Taste als ausgabeargument zurückgegeben wird.  
  
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
  
 *Wert*  
 Variablen, empfängt der gebundene Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Form der Methode gibt "true", wenn der Schlüssel gefunden wird, andernfalls "false" zurück. Die zweite und dritte Formulare zurückgeben, einen Zeiger auf eine [CPair](#cpair_class) die als eine Position für Aufrufe verwendet werden können [CAtlMap::GetNext](#getnext) und so weiter.  
  
### <a name="remarks"></a>Hinweise  
 `Lookup`verwendet einen Hashalgorithmus zu schnell suchen des Map-Elements mit einem Schlüssel, der den angegebenen Schlüsselparameter genau übereinstimmt.  
  
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
 Die neue Anzahl der Klassen in der Hashtabelle verwenden. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erklärung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nBins` ist 0, `CAtlMap` berechnet eine angemessene Anzahl basierend auf der Anzahl von Elementen in der Zuordnung und die optimale Auslastung-Einstellung. Rehashing Prozess ist normalerweise automatisch, jedoch möglich, wenn [CAtlMap::DisableAutoRehash](#disableautorehash) wurde aufgerufen, diese Methode führt die erforderlichen Größe ändern.  
  
##  <a name="removeall"></a>CAtlMap::RemoveAll  
 Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CAtlMap` Objekt.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht die `CAtlMap` Objekt, die Freigabe des Speichers zum Speichern der Elemente verwendet.  
  
##  <a name="removeatpos"></a>CAtlMap::RemoveAtPos  
 Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der `CAtlMap` Objekt.  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Zähler, die von einem vorherigen Aufruf zurückgegebene [CAtlMap::GetNextAssoc](#getnextassoc) oder [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="remarks"></a>Hinweise  
 Entfernt das Schlüssel/Wert-Paar, das an der angegebenen Position gespeichert. Der zum Speichern des Elements verwendete Arbeitsspeicher wird freigegeben. Die POSITION verweist `pos` verliert seine Gültigkeit und während die POSITION beliebiger anderer Elemente in der Zuordnung gültig bleibt, sie müssen nicht unbedingt beibehalten die gleiche Reihenfolge.  
  
##  <a name="removekey"></a>CAtlMap::RemoveKey  
 Rufen Sie diese Methode zum Entfernen eines Elements aus der `CAtlMap` Objekt anhand des angegebenen Schlüssels.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Die Schlüssel entsprechend der Element-Paar, die Sie entfernen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn der Schlüssel gefunden und entfernt, **"false"** bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="setat"></a>CAtlMap::SetAt  
 Rufen Sie diese Methode zum Einfügen von einer Element-Paar in der Zuordnung.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselwert, der zum Hinzufügen der `CAtlMap` Objekt.  
  
 *Wert*  
 Der Wert, der zum Hinzufügen der `CAtlMap` Objekt.  
  
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
 Der untere Schwellenwert für die Load-Verhältnis.  
  
 `fHiThreshold`  
 Der obere Schwellenwert für die Load-Verhältnis.  
  
 `bRehashNow`  
 Ein Flag, der angibt, wenn die Hashtabelle neu berechnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode definiert, die optimale Auslastung-Wert für die `CAtlMap` Objekt. Finden Sie unter [CAtlMap::CAtlMap](#catlmap) eine Erläuterung der verschiedenen Parameter. Wenn `bRehashNow` ist "true", und die Anzahl von Elementen außerhalb der minimalen und maximalen Werte, die Hashtabelle neu berechnet.  
  
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
  
 *Wert*  
 Der Wert, der zum Hinzufügen der `CAtlMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ändert das Value-Element gespeichert wird, an der angegebenen Position in der `CAtlMap` Objekt.  
  
##  <a name="vinargtype"></a>CAtlMap::VINARGTYPE  
 Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CAtlMap::VOUTARGTYPE  
 Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="m_key"></a>CAtlMap::CPair::m_key  
 Das Datenelement, das Schlüsselelement speichern.  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Key-Element.  
  
##  <a name="m_value"></a>CAtlMap::CPair::m_value  
 Das Datenelement, speichern die Value-Element.  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>Parameter  
 *V*  
 Der Werttyp-Element.  
  
## <a name="see-also"></a>Siehe auch  
 [Laufschriften-Beispiel](../../visual-cpp-samples.md)   
 [UpdatePV-Beispiel](../../visual-cpp-samples.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
