---
title: Klasse CRBTree | Microsoft-Dokumentation
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
ms.openlocfilehash: 7dec5cc56d28c4574f923fe2cbb952b628e2689f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="crbtree-class"></a>CRBTree-Klasse
Diese Klasse stellt Methoden zum Erstellen und eine Rot-Schwarz-Baum nutzen.  
  
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
 Der Wert-Elementtyp.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
 `VTraits`  
 Der Code kopieren oder verschieben Elemente mit dem Wert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](#kinargtype)|Typ verwendet, wenn ein Schlüssel als Eingabeargument übergeben wird.|  
|[CRBTree::KOUTARGTYPE](#koutargtype)|-Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.|  
|[CRBTree::VINARGTYPE](#vinargtype)|-Typ, wenn der Wert als Eingabeargument übergeben wird.|  
|[CRBTree::VOUTARGTYPE](#voutargtype)|-Typ, wenn der Wert als ausgabeargument übergeben wird.|  
  
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
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Rufen Sie diese Methode, um die Position des Elements zu suchen, die den nächsten verfügbaren Schlüssel verwendet.|  
|[CRBTree::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer bestimmten Position in der Struktur abgerufen.|  
|[CRBTree::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente in der Struktur zu erhalten.|  
|[CRBTree::GetHeadPosition](#getheadposition)|Rufen Sie diese Methode, um den Wert für das Element am Anfang der Struktur abrufen.|  
|[CRBTree::GetKeyAt](#getkeyat)|Rufen Sie diese Methode, um den Schlüssel aus einer angegebenen Position in der Struktur zu erhalten.|  
|[CRBTree::GetNext](#getnext)|Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` -Objekt, und die Position auf das nächste Element.|  
|[CRBTree::GetNextAssoc](#getnextassoc)|Rufen Sie diese Methode, um den Schlüssel und den Wert eines Elements in der Zuordnung gespeicherten abrufen und die Position auf das nächste Element.|  
|[CRBTree::GetNextKey](#getnextkey)|Rufen Sie diese Methode, um den Schlüssel für ein Element in der Struktur zu erhalten und die Position auf das nächste Element.|  
|[CRBTree::GetNextValue](#getnextvalue)|Rufen Sie diese Methode, um ein Element in der Struktur zu nutzen und die Position auf das nächste Element.|  
|[CRBTree::GetPrev](#getprev)|Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` -Objekt, und aktualisieren Sie die Position zum vorherigen Element.|  
|[CRBTree::GetTailPosition](#gettailposition)|Rufen Sie diese Methode, um den Wert für die Position für das Element am Ende der Struktur zu erhalten.|  
|[CRBTree::GetValueAt](#getvalueat)|Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.|  
|[CRBTree::IsEmpty](#isempty)|Rufen Sie diese Methode für ein Strukturobjekt leere zu testen.|  
|[CRBTree::RemoveAll](#removeall)|Rufen Sie diese Methode zum Entfernen aller Elemente aus der **CRBTree** Objekt.|  
|[CRBTree::RemoveAt](#removeat)|Rufen Sie diese Methode, um entfernt das Element an der angegebenen Position in der **CRBTree** Objekt.|  
|[CRBTree::SetValueAt](#setvalueat)|Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Rot-Schwarz-Struktur ist eine binäre Suche-Struktur, die eine zusätzliche verwendet Bit pro Knoten, um sicherzustellen, dass er bleibt "Ausbalanciert", die, die Höhe der Struktur nicht unverhältnismäßig groß und die Leistung beeinträchtigen.  
  
 Diese Vorlagenklasse von verwendet werden soll [CRBMap](../../atl/reference/crbmap-class.md) und [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Der Großteil der Methoden, die diese abgeleiteten Klassen bilden, bereitgestellt `CRBTree`.  
  
 Eine vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="cpair_class"></a>CRBTree::CPair-Klasse  
 Eine Klasse, die die Schlüssel-Wert-Elemente enthält.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse wird von den Methoden verwendet [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), und [CRBTree::GetPrev](#getprev) Zugriff auf die Schlüssel-Wert-Elemente, die in der Struktur gespeichert.  
  
 Die Elemente werden wie folgt:  
  
|||  
|-|-|  
|`m_key`|Das Datenelement, das wichtigste Element speichern.|  
|`m_value`|Der Datenmember, speichern das Value-Element.|  
  
##  <a name="dtor"></a>CRBTree:: ~ CRBTree  
 Der Destruktor.  
  
```
~CRBTree() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei. Aufrufe [CRBTree::RemoveAll](#removeall) alle Elemente zu löschen.  
  
##  <a name="findfirstkeyafter"></a>CRBTree::FindFirstKeyAfter  
 Rufen Sie diese Methode, um die Position des Elements zu suchen, die den nächsten verfügbaren Schlüssel verwendet.  
  
```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Ein Schlüssel-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die Position des Elements, das den nächsten verfügbaren Schlüssel verwendet. Wenn keine Elemente mehr vorhanden sind, wird NULL zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode vereinfacht das Durchlaufen der Struktur ohne Position im Voraus berechnen.  
  
##  <a name="getat"></a>CRBTree::GetAt  
 Rufen Sie diese Methode, um das Element an einer bestimmten Position in der Struktur abgerufen.  
  
```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert für die Position an.  
  
 `key`  
 Die Variable, die den Schlüssel empfängt.  
  
 *value*  
 Die Variable, die den Wert empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten beiden Formen zurückgeben, einen Zeiger auf eine [CPair](#cpair_class). Die dritte Form erhält einen Schlüssel und einen Wert für die angegebene Position.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert kann bestimmt werden, zuvor durch einen Aufruf einer Methode wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::GetTailPosition](#gettailposition).  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
##  <a name="getcount"></a>CRBTree::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Struktur zu erhalten.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von Elementen (jedes Schlüssel/Wert-Paar ist ein Element) in der Struktur gespeichert.  
  
##  <a name="getheadposition"></a>CRBTree::GetHeadPosition  
 Rufen Sie diese Methode, um den Wert für das Element am Anfang der Struktur abrufen.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die Position für das Element am Anfang der Struktur zurück.  
  
### <a name="remarks"></a>Hinweise  
 Der von zurückgegebene Wert `GetHeadPosition` können mit Methoden verwendet werden, z. B. [CRBTree::GetKeyAt](#getkeyat) oder [CRBTree::GetNext](#getnext) Durchlaufen der Struktur und Werte abrufen.  
  
##  <a name="getkeyat"></a>CRBTree::GetKeyAt  
 Rufen Sie diese Methode, um den Schlüssel aus einer angegebenen Position in der Struktur zu erhalten.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert für die Position an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Schlüssel an Position gespeicherte `pos` in der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pos` ist kein Wert gültige Position, Ergebnisse sind unvorhersehbar. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
##  <a name="getnext"></a>CRBTree::GetNext  
 Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` -Objekt, und die Position auf das nächste Element.  
  
```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den nächsten [CPair](#cpair_class) Wert in der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Struktur der `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextassoc"></a>CRBTree::GetNextAssoc  
 Rufen Sie diese Methode, um den Schlüssel und den Wert eines Elements in der Zuordnung gespeicherten abrufen und die Position auf das nächste Element.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 `key`  
 Der Vorlagenparameter, die den Typ des Schlüssels für die Struktur.  
  
 *value*  
 Der Vorlagenparameter, der den Wert der Struktur angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `pos` Position der Zähler wird nach jedem Aufruf aktualisiert. Wenn das abgerufene Element das letzte Element in der Struktur der `pos` auf NULL festgelegt ist.  
  
##  <a name="getnextkey"></a>CRBTree::GetNextKey  
 Rufen Sie diese Methode, um den Schlüssel für ein Element in der Struktur zu erhalten und die Position auf das nächste Element.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Schlüssel in der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Leistungsindikator `pos`. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Position Zähler auf NULL festgelegt.  
  
##  <a name="getnextvalue"></a>CRBTree::GetNextValue  
 Rufen Sie diese Methode, um ein Element in der Struktur zu nutzen und die Position auf das nächste Element.  
  
```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den nächsten Wert in der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Leistungsindikator `pos`. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Position Zähler auf NULL festgelegt.  
  
##  <a name="getprev"></a>CRBTree::GetPrev  
 Rufen Sie diese Methode, um einen Zeiger auf ein Element in der `CRBTree` -Objekt, und aktualisieren Sie die Position zum vorherigen Element.  
  
```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die vorherige [CPair](#cpair_class) Wert in der Struktur gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die aktuelle Position Leistungsindikator `pos`. Wenn keine weiteren Einträge in der Struktur vorhanden sind, wird der Position Zähler auf NULL festgelegt.  
  
##  <a name="gettailposition"></a>CRBTree::GetTailPosition  
 Rufen Sie diese Methode, um den Wert für die Position für das Element am Ende der Struktur zu erhalten.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Positionswert "für das Element am Ende der Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Der von zurückgegebene Wert `GetTailPosition` können mit Methoden verwendet werden, z. B. [CRBTree::GetKeyAt](#getkeyat) oder [CRBTree::GetPrev](#getprev) Durchlaufen der Struktur und Werte abrufen.  
  
##  <a name="getvalueat"></a>CRBTree::GetValueAt  
 Rufen Sie diese Methode zum Abrufen des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.  
  
```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den Wert gespeichert, die an der angegebenen Position in der `CRBTree` Objekt.  
  
##  <a name="isempty"></a>CRBTree::IsEmpty  
 Rufen Sie diese Methode für ein Strukturobjekt leere zu testen.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist die Struktur leer, wird **false** andernfalls.  
  
##  <a name="kinargtype"></a>CRBTree::KINARGTYPE  
 Typ verwendet, wenn ein Schlüssel als Eingabeargument übergeben wird.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CRBTree::KOUTARGTYPE  
 -Typ, wenn ein Schlüssel als ausgabeargument zurückgegeben wird.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="removeall"></a>CRBTree::RemoveAll  
 Rufen Sie diese Methode zum Entfernen aller Elemente aus der `CRBTree` Objekt.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht das `CRBTree` -Objekt, der belegte Arbeitsspeicher zum Speichern der Elemente.  
  
##  <a name="removeat"></a>CRBTree::RemoveAt  
 Rufen Sie diese Methode, um entfernt das Element an der angegebenen Position in der **CRBTree** Objekt.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="remarks"></a>Hinweise  
 Entfernt den Schlüssel/Wert-Paar an der angegebenen Position gespeichert. Der zum Speichern des Elements verwendete Arbeitsspeicher wird freigegeben. Die POSITION verweist `pos` ungültig, und während die POSITION der anderen Elemente in der Struktur gültig bleibt, sie müssen nicht unbedingt beibehalten die Reihenfolge.  
  
##  <a name="setvalueat"></a>CRBTree::SetValueAt  
 Rufen Sie diese Methode zum Ändern des Werts gespeichert, die an einer bestimmten Position in der `CRBTree` Objekt.  
  
```
void SetValueAt(POSITION pos, VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Position Zähler, der durch einen vorherigen Aufruf von Methoden zurückgegeben, wie z. B. [CRBTree::GetHeadPosition](#getheadposition) oder [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 *value*  
 Der hinzuzufügende Wert der `CRBTree` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ändert das Value-Element gespeichert, die an der angegebenen Position in der `CRBTree` Objekt.  
  
##  <a name="vinargtype"></a>CRBTree::VINARGTYPE  
 -Typ, wenn der Wert als Eingabeargument übergeben wird.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CRBTree::VOUTARGTYPE  
 -Typ, wenn der Wert als ausgabeargument übergeben wird.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

