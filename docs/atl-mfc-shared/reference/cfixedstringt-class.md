---
title: CFixedStringT Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f357a70a728b388c3b5d3d26ac4efd0d4c84434a
ms.lasthandoff: 02/24/2017

---
# <a name="cfixedstringt-class"></a>CFixedStringT-Klasse
Diese Klasse stellt ein Zeichenfolgenobjekt mit einer festen Zeichenpuffer.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>Parameter  
 `StringType`  
 Für die feste Zeichenfolge-Objekt als Basisklasse verwendet und kann `CStringT`-basierten Typ. Beispiele hierfür sind `CString`, `CStringA`, und `CStringW`.  
  
 *t_nChars*  
 Die Anzahl der Zeichen im Puffer gespeichert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Der Konstruktor für das String-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Weist einen neuen Wert zu einem `CFixedStringT` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist ein Beispiel für eine benutzerdefinierte Klasse basierend auf `CStringT`. Obwohl sehr ähnlich, unterscheiden sich die beiden Klassen in Implementierung. Die wichtigsten Unterschiede zwischen `CFixedStringT` und `CStringT` sind:  
  
-   Der erste Zeichenpuffer wird als Teil des Objekts zugeordnet und Größe hat *T_nChars*. Dadurch wird die **CFixedString** -Objekt, das ein Block zusammenhängender Arbeitsspeicher zu belegen. Jedoch wenn den Inhalt einer `CFixedStringT` Objekt hinausgeht *T_nChars*, der Puffer wird dynamisch zugewiesen.  
  
-   Den Zeichenpuffer für einen `CFixedStringT` Objekt ist immer die gleiche Länge ( *T_nChars*). Es gibt keine Einschränkung für die Puffergröße für `CStringT` Objekte.  
  
-   Der Speicher-Manager für `CFixedStringT` wird angepasst, so, dass der Freigabe einer [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) Objekt zwischen zwei oder mehr `CFixedStringT` Objectsis nicht zulässig. `CStringT`Objekte müssen diese Einschränkung nicht.  
  
 Für Weitere Informationen über die Anpassung der `CFixedStringT` und Verwaltung des Arbeitsspeichers für String-Objekten im Allgemeinen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** cstringt.h  
  
##  <a name="a-namecfixedstringta--cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a>CFixedStringT::CFixedStringT  
 Erstellt ein `CFixedStringT`-Objekt.  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Eine auf Null endende Zeichenfolge, die in diese kopiert werden `CFixedStringT` Objekt.  
  
 `str`  
 Eine vorhandene `CFixedStringT` Objekt in diese kopiert werden `CFixedStringT` Objekt.  
  
 `pStringMgr`  
 Ein Zeiger auf den Speicher-Manager von der `CFixedStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Verwaltung des Arbeitsspeichers für `CFixedStringT`, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Hinweise  
 Da die Konstruktoren die Eingabedaten in neuen reservierten Speicher kopieren, sollten Sie bedenken, dass der Speicher Ausnahmen führen können. Beachten Sie, dass einige dieser Konstruktoren als Funktionen fungieren.  
  
##  <a name="a-nameoperatoreqa--cfixedstringtoperator-"></a><a name="operator__eq"></a>CFixedStringT::operator =  
 Initialisiert eine vorhandene `CFixedStringT` Objekt mit neuen Daten.  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Eine auf Null endende Zeichenfolge, die in diese kopiert werden `CFixedStringT` Objekt.  
  
 `psz`  
 Eine vorhandene `CFixedStringT` in diese kopiert werden `CFixedStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten sich bewusst sein, dass der Speicher Ausnahmen auftreten, bei jeder Verwendung den Zuweisungsoperator, da häufig neuer Speicher zugeordnet ist, enthält das resultierende `CFixedStringT` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)





