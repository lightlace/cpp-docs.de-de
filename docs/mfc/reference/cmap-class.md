---
title: CMap Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- dictionary mapping class
- collection classes, dictionary mapping
- CMap class
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 680d44fe6154861d2c638697cfc9d3fbeab36cc4
ms.lasthandoff: 02/24/2017

---
# <a name="cmap-class"></a>CMap-Klasse
Eine Wörterbuchauflistungsklasse, die eindeutigen Schlüsseln Werte zuordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>Parameter  
 `KEY`  
 Die Klasse des Objekts, das als Schlüssel für die Zuordnung verwendet.  
  
 `ARG` *_* `KEY`  
 Datentyp für `KEY` Argumente, in der Regel einen Verweis auf `KEY`.  
  
 `VALUE`  
 Die Klasse des Objekts in der Zuordnung gespeichert.  
  
 `ARG` *_* `VALUE`  
 Datentyp für `VALUE` Argumente, in der Regel einen Verweis auf `VALUE`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-structures"></a>Öffentliche Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|Eine geschachtelte Struktur, die einen Schlüsselwert und der Wert des zugeordneten Objekts enthält.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|Erstellt eine Auflistung, die Schlüsseln Werte zuordnet.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMap::GetHashTableSize](#gethashtablesize)|Gibt die Anzahl der Elemente in der Hashtabelle zurück.|  
|[CMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|  
|[CMap::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMap::GetStartPosition](#getstartposition)|Gibt die Position des ersten Elements zurück.|  
|[CMap::InitHashTable](#inithashtable)|Initialisiert die Hash-Tabelle und eine Größe angegeben.|  
|[CMap::IsEmpty](#isempty)|Tests für die leere Zuordnung Bedingung (keine Elemente).|  
|[CMap::Lookup](#lookup)|Sucht nach einem bestimmten Schlüssel zugeordnete Wert.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Gibt einen Zeiger auf das erste Element zurück.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|Ruft einen Zeiger auf das nächste Element durchlaufen werden können.|  
|[CMap::PLookup](#plookup)|Gibt einen Zeiger auf einen Schlüssel, dessen Wert dem angegebenen Wert übereinstimmt.|  
|[CMap::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMap::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CMap::SetAt](#setat)|Fügt ein Element in der Zuordnung. ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMap::operator]](#operator_at)|Fügt ein Element in der Zuordnung Â €"Operator Ersetzung für `SetAt`.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie ein Schlüssel-Wert-Paar (Element) in die Zuordnung eingefügt haben, können effizient abrufen oder löschen das Paar mit dem Schlüssel darauf zugreifen. Sie können auch alle Elemente in der Zuordnung durchlaufen.  
  
 Eine Variable vom Typ **POSITION** wird für den alternativen Zugriff auf Einträge verwendet. Sie können eine **POSITION** einen Eintrag "merken" und die Zuordnung durchlaufen. Glauben, dass diese Iteration sequenziell Schlüsselwert ist; Es ist nicht. Die Reihenfolge der abgerufenen Elemente ist unbestimmt.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CMap` Klasse. Finden Sie unter [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) im Abschnitt Makros und globale Variablen für die `MFC``Reference`.  
  
 `CMap`überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize) zur Unterstützung der Serialisierung und Sicherung der Elemente. Wenn eine Zuordnung mit einem Archiv gespeichert ist `Serialize`, jedes kartenelement wiederum serialisiert wird. Die standardmäßige Implementierung der von der `SerializeElements` Hilfsfunktion wird eine bitweise schreiben. Informationen über die Serialisierung der Auflistungselemente Zeiger aus abgeleiteten `CObject` oder andere benutzerdefinierte Typen finden Sie unter [Gewusst wie: Erstellen einer typsicheren Auflistung](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Wenn Sie einen Diagnose Dump der einzelnen Elemente in der Zuordnung (Schlüssel und Werte) benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CMap` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die Schlüssel und Werte werden entfernt.  
  
 Map-klassenableitung ist ähnlich wie die Liste Ableitung. Finden Sie im Artikel [Sammlungen](../../mfc/collections.md) für die Ableitung einer Klasse spezielle Liste veranschaulicht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="cmap"></a>CMap::CMap  
 Erstellt eine leere Zuordnung.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Gibt die Granularität der Reservierung von Speicher für die Erweiterung der Zuordnungs an.  
  
### <a name="remarks"></a>Hinweise  
 Mit zunehmender die Zuordnung in Einheiten von Arbeitsspeicher belegt `nBlockSize` Einträge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#56;](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 Enthält einen Schlüsselwert und der Wert des zugeordneten Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine geschachtelte Struktur in der Klasse [CMap](../../mfc/reference/cmap-class.md).  
  
 Die Struktur besteht aus zwei Feldern:  
  
- **KeyÂ Â Â** der tatsächliche Wert, der den Typ des Schlüssels.  
  
- **ValueÂ Â Â** der Wert des zugeordneten Objekts.  
  
 Es wird verwendet, um die Rückgabewerte zu speichern [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), und [CMap::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung, finden Sie im Beispiel für [CMap::PLookup](#plookup).  
  
##  <a name="getcount"></a>CMap::GetCount  
 Ruft die Anzahl der Elemente in der Zuordnung ab.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::Lookup](#lookup).  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 Bestimmt die Anzahl der Elemente in der Hashtabelle für die Karte.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Hashtabelle.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#57;](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="getnextassoc"></a>CMap::GetNextAssoc  
 Ruft das Map-Element in `rNextPosition`, dann werden die `rNextPosition` zum Verweisen auf das nächste Element in der Zuordnung.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rNextPosition`  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNextAssoc` oder `GetStartPosition` aufrufen.  
  
 *SCHLÜSSEL*  
 Der Vorlagenparameter, der den Schlüssel der Zuordnung angibt.  
  
 `rKey`  
 Gibt den zurückgegebenen Schlüssel des Elements abgerufen.  
  
 *WERT*  
 Der Vorlagenparameter, der den Wert der Zuordnung angibt.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert des Elements abgerufen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht unbedingt die Sequenz von Schlüssel-Wert identisch ist.  
  
 Wenn das abgerufene Element das letzte Element in der Zuordnung und dann der neue Wert der `rNextPosition` Wert **NULL**.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::SetAt](#setat).  
  
##  <a name="getsize"></a>CMap::GetSize  
 Gibt die Anzahl der Elemente zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Zuordnung ab.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 Startet eine Zuordnung Iteration durch die Rückgabe einer **POSITION** -Wert, der an übergeben werden kann ein `GetNextAssoc` aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert an der Position des ersten Durchlaufen der Karte; oder **NULL** , wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Reihenfolge der Iteration ist nicht vorhersagbar. "erste Element in der Zuordnung" hat daher keine besondere Bedeutung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::SetAt](#setat).  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 Initialisiert die Hash-Tabelle.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUEÂ);  
```  
  
### <a name="parameters"></a>Parameter  
 `hashSize`  
 Anzahl der Einträge in der Hashtabelle.  
  
 `bAllocNow`  
 Wenn **TRUE**, ordnet die Hashtabelle, bei der Initialisierung; andernfalls wird die Tabelle zugeordnet, wenn benötigt.  
  
### <a name="remarks"></a>Hinweise  
 Für eine optimale Leistung sollte die Größe des Hash-Tabelle eine Primzahl. Um Konflikte zu minimieren, sollte die Größe ungefähr 20 Prozent größer als der größte erwartete DataSet.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::Lookup](#lookup).  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 Bestimmt, ob die Zuordnung leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn diese Zuordnung keine Elemente enthält; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::RemoveAll](#removeall).  
  
##  <a name="lookup"></a>CMap::Lookup  
 Sucht nach einem bestimmten Schlüssel zugeordnete Wert.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_KEY`  
 Angabe des Typs der Vorlagenparameter der `key` Wert.  
  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 *WERT*  
 Gibt den Typ des Werts, der gesucht werden sollen.  
  
 `rValue`  
 Empfängt der gebundene Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `Lookup`verwendet einen Hashalgorithmus schnell das Map-Element mit einem Schlüssel finden, die mit den angegebenen Schlüssel übereinstimmt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>CMap::operator]  
 Praktische Ersatz für die `SetAt` -Memberfunktion.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>Parameter  
 *WERT*  
 Der Vorlagenparameter, die den Typ des Werts zuordnen.  
  
 `ARG_KEY`  
 Der Vorlagenparameter, der den Wert des Schlüssels angibt.  
  
 `key`  
 Der Schlüssel zum Abrufen des Werts aus der Zuordnung verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Daher kann es nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden. Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt.  
  
 Es gibt keine "rechts" (r) dieser Operator entspricht, da es besteht die Möglichkeit, die ein Schlüssel nicht in der Zuordnung gefunden werden kann. Verwenden der `Lookup` Member-Funktion für das Element abrufen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::Lookup](#lookup).  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Gibt den ersten Eintrag der Map-Objekt zurück.  
  
```  
const CPair* PGetFirstAssoc() const;Â CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den ersten Eintrag in der Karte; finden Sie unter [CMap::CPair](#cpair). Wenn die Zuordnung keine Einträge enthält, ist der Wert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger das erste Element in der Map-Objekt zurückgeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#59;](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 Ruft das Map-Element, das auf den `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>Parameter  
 *pAssocRet*  
 Verweist auf einen Eintrag für die Zuordnung von einem vorherigen zurückgegebene [PGetNextAssoc](#pgetnextassoc) oder [CMap::PGetFirstAssoc](#pgetfirstassoc) aufrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den nächsten Eintrag in der Karte; finden Sie unter [CMap::CPair](#cpair). Wenn das Element das letzte Element in der Zuordnung ist, ist der Wert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Durchlaufen aller Elemente in der Zuordnung. Das erste Element mit einem Aufruf abgerufen `PGetFirstAssoc` und durchlaufen Sie dann auf die Karte mit aufeinander folgenden Aufrufen von `PGetNextAssoc`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMap::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMap::PLookup  
 Sucht nach einem bestimmten Schlüssel zugeordnete Wert.  
  
```  
const CPair* PLookup(ARG_KEY  key) const;
CPair* PLookup(Â    ARG_KEY  keyÂ);  ```  
  
### Parameters  
 `key`  
 Key for the element to be searched for.  
  
### Return Value  
 A pointer to a key structure; see [CMap::CPair](#cpair). If no match is found, `CMap::PLookup` returns `NULL`.  
  
### Remarks  
 Call this method to search for a map element with a key that exactly matches the given key.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>  CMap::RemoveAll  
 Removes all the values from this map by calling the global helper function **DestructElements**.  
  
```  
void RemoveAll();
```  
  
### Remarks  
 The function works correctly if the map is already empty.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>  CMap::RemoveKey  
 Looks up the map entry corresponding to the supplied key; then, if the key is found, removes the entry.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the key.  
  
 `key`  
 Key for the element to be removed.  
  
### Return Value  
 Nonzero if the entry was found and successfully removed; otherwise 0.  
  
### Remarks  
 The **DestructElements** helper function is used to remove the entry.  
  
### Example  
 See the example for [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>  CMap::SetAt  
 The primary means to insert an element in a map.  
  
```  
void SetAt (ARG_KEY Schlüssel ARG_VALUE NewValue;)
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the `key` parameter.  
  
 `key`  
 Specifies the key of the new element.  
  
 `ARG_VALUE`  
 Template parameter specifying the type of the `newValue` parameter.  
  
 `newValue`  
 Specifies the value of the new element.  
  
### Remarks  
 First, the key is looked up. If the key is found, then the corresponding value is changed; otherwise a new key-value pair is created.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)  

