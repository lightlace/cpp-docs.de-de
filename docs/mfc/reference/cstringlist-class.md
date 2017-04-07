---
title: Klasse CStringList | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], lists
- lists, string
- CStringList class
- strings [C++], collections
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
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
ms.openlocfilehash: 0b67104e330890ffe8f67bac0dd3b129c7742a29
ms.lasthandoff: 02/24/2017

---
# <a name="cstringlist-class"></a>CStringList-Klasse
Unterstützt Listen von `CString` -Objekten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
 Die Memberfunktionen von `CStringList` ähneln den Memberfunktionen der Klasse [CObList](../../mfc/reference/coblist-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObList`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CObject` Zeiger als Rückgabewert, ersetzen Sie durch eine `CString` (keinen `CString` Zeiger). Immer dort, wo ein `CObject` Zeiger als Funktionsparameter, ersetzen Sie durch eine `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 Beispielsweise übersetzt zu  
  
 `CString& CStringList::GetHead() const;`  
  
 und  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 wird übersetzt in  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Erstellt eine leere Liste.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (wird eine neue Head).|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an das Ende der Liste (wird eine neue Erweiterung).|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|Ruft die Position eines Elements durch Zeigerwert angegeben.|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Ruft die Position eines Elements durch einen nullbasierten Index angegeben.|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Ruft das Element an einer angegebenen Position ab.|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Gibt die Anzahl der Elemente in dieser Liste zurück.|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Gibt das Head-Element der Liste (darf nicht leer sein).|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Gibt die Position des Head-Element der Liste zurück.|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Ruft das nächste Element durchlaufen werden können.|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Ruft das vorherige Element durchlaufen werden können.|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Gibt die Anzahl der Elemente in dieser Liste zurück.|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Gibt das Ende der Liste (darf nicht leer sein) zurück.|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Gibt die Position des Elements Ende der Liste.|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Fügt ein neues Element nach einer angegebenen Position ein.|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Fügt vor einer angegebenen Position ein neues Element.|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Tests für die leere Liste Bedingung (keine Elemente).|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Entfernt alle Elemente aus dieser Liste.|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Entfernt ein Element aus dieser Liste anhand der Position angegeben.|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Entfernt das Element am Anfang der Liste.|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Entfernt das Element dem Ende der Liste aus.|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Legt das Element an einer bestimmten Position fest.|  
  
## <a name="remarks"></a>Hinweise  
 Alle Vergleiche erfolgen zurück, was bedeutet, dass die Zeichen in der Zeichenfolge anstelle der Adressen der Zeichenfolgen verglichen werden.  
  
 `CStringList`enthält die `IMPLEMENT_SERIAL` Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Wenn eine Liste der `CString` Objekte wird in ein Archiv gespeichert, entweder mit einem überladenen Operator zum Einfügen oder mit der `Serialize` Member-Funktion, `CString` Element wiederum serialisiert wird.  
  
 Wenn Sie eine Sicherung der einzelnen benötigen `CString` Elemente müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Weitere Informationen zur Verwendung von `CStringList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




