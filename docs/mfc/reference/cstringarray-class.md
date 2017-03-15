---
title: Klasse CStringArray | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringArray
dev_langs:
- C++
helpviewer_keywords:
- string arrays
- arrays [C++], strings
- CStringArray class
- strings [C++], collections
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6f6ef1f6bdef74540948520cc27d6c10b143216c
ms.lasthandoff: 02/24/2017

---
# <a name="cstringarray-class"></a>CStringArray-Klasse
Unterstützt Arrays mit [CString](../../atl-mfc-shared/using-cstring.md) Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStringArray : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
 Die Memberfunktionen von `CStringArray` ähneln den Memberfunktionen der Klasse [CObArray](../../mfc/reference/cobarray-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObArray`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CObject` Zeiger als Rückgabewert, ersetzen Sie durch eine [CString](../../atl-mfc-shared/using-cstring.md) Objekt (keine [CString](../../atl-mfc-shared/using-cstring.md) Zeiger). Immer dort, wo ein `CObject`-Zeiger als Funktionsparameter angezeigt wird, ersetzen Sie einen `LPCTSTR`.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Beispielsweise übersetzt zu  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 und  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 wird übersetzt in  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Erstellt ein leeres Array.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Ermöglicht den Zugriff auf Elemente im Array. Kann **NULL**.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Gibt den größten gültigen Index zurück.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Bestimmt, ob das Array leer ist.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Entfernt alle Elemente aus diesem Array.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Entfernt ein Element an einem spezifischen Index.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Legt die Anzahl der Elemente im Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::operator]](../../mfc/reference/cobarray-class.md#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## <a name="remarks"></a>Hinweise  
 `CStringArray`enthält die `IMPLEMENT_SERIAL` Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Wenn ein Array mit `CString`-Objekten in einem Archiv gespeichert wird, entweder mit einem überladenen Operator zum Einfügen oder mit der `Serialize`-Member-Funktion, wird jedes Element der Reihe nach serialisiert.  
  
> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie eine Sicherung einzelner Zeichenfolgenelemente im Array benötigen, müssen Sie die Tiefe des Sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CString`-Array gelöscht wird oder wenn dessen Elemente entfernt werden, wird je nach Bedarf Zeichenfolgenspeicher freigegeben.  
  
 Weitere Informationen zur Verwendung von `CStringArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




