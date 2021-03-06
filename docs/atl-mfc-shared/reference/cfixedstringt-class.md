---
title: CFixedStringT-Klasse
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: 6c7649b7131e3b1620112acf89867d0731d7265d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235160"
---
# <a name="cfixedstringt-class"></a>CFixedStringT-Klasse

Diese Klasse stellt einen String-Objekt mit einem festen Zeichenpuffer.

## <a name="syntax"></a>Syntax

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Parameter

*StringType*<br/>
Als die Basisklasse für das feste String-Objekt verwendet und kann `CStringT`-basiertem Typ. Beispiele hierfür sind `CString`, `CStringA`, und `CStringW`.

*t_nChars*<br/>
Die Anzahl der Zeichen im Puffer gespeichert.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Der Konstruktor für die String-Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CFixedStringT::operator =](#operator_eq)|Weist einen neuen Wert ein `CFixedStringT` Objekt.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist ein Beispiel für eine benutzerdefinierte Zeichenfolge-Klasse, die basierend auf `CStringT`. Zwar ähnlich, unterscheiden sich die beiden Klassen in der Implementierung ein. Die wichtigsten Unterschiede zwischen `CFixedStringT` und `CStringT` sind:

- Der Zeichenpuffer für die ersten, die als Teil des Objekts zugeordnet ist und Größe *T_nChars*. Dadurch wird die `CFixedString` Objekt, das ein Block zusammenhängender Arbeitsspeicher zu belegen. Jedoch, wenn der Inhalt des eine `CFixedStringT` Objekt hinausgeht *T_nChars*, der Puffer wird dynamisch zugewiesen.

- Den Zeichenpuffer für einen `CFixedStringT` Objekt ist immer die gleiche Länge ( *T_nChars*). Es gibt keine Einschränkung hinsichtlich der Größe des Puffers für `CStringT` Objekte.

- Der Speicher-Manager für `CFixedStringT` wird angepasst, dass der Freigabe einer [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) Objekt zwischen zwei oder mehr `CFixedStringT` Objekte ist nicht zulässig. `CStringT` Objekte müssen diese Einschränkung nicht.

Um mehr über die Anpassung der `CFixedStringT` und Speicherverwaltung für String-Objekte im Allgemeinen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

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
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>Parameter

*pszSrc*<br/>
Eine mit Null endende Zeichenfolge, die in diese kopiert werden `CFixedStringT` Objekt.

*strSrc*<br/>
Eine vorhandene `CFixedStringT` Objekt, das in diese kopiert werden `CFixedStringT` Objekt.

*pStringMgr*<br/>
Ein Zeiger auf den Speicher-Manager, der die `CFixedStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Speicherverwaltung für `CFixedStringT`, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Hinweise

Da die Konstruktoren der Eingabedaten in den neuen zugeordneten Speicher kopieren, sollten Sie bedenken, dass der Speicher Ausnahmen führen können. Einige dieser Konstruktoren fungieren als Funktionen für die typkonvertierung.

##  <a name="operator_eq"></a>  CFixedStringT::operator =

Initialisiert eine vorhandene `CFixedStringT` Objekt mit neuen Daten.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>Parameter

*pszSrc*<br/>
Eine mit Null endende Zeichenfolge, die in diese kopiert werden `CFixedStringT` Objekt.

*strSrc*<br/>
Eine vorhandene `CFixedStringT` in diese kopiert werden `CFixedStringT` Objekt.

### <a name="remarks"></a>Hinweise

Sie sollten bedenken, dass der Speicher Ausnahmen auftreten, wenn Sie den Zuweisungsoperator verwenden, da häufig mit neuer Speicher, zum Speichern der resultierenden zugeordnet wird `CFixedStringT` Objekt.

## <a name="see-also"></a>Siehe auch

[CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
