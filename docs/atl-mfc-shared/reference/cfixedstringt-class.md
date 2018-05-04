---
title: CFixedStringT Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93125d15be32a95d71c763f476fad700dab65a3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
 Für die feste String-Objekt als Basisklasse verwendet und kann `CStringT`-basiertem Typ. Einige Beispiele für `CString`, `CStringA`, und `CStringW`.  
  
 *t_nChars*  
 Die Anzahl der Zeichen im Puffer gespeichert.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Der Konstruktor für den String-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Weist einen neuen Wert zu einem `CFixedStringT` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist ein Beispiel für eine benutzerdefinierte Zeichenfolge-Klasse, die basierend auf `CStringT`. Zwar sehr ähnlich, unterscheiden sich die beiden Klassen in der Implementierung ein. Die wichtigsten Unterschiede zwischen `CFixedStringT` und `CStringT` sind:  
  
-   Das Anfangszeichen Puffer wird als Teil des Objekts zugeordnet und Größe hat *T_nChars*. Dies ermöglicht die **CFixedString** Objekt, das ein Block zusammenhängender Arbeitsspeicher zur leistungsverbesserung belegen. Jedoch wenn den Inhalt einer `CFixedStringT` Objekt hinausgeht *T_nChars*, der Puffer wird dynamisch zugewiesen.  
  
-   Der Zeichenpuffer für eine `CFixedStringT` Objekt weist immer dieselbe Länge ( *T_nChars*). Es gibt keine Einschränkung hinsichtlich der Puffergröße für `CStringT` Objekte.  
  
-   Der Speicher-Manager für `CFixedStringT` wird angepasst, dass der Freigabe einer [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) Objekt zwischen mindestens zwei `CFixedStringT` Objectsis nicht zulässig. `CStringT` -Objekte verfügen über diese Einschränkung nicht.  
  
 Informationen über die Anpassung der `CFixedStringT` und Verwaltung des Arbeitsspeichers für Zeichenfolgenobjekten im Allgemeinen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** cstringt.h  
  
##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT  
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
 Ein Zeiger auf Speicher-Manager, der die `CFixedStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Verwaltung des Arbeitsspeichers für `CFixedStringT`, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Hinweise  
 Da die Konstruktoren die Eingabedaten in den neuen belegten Speicher kopieren, sollten Sie bedenken, dass der Arbeitsspeicher Ausnahmen führen können. Beachten Sie, dass einige dieser Konstruktoren als Konvertierungsfunktionen fungieren.  
  
##  <a name="operator__eq"></a>  CFixedStringT::operator =  
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
 Sie sollten sich bewusst sein, dass der Arbeitsspeicher Ausnahmen auftreten, jedes Mal, wenn Sie den Zuweisungsoperator da häufig neue Speicher, zum Speichern der resultierenden reserviert wird `CFixedStringT` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)




