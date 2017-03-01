---
title: CSimpleMap Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSimpleMap
- ATL.CSimpleMap
- CSimpleMap
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c02ef1d9d3fafebf38abaaa55d77511f4476a02f
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemap-class"></a>CSimpleMap-Klasse
Diese Klasse bietet Unterstützung für eine einfache Zuordnung Array.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>  
class CSimpleMap
```  
  
#### <a name="parameters"></a>Parameter  
 `TKey`  
 Der Typ des Key-Element.  
  
 `TVal`  
 Der Wert-Elementtyp.  
  
 `TEqual`  
 Ein Merkmal-Objekt, und definieren den Gleichheitstest auf, für Elemente des Typs `T`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|TypeDef für den Werttyp.|  
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|TypeDef für den Typ des Schlüssels.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMap::CSimpleMap](#csimplemap)|Der Konstruktor.|  
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMap::Add](#add)|Fügt ein Schlüssel und den zugehörigen Wert in das Zuordnungsarray.|  
|[CSimpleMap::FindKey](#findkey)|Sucht nach einem bestimmten Schlüssel.|  
|[CSimpleMap::FindVal](#findval)|Sucht nach einem bestimmten Wert.|  
|[CSimpleMap::GetKeyAt](#getkeyat)|Ruft den angegebenen Schlüssel ab.|  
|[CSimpleMap::GetSize](#getsize)|Gibt die Anzahl der Einträge in der Mapping-Array zurück.|  
|[CSimpleMap::GetValueAt](#getvalueat)|Ruft den angegebenen Wert.|  
|[CSimpleMap::Lookup](#lookup)|Gibt den dem angegebenen Schlüssel zugeordneten Wert.|  
|[CSimpleMap::Remove](#remove)|Entfernt einen Schlüssel und einen übereinstimmenden Wert.|  
|[CSimpleMap::RemoveAll](#removeall)|Entfernt sämtliche Schlüssel und Werte.|  
|[CSimpleMap::RemoveAt](#removeat)|Entfernt einen bestimmten Schlüssel und einen übereinstimmenden Wert.|  
|[CSimpleMap::ReverseLookup](#reverselookup)|Gibt den zugeordneten Schlüssel für den angegebenen Wert zurück.|  
|[CSimpleMap::SetAt](#setat)|Legt den dem angegebenen Schlüssel zugeordneten Wert.|  
|[CSimpleMap::SetAtIndex](#setatindex)|Legt fest, die bestimmten Schlüssel und Wert.|  
  
## <a name="remarks"></a>Hinweise  
 `CSimpleMap`bietet Unterstützung für eine einfache Zuordnung Array eines beliebigen angegebenen Typs `T`, Verwalten von Array von ungeordneten der wichtigsten Elemente und die zugehörigen Werte.  
  
 Der Parameter `TEqual` ermöglicht das Definieren einer Gleichheitsfunktion für zwei Elemente des Typs `T`. Durch Erstellen einer Klasse ähnelt [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), es ist möglich, die das Verhalten des Tests für alle angegebenen Arrays auf Gleichheit zu ändern. Beispielsweise kann beim Umgang mit der ein Array von Zeigern, es hilfreich sein, die Gleichheit als abhängig von den Werten zu definieren, die Zeiger verweisen. Die standardmäßige Implementierung nutzt **operator==()**.  
  
 Beide `CSimpleMap` und [CSimpleArray](../../atl/reference/csimplearray-class.md) für Kompatibilität mit früheren ATL frei, und vollständige und effiziente sammlungsimplementierungen bereitgestellt werden bereitgestellt [CAtlArray](../../atl/reference/catlarray-class.md) und [CAtlMap](../../atl/reference/catlmap-class.md).  
  
 Im Gegensatz zu anderen Auflistungen in den ATL- und MFC-Zuordnung dieser Klasse mit einem einfachen Array implementiert ist, und sucht erfordern eine lineare Suche. `CAtlMap`sollte verwendet werden, wenn das Array eine große Anzahl von Elementen enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#91;](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]  
  
##  <a name="a-nameadda--csimplemapadd"></a><a name="add"></a>CSimpleMap::Add  
 Fügt ein Schlüssel und den zugehörigen Wert in das Zuordnungsarray.  
  
```
BOOL Add(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
 *val*  
 Der zugeordnete Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der Schlüssel und Wert wurde erfolgreich hinzugefügt, andernfalls FALSE wurden.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Schlüssel-Wert-Paar hinzugefügt, wird die Zuordnung array Arbeitsspeicher neu reserviert und freigegeben werden, um sicherzustellen, dass die Daten für jede immer zusammenhängend gespeichert ist. D. h. folgt das zweite wichtige Element immer direkt das erste wichtige Element im Arbeitsspeicher und so weiter.  
  
##  <a name="a-namearrayelementtypea--csimplemaparrayelementtype"></a><a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType  
 Eine Typedef für den Typ des Schlüssels.  
  
```
typedef TVal _ArrayElementType;
```  
  
##  <a name="a-namearraykeytypea--csimplemaparraykeytype"></a><a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType  
 Eine Typedef für den Werttyp.  
  
```
typedef TKey _ArrayKeyType;
```  
  
##  <a name="a-namecsimplemapa--csimplemapcsimplemap"></a><a name="csimplemap"></a>CSimpleMap::CSimpleMap  
 Der Konstruktor.  
  
```
CSimpleMap();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die Datenmember.  
  
##  <a name="a-namedtora--csimplemapcsimplemap"></a><a name="dtor"></a>CSimpleMap:: ~ CSimpleMap  
 Der Destruktor.  
  
```
~CSimpleMap();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="a-namefindkeya--csimplemapfindkey"></a><a name="findkey"></a>CSimpleMap::FindKey  
 Sucht nach einem bestimmten Schlüssel.  
  
```
int FindKey(const TKey& key) const;
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der zu suchende Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt der Index zurück, wenn der Schlüssel gefunden wird, andernfalls wird-1 zurückgegeben.  
  
##  <a name="a-namefindvala--csimplemapfindval"></a><a name="findval"></a>CSimpleMap::FindVal  
 Sucht nach einem bestimmten Wert.  
  
```
int FindVal(const TVal& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 *val*  
 Der Wert, nach dem gesucht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt der Index des Werts, wenn er gefunden wird, andernfalls-1 zurück.  
  
##  <a name="a-namegetkeyata--csimplemapgetkeyat"></a><a name="getkeyat"></a>CSimpleMap::GetKeyAt  
 Ruft den Schlüssel am angegebenen Index ab.  
  
```
TKey& GetKeyAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des zurückzugebenden Schlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Schlüssel auf die `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Der Index übergebener `nIndex` muss für den Rückgabewert sinnvoll ist gültig sein.  
  
##  <a name="a-namegetsizea--csimplemapgetsize"></a><a name="getsize"></a>CSimpleMap::GetSize  
 Gibt die Anzahl der Einträge in der Mapping-Array zurück.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Einträge (einen Schlüssel und Wert ist ein Eintrag) in der Mapping-Array zurück.  
  
##  <a name="a-namegetvalueata--csimplemapgetvalueat"></a><a name="getvalueat"></a>CSimpleMap::GetValueAt  
 Ruft den Wert am angegebenen Index ab.  
  
```
TVal& GetValueAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des zurückzugebenden Werts.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert auf die `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Der Index übergebener `nIndex` muss für den Rückgabewert sinnvoll ist gültig sein.  
  
##  <a name="a-namelookupa--csimplemaplookup"></a><a name="lookup"></a>CSimpleMap::Lookup  
 Gibt den dem angegebenen Schlüssel zugeordneten Wert.  
  
```
TVal Lookup(const TKey& key) const;
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den zugeordneten Wert zurück. Ist kein passender Schlüssel gefunden wurde, wird NULL zurückgegeben.  
  
##  <a name="a-nameremovea--csimplemapremove"></a><a name="remove"></a>CSimpleMap::Remove  
 Entfernt einen Schlüssel und einen übereinstimmenden Wert.  
  
```
BOOL Remove(const TKey& key);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der Schlüssel und die übereinstimmenden Wert wurde erfolgreich entfernt, andernfalls FALSE wurden.  
  
##  <a name="a-nameremovealla--csimplemapremoveall"></a><a name="removeall"></a>CSimpleMap::RemoveAll  
 Entfernt sämtliche Schlüssel und Werte.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt sämtliche Schlüssel und Werte aus der Mapping-Array-Objekt.  
  
##  <a name="a-nameremoveata--csimplemapremoveat"></a><a name="removeat"></a>CSimpleMap::RemoveAt  
 Entfernt einen Schlüssel und den zugeordneten Wert am angegebenen Index.  
  
```
BOOL RemoveAt(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Schlüssels und des zugeordneten Wert zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE bei Erfolg, "false" zurück, wenn der angegebene Index befindet sich ein ungültiger Index.  
  
##  <a name="a-namereverselookupa--csimplemapreverselookup"></a><a name="reverselookup"></a>CSimpleMap::ReverseLookup  
 Gibt den zugeordneten Schlüssel für den angegebenen Wert zurück.  
  
```
TKey ReverseLookup(const TVal& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 *val*  
 Der Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den zugeordneten Schlüssel zurück. Ist kein passender Schlüssel gefunden wurde, wird NULL zurückgegeben.  
  
##  <a name="a-namesetata--csimplemapsetat"></a><a name="setat"></a>CSimpleMap::SetAt  
 Legt den dem angegebenen Schlüssel zugeordneten Wert.  
  
```
BOOL SetAt(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
 *val*  
 Der neue Wert zuweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der Schlüssel gefunden wurde, und der Wert erfolgreich geändert, FALSE, andernfalls wurde.  
  
##  <a name="a-namesetatindexa--csimplemapsetatindex"></a><a name="setatindex"></a>CSimpleMap::SetAtIndex  
 Legt den Schlüssel und den Wert am angegebenen Index fest.  
  
```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index, verweisen Sie auf den Schlüssel und Wert koppeln, um zu ändern.  
  
 `key`  
 Der neue Schlüssel.  
  
 *val*  
 Der neue Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn erfolgreich, andernfalls FALSE, wenn der Index ungültig war.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert den Schlüssel und den Wert auf den `nIndex`.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

