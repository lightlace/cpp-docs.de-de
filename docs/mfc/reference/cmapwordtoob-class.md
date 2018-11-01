---
title: CMapWordToOb-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMapWordToOb
- AFXCOLL/CMapWordToOb
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
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
ms.openlocfilehash: 3fcd3bd59b406d19c57335702e7059feab6a754c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513853"
---
# <a name="cmapwordtoob-class"></a>CMapWordToOb-Klasse

Unterstützt Zuordnungen von `CObject` -Zeigern mit 16-Bit-Wörtern als Schlüssel.

## <a name="syntax"></a>Syntax

```
class CMapWordToOb : public CObject
```

## <a name="members"></a>Member

Die Memberfunktionen der `CMapWordToOb` ähneln den Memberfunktionen der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CMapStringToOb`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CString` oder **const** Zeiger auf **Char** als Funktionsparameter oder Rückgabewert, ersetzen Sie WORD.

`BOOL CMapStringToOb::Lookup( const char* <key>,` CObject* & <rValue> ) const;'

Beispielsweise übersetzt zu

`BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`

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
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Berechnet den Hashwert eines angegebenen Schlüssels.|
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Initialisiert die Hashtabelle.|
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Testet, ob die Karten im Detail leere Bedingung (keine Elemente).|
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Sucht einen void-Zeiger auf Grundlage des Schlüssels void-Zeiger. Der Wert des Zeigers, nicht in der Entität, die, auf die verwiesen, wird für die beim Schlüsselvergleich verwendet.|
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Gibt einen Verweis auf den zugeordneten Schlüssel für das angegebene Schlüssel-Wert zurück.|
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Entfernt alle Elemente aus dieser Zuordnung an.|
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Fügt ein Element in der Karte; ersetzt ein vorhandenes Element an, wenn ein passender Schlüssel gefunden wird.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersetzung für `SetAt`.|

## <a name="remarks"></a>Hinweise

`CMapWordToOb` enthält das IMPLEMENT_SERIAL-Makro, um Serialisierung und die Sicherung der Elemente zu unterstützen. Jedes Element der Reihe nach serialisiert, wenn eine Zuordnung in ein Archiv, entweder mit den überladenen einfügen gespeichert ist ( **<<**) Operator oder mit der `Serialize` Member-Funktion.

Wenn Sie eine Sicherung von einzelnen WORD - benötigen `CObject` Elemente müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.

Wenn eine `CMapWordToOb` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die `CObject` zeigenden Elemente entfernt werden. Die Objekte, die auf die verwiesen wird durch die `CObject` Zeigern werden nicht gelöscht.

Weitere Informationen zu `CMapWordToOb`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CMapWordToOb`

## <a name="requirements"></a>Anforderungen

**Header:** afxcoll.h

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

