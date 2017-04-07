---
title: Klasse CMapStringToString | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- collection classes, string mapping
- strings [C++], mapping
- strings [C++], class for mapping
- CMapStringToString class
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
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
ms.openlocfilehash: 58ca2023d57c2865dadc8dfab304aab2fa39a96b
ms.lasthandoff: 02/24/2017

---
# <a name="cmapstringtostring-class"></a>CMapStringToString-Klasse
Unterstützt Zuordnungen von `CString` -Objekten mit `CString` -Objekten als Schlüssel.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
 Die Memberfunktionen von `CMapStringToString` ähneln den Memberfunktionen der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CMapStringToOb`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CObject` Zeiger als Rückgabewert oder "output"-Parameter verwenden, funktionieren, ersetzen Sie einen Zeiger auf `char`. Immer dort, wo ein `CObject` Zeiger als Funktionsparameter 'input'-, ersetzen Sie einen Zeiger auf `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 Beispielsweise übersetzt zu  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>Öffentliche Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|Eine geschachtelte Struktur, die einen Schlüsselwert und der Wert des zugeordneten Objekts enthält.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Bestimmt die aktuelle Anzahl der Elemente in der Hashtabelle.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Gibt die Position des ersten Elements zurück.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Berechnet den Hashwert, der einem angegebenen Schlüssel.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Initialisiert die Hash-Tabelle.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Tests für die leere Zuordnung Bedingung (keine Elemente).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Sucht einen void-Zeiger anhand des Schlüssels void-Zeiger. Der Wert des Zeigers, nicht die Entität, auf die verwiesen, wird für die beim Schlüsselvergleich verwendet.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Gibt einen Verweis auf den zugeordneten Schlüssel für das angegebene Schlüssel-Wert zurück.|  
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Ruft einen Zeiger auf dem erste `CString` in der Zuordnung.|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Ruft einen Zeiger auf dem nächsten `CString` durchlaufen werden können.|  
|[CMapStringToString::PLookup](#plookup)|Gibt einen Zeiger auf ein `CString` , dessen Wert den angegebenen Wert entspricht.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Fügt ein Element in der Zuordnung. ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersetzung für `SetAt`.|  
  
## <a name="remarks"></a>Hinweise  
 `CMapStringToString`enthält die `IMPLEMENT_SERIAL` Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Jedes Element wird wiederum serialisiert, wenn eine Zuordnung in ein Archiv, entweder mit den überladenen einfügen gespeichert ist ( ** << **) Operator oder mit der `Serialize` Member-Funktion.  
  
 Wenn Sie eine Sicherung der einzelnen benötigen `CString` -  `CString` Elemente müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CMapStringToString` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die `CString` Objekte werden nach Bedarf entfernt.  
  
 Weitere Informationen zu `CMapStringToString`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="cpair"></a>CMapStringToString::CPair  
 Enthält einen Schlüsselwert und der Wert des zugeordneten Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine geschachtelte Struktur in der Klasse [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).  
  
 Die Struktur besteht aus zwei Feldern:  
  
- **Schlüssel** der tatsächliche Wert, der den Typ des Schlüssels.  
  
- **Wert** den Wert des zugeordneten Objekts.  
  
 Es wird verwendet, um die Rückgabewerte zu speichern [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), und [CMapStringToString::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung, finden Sie im Beispiel für [CMapStringToString::PLookup](#plookup).  
  
##  <a name="pgetfirstassoc"></a>CMapStringToString::PGetFirstAssoc  
 Gibt den ersten Eintrag der Map-Objekt zurück.  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den ersten Eintrag in der Karte; finden Sie unter [CMapStringToString::CPair](#cpair). Wenn die Zuordnung leer ist, ist der Wert `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger das erste Element in der Map-Objekt zurückgeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#73;](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMapStringToString::PGetNextAssoc  
 Ruft das Map-Element, das auf den `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>Parameter  
 *pAssoc*  
 Verweist auf einen Eintrag für die Zuordnung von einem vorherigen zurückgegebene [PGetNextAssoc](#pgetnextassoc) oder [PGetFirstAssoc](#pgetfirstassoc) aufrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den nächsten Eintrag in der Karte; finden Sie unter [CMapStringToString::CPair](#cpair). Wenn das Element das letzte Element in der Zuordnung ist, ist der Wert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Durchlaufen aller Elemente in der Zuordnung. Das erste Element mit einem Aufruf abgerufen `PGetFirstAssoc` und durchlaufen Sie dann auf die Karte mit aufeinander folgenden Aufrufen von `PGetNextAssoc`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMapStringToString::PLookup  
 Sucht nach einem bestimmten Schlüssel zugeordnete Wert.  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Ein Zeiger auf den Schlüssel für das Element, nach dem gesucht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den angegebenen Schlüssel.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für ein Map-Element mit einem Schlüssel zu suchen, die mit den angegebenen Schlüssel übereinstimmt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#74;](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




