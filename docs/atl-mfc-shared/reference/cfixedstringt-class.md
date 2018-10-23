---
title: CFixedStringT-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: d9f48ffb9cad787159a40a58d85e6bff5dacc475
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808250"
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
|[CFixedStringT::operator =](#eq)|Weist einen neuen Wert ein `CFixedStringT` Objekt.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist ein Beispiel für eine benutzerdefinierte Zeichenfolge-Klasse, die basierend auf `CStringT`. Zwar sehr ähnlich, unterscheiden sich die beiden Klassen in der Implementierung ein. Die wichtigsten Unterschiede zwischen `CFixedStringT` und `CStringT` sind:

- Der Zeichenpuffer für die ersten, die als Teil des Objekts zugeordnet ist und Größe *T_nChars*. Dadurch wird die `CFixedString` Objekt, das ein Block zusammenhängender Arbeitsspeicher zu belegen. Jedoch, wenn der Inhalt des eine `CFixedStringT` Objekt hinausgeht *T_nChars*, der Puffer wird dynamisch zugewiesen.

- Den Zeichenpuffer für einen `CFixedStringT` Objekt ist immer die gleiche Länge ( *T_nChars*). Es gibt keine Einschränkung hinsichtlich der Größe des Puffers für `CStringT` Objekte.

- Der Speicher-Manager für `CFixedStringT` wird angepasst, dass der Freigabe einer [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) Objekt zwischen zwei oder mehr `CFixedStringT` Objectsis nicht zulässig. `CStringT` Objekte müssen diese Einschränkung nicht.

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
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```

### <a name="parameters"></a>Parameter

*psz*<br/>
Eine mit Null endende Zeichenfolge, die in diese kopiert werden `CFixedStringT` Objekt.

*str*<br/>
Eine vorhandene `CFixedStringT` Objekt, das in diese kopiert werden `CFixedStringT` Objekt.

*pStringMgr*<br/>
Ein Zeiger auf den Speicher-Manager, der die `CFixedStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Speicherverwaltung für `CFixedStringT`, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Hinweise

Da die Konstruktoren der Eingabedaten in den neuen zugeordneten Speicher kopieren, sollten Sie bedenken, dass der Speicher Ausnahmen führen können. Beachten Sie, dass einige dieser Konstruktoren als Funktionen für die typkonvertierung fungieren.

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

*str*<br/>
Eine mit Null endende Zeichenfolge, die in diese kopiert werden `CFixedStringT` Objekt.

*psz*<br/>
Eine vorhandene `CFixedStringT` in diese kopiert werden `CFixedStringT` Objekt.

### <a name="remarks"></a>Hinweise

Sie sollten bedenken, dass der Speicher Ausnahmen auftreten, wenn Sie den Zuweisungsoperator verwenden, da häufig mit neuer Speicher, zum Speichern der resultierenden zugeordnet wird `CFixedStringT` Objekt.

## <a name="see-also"></a>Siehe auch

[CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

