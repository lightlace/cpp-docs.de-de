---
title: Klasse CMapWordToPtr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapWordToPtr
dev_langs:
- C++
helpviewer_keywords:
- 16-bit word mapping
- CMapWordToPtr class
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 982d42b1204d57e2abf76498b90c17864db34fb9
ms.lasthandoff: 02/24/2017

---
# <a name="cmapwordtoptr-class"></a>CMapWordToPtr-Klasse
Unterstützt Zuordnungen von void-Zeigern mit 16-Bit-Wörtern als Schlüssel.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMapWordToPtr : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
 Die Memberfunktionen von `CMapWordToPtr` ähneln den Memberfunktionen der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CMapStringToOb`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Wenn Sie einen `CObject`-Zeiger als Funktionsparameter oder als Rückgabewert finden, ersetzen Sie einen Zeiger auf `void`. Immer dort, wo ein `CString` oder **const** Zeiger auf `char` als Funktionsparameter oder Rückgabewert, ersetzen **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 Beispielsweise übersetzt zu  
  
 `BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`  
  
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
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Fügt ein Element in der Zuordnung. ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersetzung für `SetAt`.|  
  
## <a name="remarks"></a>Hinweise  
 `CMapWordToPtr` enthält das `IMPLEMENT_DYNAMIC`-Makro zur Unterstützung von Laufzeittypenzugriff und zum Sichern in ein `CDumpContext`-Objekt. Wenn Sie ein Abbild der einzelnen Elemente benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Word-Zeiger-Karten können nicht serialisiert werden.  
  
 Wenn ein `CMapWordToPtr` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die Wörter und die Zeiger werden entfernt. Die Entitäten, die Zeiger auf die verwiesen wird, werden nicht entfernt.  
  
 Weitere Informationen zu `CMapWordToPtr`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




