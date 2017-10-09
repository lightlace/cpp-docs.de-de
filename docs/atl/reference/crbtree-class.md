---
title: CRBTree Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 078224c555f2f1955083b51954d56b3e9cac8fd1
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="crbtree-class"></a>CRBTree-Klasse
Diese Klasse stellt Methoden zum Erstellen und eine Rot-Schwarz-Struktur nutzen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBTree
```  
  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Key-Element.  
  
 *V*  
 Der Werttyp-Element.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.  
  
 `VTraits`  
 Der Code zum Kopieren oder verschieben Wertelemente verwendet.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](#kinargtype)|Der Typ verwendet, wenn ein Schlüssel, als Eingabeargument übergeben wird.|  
|[CRBTree::KOUTARGTYPE](#koutargtype)|Der Typ verwendet, wenn eine Taste als ausgabeargument zurückgegeben wird.|  
|[CRBTree::VINARGTYPE](#vinargtype)|Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.|  
|[CRBTree::VOUTARGTYPE](#voutargtype)|Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.|  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBTree::CPair-Klasse](#cpair_class)|Eine Klasse, die die Schlüssel und Wert Elemente enthält.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBTree:: ~ CRBTree](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Rufen Sie diese Methode, um die Position des Elements zu suchen, die den nächsten Schlüssel verwendet.|  
|[CRBTree::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer bestimmten Position in der Struktur abrufen.|  
|[CRBTree::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente in der Struktur abrufen.|  
|[CRBTree::GetHeadPosition](#getheadposition)|Rufen Sie diese Methode, um den Positionswert für das Element am Anfang der Struktur erhalten.|  
|[CRBTree::GetKeyAt](#getkeyat)|Rufen Sie diese Methode, um den Schlüssel aus einer bestimmten Position in der Struktur zu erhalten.|  
|[CRBTree::GetNext](#getnext)|Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` Objekt, und die Position auf das nächste Element zu wechseln.|  
|[CRBTree::GetNextAssoc](#getnextassoc)|Rufen Sie diese Methode, um die Schlüssel und Wert eines Elements in der Zuordnung gespeicherten abzurufen, und wechseln Sie die Position auf das nächste Element zu.|  
|[CRBTree::GetNextKey](#getnextkey)|Rufen Sie diese Methode zum Abrufen der Schlüssel eines Elements in der Struktur gespeichert, und wechseln Sie die Position auf das nächste Element zu.|  
|[CRBTree::GetNextValue](#getnextvalue)|Rufen Sie diese Methode zum Abrufen des Werts eines Elements in der Struktur gespeichert, und wechseln Sie die Position auf das nächste Element zu.|  
|[CRBTree::GetPrev](#getprev)|Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` -Objekt, und aktualisieren Sie die Position zum vorherigen Element.|  
|[CRBTree::GetTailPosition](#gettailposition)|Rufen Sie diese Methode, um den Positionswert für das Element am Ende der Struktur erhalten.|  
|[CRBTree::GetValueAt](#getvalueat)|Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.|  
|[CRBTree::IsEmpty](#isempty)|Rufen Sie diese Methode für ein Strukturobjekt leere zu testen.|  
|[CRBTree::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die **CRBTree** Objekt.|  
|[CRBTree::RemoveAt](#removeat)|Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der **CRBTree** Objekt.|  
|[CRBTree::SetValueAt](#setvalueat)|Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Rot-Schwarz-Struktur ist eine binäre Suche-Struktur, die eine zusätzliche verwendet Paar Informationen pro Knoten an, stellen Sie sicher, dass er bleibt "ausgeglichen,", der, der die Höhe der Struktur nicht unverhältnismäßig groß und die Leistung beeinträchtigen.  
  
 Diese Vorlagenklasse dient zum unbefriedigend erwiesen [CRBMap](../../atl/reference/crbmap-class.md) und [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Der Großteil der Methoden, die diese abgeleiteten Klassen bilden gebotenen `CRBTree`.  
  
 Eine vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="cpair_class"></a>CRBTree::CPair-Klasse  
 Eine Klasse, die die Schlüssel und Wert Elemente enthält.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem Sie die Methoden [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), und [CRBTree::GetPrev](#getprev) Zugriff auf die Schlüssel und Wert Elemente, die in der Struktur gespeichert.  
  
 Die Elemente werden wie folgt:  
  
|||  
|-|-|  
|`m_key`|Das Datenelement, das Schlüsselelement speichern.|  
|`m_value`|Das Datenelement, speichern die Value-Element.|  
  
##  <a name="dtor"></a>CRBTree:: ~ CRBTree  
 Der Destruktor.  
  
```
~CRBTree() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei. Aufrufe [CRBTree::RemoveAll](#removeall) alle Elemente löschen.  
  
##  <a name="findfirstkeyafter"></a>CRBTree::FindFirstKeyAfter  
 Rufen Sie diese Methode, um die Position des Elements zu suchen, die den nächsten Schlüssel verwendet.  
  
```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Ein Schlüssel-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Positionswert des Elements, das den nächsten verfügbaren Schlüssel verwendet. Wenn keine Elemente mehr vorhanden sind, wird NULL zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erleichtert das Durchlaufen der Struktur ohne Positionswerte im Vorfeld berechnen.  
  
##  <a name="getat"></a>CRBTree::GetAt  
 Rufen Sie diese Methode, um das Element an einer bestimmten Position in der Struktur abrufen.  
  
```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Positionswert.  
  
 `key`  
 Die Variable, die den Schlüssel erhält.  
  
 *value*  
 Die Variable, die den Wert empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten beiden Formen zurückgeben, einen Zeiger auf eine [CPair](#cpair_class). Die dritte Form erhält einen Schlüssel und einen Wert für die angegebene Position.  
  
### <a name="remarks"></a>Hinweise  
 Der Positionswert kann bestimmt werden, zuvor durch einen Aufruf einer Methode wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::GetTailPosition](#gettailposition).  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
##  <a name="getcount"></a>CRBTree::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Struktur abrufen.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente, die in der Struktur gespeichert (jedes Schlüssel/Wert-Paar ist ein Element) zurück.  
  
##  <a name="getheadposition"></a>CRBTree::GetHeadPosition  
 Rufen Sie diese Methode, um den Positionswert für das Element am Anfang der Struktur erhalten.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die Position für das Element am Anfang der Struktur zurück.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert von `GetHeadPosition` können Methoden verwendet werden, z. B. [CRBTree::GetKeyAt](#getkeyat) oder [CRBTree::GetNext](#getnext) zum Traversieren der Struktur und zum Abrufen von Werten.  
  
##  <a name="getkeyat"></a>CRBTree::GetKeyAt  
 Rufen Sie diese Methode, um den Schlüssel aus einer bestimmten Position in der Struktur zu erhalten.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Positionswert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Schlüssel an Position gespeicherte `pos` in der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pos` ist kein Wert für die gültige Position Ergebnisse sind unvorhersehbar. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
##  <a name="getnext"></a>CRBTree::GetNext  
 Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` Objekt, und die Position auf das nächste Element zu wechseln.  
  
```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den nächsten [CPair](#cpair_class) Wert in der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Struktur `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextassoc"></a>CRBTree::GetNextAssoc  
 Rufen Sie diese Methode, um die Schlüssel und Wert eines Elements in der Zuordnung gespeicherten abzurufen, und wechseln Sie die Position auf das nächste Element zu.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 `key`  
 Template-Parameter, die den Typ des Schlüssels der Struktur angibt.  
  
 *value*  
 Vorlagenparameter, der den Typ des Werts der Struktur angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Struktur `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextkey"></a>CRBTree::GetNextKey  
 Rufen Sie diese Methode zum Abrufen der Schlüssel eines Elements in der Struktur gespeichert, und wechseln Sie die Position auf das nächste Element zu.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Schlüssel in der Struktur zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Indikator `pos`. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Zähler der Position auf NULL festgelegt.  
  
##  <a name="getnextvalue"></a>CRBTree::GetNextValue  
 Rufen Sie diese Methode zum Abrufen des Werts eines Elements in der Struktur gespeichert, und wechseln Sie die Position auf das nächste Element zu.  
  
```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Wert in der Struktur zurück.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Indikator `pos`. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Zähler der Position auf NULL festgelegt.  
  
##  <a name="getprev"></a>CRBTree::GetPrev  
 Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` -Objekt, und aktualisieren Sie die Position zum vorherigen Element.  
  
```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den vorherigen [CPair](#cpair_class) Wert in der Struktur gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Indikator `pos`. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Zähler der Position auf NULL festgelegt.  
  
##  <a name="gettailposition"></a>CRBTree::GetTailPosition  
 Rufen Sie diese Methode, um den Positionswert für das Element am Ende der Struktur erhalten.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die Position für das Element am Ende der Struktur zurück.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert von `GetTailPosition` können Methoden verwendet werden, z. B. [CRBTree::GetKeyAt](#getkeyat) oder [CRBTree::GetPrev](#getprev) zum Traversieren der Struktur und zum Abrufen von Werten.  
  
##  <a name="getvalueat"></a>CRBTree::GetValueAt  
 Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.  
  
```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den Wert gespeichert, an der angegebenen Position in der `CRBTree` Objekt.  
  
##  <a name="isempty"></a>CRBTree::IsEmpty  
 Rufen Sie diese Methode für ein Strukturobjekt leere zu testen.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist die Struktur leer, wird **"false"** andernfalls.  
  
##  <a name="kinargtype"></a>CRBTree::KINARGTYPE  
 Der Typ verwendet, wenn ein Schlüssel, als Eingabeargument übergeben wird.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CRBTree::KOUTARGTYPE  
 Der Typ verwendet, wenn eine Taste als ausgabeargument zurückgegeben wird.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="removeall"></a>CRBTree::RemoveAll  
 Rufen Sie diese Methode, um alle Elemente entfernt werden sollen die `CRBTree` Objekt.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht die `CRBTree` Objekt, die Freigabe des Speichers zum Speichern der Elemente verwendet.  
  
##  <a name="removeat"></a>CRBTree::RemoveAt  
 Rufen Sie diese Methode, um das Element an der angegebenen Position im Entfernen der **CRBTree** Objekt.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="remarks"></a>Hinweise  
 Entfernt das Schlüssel/Wert-Paar, das an der angegebenen Position gespeichert. Der zum Speichern des Elements verwendete Arbeitsspeicher wird freigegeben. Die POSITION verweist `pos` verliert seine Gültigkeit und während die POSITION beliebiger anderer Elemente in der Struktur gültig bleibt, sie müssen nicht unbedingt beibehalten die gleiche Reihenfolge.  
  
##  <a name="setvalueat"></a>CRBTree::SetValueAt  
 Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.  
  
```
void SetValueAt(POSITION pos, VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Position-Leistungsindikator, wie z. B. von einem vorherigen Aufruf von Methoden zurückgegebene [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 *value*  
 Der Wert, der zum Hinzufügen der `CRBTree` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ändert das Value-Element gespeichert wird, an der angegebenen Position in der `CRBTree` Objekt.  
  
##  <a name="vinargtype"></a>CRBTree::VINARGTYPE  
 Der Typ verwendet, wenn ein Wert als Eingabeargument übergeben wird.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CRBTree::VOUTARGTYPE  
 Der Typ verwendet, wenn ein Wert als ausgabeargument übergeben wird.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

