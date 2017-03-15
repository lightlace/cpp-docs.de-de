---
title: CMapStringToOb Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToOb
dev_langs:
- C++
helpviewer_keywords:
- collection classes, string mapping
- CMapStringToOb class
- strings [C++], class for mapping
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 20
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
ms.openlocfilehash: 2bfd277ebc1f00784d8e3d9686623777cb7fb5a5
ms.lasthandoff: 02/24/2017

---
# <a name="cmapstringtoob-class"></a>CMapStringToOb-Klasse
Eine Wörterbuchauflistungsklasse, die eindeutige `CString` -Objekte und `CObject` -Zeiger einander zuordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Bestimmt die aktuelle Anzahl der Elemente in der Hashtabelle.|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|  
|[CMapStringToOb::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|Gibt die Position des ersten Elements zurück.|  
|[CMapStringToOb::HashKey](#hashkey)|Berechnet den Hashwert, der einem angegebenen Schlüssel.|  
|[CMapStringToOb::InitHashTable](#inithashtable)|Initialisiert die Hash-Tabelle.|  
|[CMapStringToOb::IsEmpty](#isempty)|Tests für die leere Zuordnung Bedingung (keine Elemente).|  
|[CMapStringToOb::Lookup](#lookup)|Sucht einen void-Zeiger anhand des Schlüssels void-Zeiger. Der Wert des Zeigers, nicht die Entität, auf die verwiesen, wird für die beim Schlüsselvergleich verwendet.|  
|[CMapStringToOb::LookupKey](#lookupkey)|Gibt einen Verweis auf den zugeordneten Schlüssel für das angegebene Schlüssel-Wert zurück.|  
|[CMapStringToOb::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMapStringToOb::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CMapStringToOb::SetAt](#setat)|Fügt ein Element in der Zuordnung. ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::operator]](#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersetzung für `SetAt`.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie eingefügt haben eine `CString` -  `CObject*` Paar (Element) in der Zuordnung können effizient abgerufen oder löschen Sie das Paar mit einer Zeichenfolge oder einen `CString` Wert als Schlüssel. Sie können auch alle Elemente in der Zuordnung durchlaufen.  
  
 Eine Variable vom Typ **POSITION** für den Zugriff von anderen Eintrag in allen Varianten der Zuordnung. Sie können eine **POSITION** einen Eintrag "merken" und die Zuordnung durchlaufen. Glauben, dass diese Iteration sequenziell Schlüsselwert ist; Es ist nicht. Die Reihenfolge der abgerufenen Elemente ist unbestimmt.  
  
 `CMapStringToOb`enthält die `IMPLEMENT_SERIAL` Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Jedes Element wird wiederum serialisiert, wenn eine Zuordnung in ein Archiv, entweder mit den überladenen einfügen gespeichert ist ( ** << **) Operator oder mit der `Serialize` Member-Funktion.  
  
 Sollten Sie einen Diagnose Dump der einzelnen Elemente in der Zuordnung (die `CString` Wert und die `CObject` Inhalt), müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CMapStringToOb` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die `CString` Objekte und die `CObject` Zeiger werden entfernt. Objekte der `CObject` Zeiger nicht zerstört.  
  
 Map-klassenableitung ist ähnlich wie die Liste Ableitung. Finden Sie im Artikel [Sammlungen](../../mfc/collections.md) für die Ableitung einer Klasse spezielle Liste veranschaulicht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="a-namecmapstringtooba--cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a>CMapStringToOb::CMapStringToOb  
 Erstellt ein leeres `CString`- zu - `CObject*` zuordnen.  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Gibt die Granularität der Reservierung von Speicher für die Erweiterung der Zuordnungs an.  
  
### <a name="remarks"></a>Hinweise  
 Mit zunehmender die Zuordnung in Einheiten von Arbeitsspeicher belegt `nBlockSize` Einträge.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb:: CMapStringToOb**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#63;](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
##  <a name="a-namegetcounta--cmapstringtoobgetcount"></a><a name="getcount"></a>CMapStringToOb::GetCount  
 Bestimmt, wie viele Elemente in der Zuordnung sind.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in dieser Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetCount`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#64;](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="a-namegethashtablesizea--cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize  
 Bestimmt die aktuelle Anzahl der Elemente in der Hashtabelle.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente in der Hashtabelle zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetHashTableSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|  
  
##  <a name="a-namegetnextassoca--cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc  
 Ruft das Map-Element in *rNextPosition*, dann werden die *rNextPosition* zum Verweisen auf das nächste Element in der Zuordnung.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rNextPosition*  
 Gibt einen Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert **GetNextAssoc** oder **GetStartPosition** aufrufen.  
  
 *rKey*  
 Gibt den zurückgegebenen Schlüssel des Elements abgerufen (eine Zeichenfolge).  
  
 *r-Wert*  
 Gibt der zurückgegebene Wert, der das abgerufene Element (ein **CObject** Zeiger). Weitere zu diesem Parameter finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht unbedingt die Sequenz von Schlüssel-Wert identisch ist.  
  
 Wenn das abgerufene Element das letzte Element in der Zuordnung und dann der neue Wert der *rNextPosition* Wert **NULL**.  
  
 Für die *rValue* -Parameter, achten Sie darauf, dass Sie Ihre Objekttyp umwandeln **CObject\*&**, also was erfordert, dass der Compiler, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFCCollections&#65;](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 Dies gilt nicht für **GetNextAssoc** für Karten, die auf Vorlagen basieren.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb::GetNextAssoc**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, void\*&** *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, WORD&** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (POSITION &** *rNextPosition* **, CString &** *rKey* **, void\* & ** *rValue* **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (POSITION &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (POSITION &** *rNextPosition* **, WORD &** *rKey* **, CObject\* & ** *rValue* **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, WORD&** *rKey* **, void\*&** *rValue* **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#66;](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="a-namegetsizea--cmapstringtoobgetsize"></a><a name="getsize"></a>CMapStringToOb::GetSize  
 Gibt die Anzahl der Elemente zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Zuordnung.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Zuordnung ab.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#67;](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="a-namegetstartpositiona--cmapstringtoobgetstartposition"></a><a name="getstartposition"></a>CMapStringToOb::GetStartPosition  
 Startet eine Zuordnung Iteration durch die Rückgabe einer **POSITION** -Wert, der an übergeben werden kann ein `GetNextAssoc` aufrufen.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert an der Position des ersten Durchlaufen der Karte; oder **NULL** , wenn die Zuordnung leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Reihenfolge der Iteration ist nicht vorhersagbar. "erste Element in der Zuordnung" hat daher keine besondere Bedeutung.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::GetStartPosition`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Positionieren Sie GetStartPosition (const).**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Positionieren Sie GetStartPosition (const).**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Positionieren Sie GetStartPosition (const).**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Positionieren Sie GetStartPosition (const).**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Positionieren Sie GetStartPosition (const).**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Positionieren Sie GetStartPosition (const).**|  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CMapStringToOb::GetNextAssoc](#getnextassoc).  
  
##  <a name="a-namehashkeya--cmapstringtoobhashkey"></a><a name="hashkey"></a>CMapStringToOb::HashKey  
 Berechnet den Hashwert, der einem angegebenen Schlüssel.  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel, dessen Hashwert berechnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Schlüssel-Wert  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::HashKey`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void\* ** `key` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void\* ** `key` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
  
##  <a name="a-nameinithashtablea--cmapstringtoobinithashtable"></a><a name="inithashtable"></a>CMapStringToOb::InitHashTable  
 Initialisiert die Hash-Tabelle.  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hashSize`  
 Anzahl der Einträge in der Hashtabelle.  
  
 `bAllocNow`  
 Wenn **TRUE**, ordnet die Hashtabelle, bei der Initialisierung; andernfalls wird die Tabelle zugeordnet, wenn benötigt.  
  
### <a name="remarks"></a>Hinweise  
 Für eine optimale Leistung sollte die Größe des Hash-Tabelle eine Primzahl. Um Konflikte zu minimieren, sollte die Größe ungefähr 20 Prozent größer als der größte erwartete DataSet.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::InitHashTable`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
  
##  <a name="a-nameisemptya--cmapstringtoobisempty"></a><a name="isempty"></a>CMapStringToOb::IsEmpty  
 Bestimmt, ob die Zuordnung leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn diese Zuordnung keine Elemente enthält; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [RemoveAll](#removeall).  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb:: IsEmpty**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|  
  
##  <a name="a-namelookupa--cmapstringtooblookup"></a><a name="lookup"></a>CMapStringToOb::Lookup  
 Gibt eine `CObject` Zeiger auf der Grundlage einer `CString` Wert.  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 `rValue`  
 Gibt den zurückgegebenen Wert aus dem nachgeschlagenen-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 `Lookup`verwendet einen Hashalgorithmus schnell das Map-Element mit einem Schlüssel finden, die genau übereinstimmt ( `CString` Wert).  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::LookUp`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL Lookup( void\*** `key` **, void\*&** `rValue` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL Lookup( void\*** `key` **, WORD&** `rValue` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL Lookup( LPCTSTR** `key` **, void\*&** `rValue` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL-Suche (LPCTSTR** `key` **, CString &** `rValue` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL Lookup( WORD** `key` **, CObject\*&** `rValue` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL Lookup( WORD** `key` **, void\*&** `rValue` **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#68;](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="a-namelookupkeya--cmapstringtooblookupkey"></a><a name="lookupkey"></a>CMapStringToOb::LookupKey  
 Gibt einen Verweis auf den zugeordneten Schlüssel für das angegebene Schlüssel-Wert zurück.  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 `rKey`  
 Der Verweis auf den zugeordneten Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Schlüssel gefunden wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit einem Verweis auf ein Schlüssel ist unsicher, wenn verwendet, nachdem das zugeordnete Element aus der Zuordnung entfernt wurde oder nachdem die Zuordnung zerstört wurde.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb:: LookupKey**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
  
##  <a name="a-nameoperatorata--cmapstringtooboperator--"></a><a name="operator_at"></a>CMapStringToOb::operator]  
 Praktische Ersatz für die `SetAt` -Memberfunktion.  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf einen Zeiger auf eine `CObject` -Objekt oder **NULL** , wenn die Zuordnung leer ist oder `key` liegt außerhalb des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Daher kann es nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden. Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt.  
  
 Es gibt keine "rechts" (r) dieser Operator entspricht, da es besteht die Möglichkeit, die ein Schlüssel nicht in der Zuordnung gefunden werden kann. Verwenden der `Lookup` Member-Funktion für das Element abrufen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind **CMapStringToOb::operator []**.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void\*& operator[](void\*** `key` **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD& operator[](void\*** `key` **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& operator[](lpctstr** `key` **\);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString- & -Operator [] (Lpctstr** `key` ** \);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& operator[](word** `key` **\);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& operator[](word** `key` **\);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#72;](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="a-nameremovealla--cmapstringtoobremoveall"></a><a name="removeall"></a>CMapStringToOb::RemoveAll  
 Entfernt alle Elemente aus dieser Zuordnung und zerstört der `CString` key-Objekte.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `CObject` -Objekten verwiesen, die von jedem Schlüssel wird nicht zerstört. Die `RemoveAll` Funktion kann Speicherverluste verursachen, wenn Sie nicht sicherstellen, dass der referenzierte `CObject` Objekte werden zerstört.  
  
 Die Funktion funktioniert ordnungsgemäß, wenn die Zuordnung bereits leer ist.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::RemoveAll`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll ();**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll ();**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll ();**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll ();**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll ();**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#69;](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="a-nameremovekeya--cmapstringtoobremovekey"></a><a name="removekey"></a>CMapStringToOb::RemoveKey  
 Sucht nach dem Eintrag für die Zuordnung, die bereitgestellten Schlüssel entspricht; Wenn der Schlüssel gefunden wird, wird anschließend den Eintrag entfernt.  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt die Zeichenfolge für die Zuordnung Suche verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies kann Speicherverluste verursachen, wenn die `CObject` Objekt nicht an anderer Stelle gelöscht.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::RemoveKey`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void\* ** `key` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void\* ** `key` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#70;](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="a-namesetata--cmapstringtoobsetat"></a><a name="setat"></a>CMapStringToOb::SetAt  
 Das primäre Mittel zum Einfügen eines Elements in einer Zuordnung.  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt die Zeichenfolge, die die Schlüssel des neuen Elements ist.  
  
 `newValue`  
 Gibt die `CObject` Zeiger, der den Wert des neuen Elements ist.  
  
### <a name="remarks"></a>Hinweise  
 Zunächst wird der Schlüssel gesucht. Wenn der Schlüssel, gefunden wird und klicken Sie dann der entsprechende Wert geändert wird, Andernfalls wird ein neues Element mit Schlüssel-Wert erstellt.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CMapStringToOb::SetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt( void\*** `key` **, void\*** `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt( void\*** `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt( LPCTSTR** `key` **, void\*** `newValue` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt( WORD** `key` **, CObject\*** `newValue` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt( WORD** `key` **, void\*** `newValue` **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#71;](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr-Klasse](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord-Klasse](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr-Klasse](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString-Klasse](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb-Klasse](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr-Klasse](../../mfc/reference/cmapwordtoptr-class.md)

