---
title: CSimpleMap Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27e4fdad706ab9e586efe72663880646e6f50f11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="csimplemap-class"></a>CSimpleMap-Klasse
Diese Klasse bietet Unterstützung für eine einfache Zuordnung-Array.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>  
class CSimpleMap
```  
  
#### <a name="parameters"></a>Parameter  
 `TKey`  
 Der Typ des Key-Element.  
  
 `TVal`  
 Der Werttyp-Element.  
  
 `TEqual`  
 Ein Merkmal ""-Objekt, das Definieren der Gleichheitstest für Elemente des Typs `T`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|Die Typdefinition für den Werttyp.|  
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|Die Typdefinition für den Typ des Schlüssels.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMap::CSimpleMap](#csimplemap)|Der Konstruktor.|  
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMap::Add](#add)|Fügt einen Schlüssel und den zugehörigen Wert in das Zuordnungsarray an.|  
|[CSimpleMap::FindKey](#findkey)|Sucht nach einem bestimmten Schlüssel.|  
|[CSimpleMap::FindVal](#findval)|Sucht nach einem bestimmten Wert.|  
|[CSimpleMap::GetKeyAt](#getkeyat)|Ruft den angegebenen Schlüssel ab.|  
|[CSimpleMap::GetSize](#getsize)|Gibt die Anzahl von Einträgen in der Zuordnung Array zurück.|  
|[CSimpleMap::GetValueAt](#getvalueat)|Ruft den angegebenen Wert.|  
|[CSimpleMap::Lookup](#lookup)|Gibt den mit dem angegebenen Schlüssel zugeordneten Wert zurück.|  
|[CSimpleMap::Remove](#remove)|Entfernt einen Schlüssel und einen übereinstimmenden Wert an.|  
|[CSimpleMap::RemoveAll](#removeall)|Entfernt alle Schlüssel und Werte.|  
|[CSimpleMap::RemoveAt](#removeat)|Entfernt einen bestimmten Schlüssel und einen übereinstimmenden Wert an.|  
|[CSimpleMap::ReverseLookup](#reverselookup)|Gibt den zugeordneten Schlüssel für den angegebenen Wert zurück.|  
|[CSimpleMap::SetAt](#setat)|Legt den Wert, der dem angegebenen Schlüssel zugeordnet.|  
|[CSimpleMap::SetAtIndex](#setatindex)|Legt fest, die bestimmten Schlüssel und Wert.|  
  
## <a name="remarks"></a>Hinweise  
 `CSimpleMap`bietet Unterstützung für eine einfache Zuordnung Array eines angegebenen Typs `T`, verwalten eine nicht geordnete Array von Schlüsselelemente und die zugehörigen Werte.  
  
 Der Parameter `TEqual` bietet eine Möglichkeit zum Definieren einer Gleichheitsfunktion für zwei Elemente des Typs `T`. Durch Erstellen einer Klasse ähnelt [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), es ist möglich, die das Verhalten des Tests auf Gleichheit für alle angegebenen Arrays zu ändern. Z. B. beim Umgang mit der ein Array von Zeigern es möglicherweise nützlich, um die Gleichheit als abhängig von den Werten zu definieren, die die Zeiger verweisen. Nutzt die standardmäßige Implementierung **operator==()**.  
  
 Beide `CSimpleMap` und [CSimpleArray](../../atl/reference/csimplearray-class.md) angegeben für Kompatibilität mit früheren ATL frei, und mehr abgeschlossen und effiziente Implementierungen Auflistung bereitgestellt [CAtlArray](../../atl/reference/catlarray-class.md) und [ CAtlMap](../../atl/reference/catlmap-class.md).  
  
 Im Gegensatz zu anderen Sammlungen Zuordnung ATL- und MFC diese Klasse wird mit einem einfachen Array implementiert, und sucht erfordern eine lineare Suche. `CAtlMap`sollte verwendet werden, wenn das Array eine große Anzahl von Elementen enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleMap::Add  
 Fügt einen Schlüssel und den zugehörigen Wert in das Zuordnungsarray an.  
  
```
BOOL Add(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
 *val*  
 Der zugeordnete Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Schlüssel und Wert wurde erfolgreich hinzugefügt, andernfalls FALSE wurden.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Schlüssel / Wert-Paar hinzugefügt Ursachen, die die Zuordnung array Speicher reserviert und zugewiesen werden, um sicherzustellen, dass die Daten für jede immer zusammenhängend gespeichert werden. Das heißt, folgt das zweite Schlüsselelement immer direkt das erste Schlüsselelement im Arbeitsspeicher und so weiter.  
  
##  <a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType  
 Eine Typedef für den Typ des Schlüssels.  
  
```
typedef TVal _ArrayElementType;
```  
  
##  <a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType  
 Eine Typedef für den Werttyp.  
  
```
typedef TKey _ArrayKeyType;
```  
  
##  <a name="csimplemap"></a>CSimpleMap::CSimpleMap  
 Der Konstruktor.  
  
```
CSimpleMap();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert den Datenmember an.  
  
##  <a name="dtor"></a>CSimpleMap:: ~ CSimpleMap  
 Der Destruktor.  
  
```
~CSimpleMap();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="findkey"></a>CSimpleMap::FindKey  
 Sucht nach einem bestimmten Schlüssel.  
  
```
int FindKey(const TKey& key) const;
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der zu suchende Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt der Index zurück, wenn der Schlüssel gefunden, andernfalls gibt-1 zurück.  
  
##  <a name="findval"></a>CSimpleMap::FindVal  
 Sucht nach einem bestimmten Wert.  
  
```
int FindVal(const TVal& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 *val*  
 Der Wert für die Suche.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, dass der Index des Werts, wenn es gefunden wird, andernfalls-1 zurück.  
  
##  <a name="getkeyat"></a>CSimpleMap::GetKeyAt  
 Ruft den Schlüssel am angegebenen Index ab.  
  
```
TKey& GetKeyAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des zurückzugebenden Schlüssels.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Schlüssel verweist `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Der Index übergebenes `nIndex` muss für den Rückgabewert in sinnvoll gültig sein.  
  
##  <a name="getsize"></a>CSimpleMap::GetSize  
 Gibt die Anzahl von Einträgen in der Zuordnung Array zurück.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von Einträgen (einen Schlüssel und Wert ist ein Eintrag) in der Zuordnung Array zurück.  
  
##  <a name="getvalueat"></a>CSimpleMap::GetValueAt  
 Ruft den Wert am angegebenen Index ab.  
  
```
TVal& GetValueAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des zurückzugebenden Werts.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert verweist `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Der Index übergebenes `nIndex` muss für den Rückgabewert in sinnvoll gültig sein.  
  
##  <a name="lookup"></a>CSimpleMap::Lookup  
 Gibt den mit dem angegebenen Schlüssel zugeordneten Wert zurück.  
  
```
TVal Lookup(const TKey& key) const;
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den zugeordneten Wert zurück. Ist kein passender Schlüssel gefunden wurde, wird NULL zurückgegeben.  
  
##  <a name="remove"></a>CSimpleMap::Remove  
 Entfernt einen Schlüssel und einen übereinstimmenden Wert an.  
  
```
BOOL Remove(const TKey& key);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Schlüssel und die übereinstimmenden Wert wurde erfolgreich entfernt, andernfalls FALSE wurden.  
  
##  <a name="removeall"></a>CSimpleMap::RemoveAll  
 Entfernt alle Schlüssel und Werte.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle Schlüssel und Werte aus der Zuordnung Array-Objekt.  
  
##  <a name="removeat"></a>CSimpleMap::RemoveAt  
 Entfernt einen Schlüssel und den zugeordneten Wert am angegebenen Index.  
  
```
BOOL RemoveAt(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Schlüssels und des zugehörigen Wert zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg "false" zurück, wenn der angegebene Index einen ungültigen Index liegt.  
  
##  <a name="reverselookup"></a>CSimpleMap::ReverseLookup  
 Gibt den zugeordneten Schlüssel für den angegebenen Wert zurück.  
  
```
TKey ReverseLookup(const TVal& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 *val*  
 Der Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den zugeordneten Schlüssel zurück. Ist kein passender Schlüssel gefunden wurde, wird NULL zurückgegeben.  
  
##  <a name="setat"></a>CSimpleMap::SetAt  
 Legt den Wert, der dem angegebenen Schlüssel zugeordnet.  
  
```
BOOL SetAt(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel.  
  
 *val*  
 Der neue Wert zugewiesen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Schlüssel gefunden wurde, und der Wert anderweitig wurde erfolgreich geändert, "false war".  
  
##  <a name="setatindex"></a>CSimpleMap::SetAtIndex  
 Legt den Schlüssel und Wert an einem angegebenen Index fest.  
  
```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index, verweisen Sie auf den Schlüssel und Wert ' Paarbildung ', um zu ändern.  
  
 `key`  
 Der neue Schlüssel.  
  
 *val*  
 Der neue Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn erfolgreich, "false", wenn der Index ungültig war.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert den Schlüssel und den Wert verweist `nIndex`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
