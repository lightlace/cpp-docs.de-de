---
title: CMapStringToString-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CMapStringToString [MFC], CPair
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
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 404796a4ff51ef821b4d5ce805b8564ab2471d25
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677317"
---
# <a name="cmapstringtostring-class"></a>CMapStringToString-Klasse

Unterstützt Zuordnungen von `CString` -Objekten mit `CString` -Objekten als Schlüssel.

## <a name="syntax"></a>Syntax

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Member

Die Memberfunktionen der `CMapStringToString` ähneln den Memberfunktionen der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CMapStringToOb`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CObject` Zeiger als Rückgabewert oder "output"-Parameter Funktion ersetzen einen Zeiger auf **Char**. Immer dort, wo ein `CObject` Zeiger als Parameter "input"-Funktion, ersetzen Sie durch einen Zeiger auf **Char**.

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

Beispielsweise übersetzt zu

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

### <a name="public-structures"></a>Öffentliche Strukturen

|name|Beschreibung|
|----------|-----------------|
|[CMapStringToString::CPair](#cpair)|Eine geschachtelte Struktur mit einem Schlüssel-Wert und der Wert des Objekts zugeordnete Zeichenfolge.|

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
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Ruft einen Zeiger auf dem erste `CString` in der Zuordnung.|
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Ruft einen Zeiger auf der nächste `CString` durchlaufen werden können.|
|[CMapStringToString::PLookup](#plookup)|Gibt einen Zeiger auf eine `CString` , dessen Wert mit den angegebenen Wert übereinstimmt.|
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Entfernt alle Elemente aus dieser Zuordnung an.|
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Fügt ein Element in der Karte; ersetzt ein vorhandenes Element an, wenn ein passender Schlüssel gefunden wird.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersetzung für `SetAt`.|

## <a name="remarks"></a>Hinweise

`CMapStringToString` enthält die `IMPLEMENT_SERIAL` Makro, um Serialisierung und die Sicherung der Elemente zu unterstützen. Jedes Element der Reihe nach serialisiert, wenn eine Zuordnung in ein Archiv, entweder mit den überladenen einfügen gespeichert ist ( **<<**) Operator oder mit der `Serialize` Member-Funktion.

Wenn Sie eine Sicherung einzelner benötigen `CString` -  `CString` Elemente müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.

Wenn eine `CMapStringToString` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die `CString` Objekte werden nach Bedarf entfernt.

Weitere Informationen zu `CMapStringToString`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Anforderungen

**Header:** afxcoll.h

##  <a name="cpair"></a>  CMapStringToString::CPair

Enthält ein Schlüssel-Wert und den Wert der zugehörigen String-Objekt.

### <a name="remarks"></a>Hinweise

Dies ist eine geschachtelte Struktur in Klasse [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).

Die Struktur besteht aus zwei Feldern:

- `key` Der tatsächliche Wert, der den Typ des Schlüssels.

- `value` Der Wert des zugeordneten Objekts.

Es wird verwendet, um die Rückgabewerte aus speichern [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), und [CMapStringToString::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Beispiel

  Ein Beispiel der Nutzung finden Sie im Beispiel für [CMapStringToString::PLookup](#plookup).

##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc

Gibt den ersten Eintrag, der das Map-Objekt zurück.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den ersten Eintrag in der Karte; finden Sie unter [CMapStringToString::CPair](#cpair). Wenn die Zuordnung leer ist, ist der Wert NULL.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um einen Zeiger mit das erste Element im Map-Objekt zurückzugeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc

Ruft das Map-Element verweist *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Parameter

*pAssoc*<br/>
Verweist auf einen Eintrag für die Zuordnung von einem vorherigen zurückgegebene [PGetNextAssoc](#pgetnextassoc) oder [PGetFirstAssoc](#pgetfirstassoc) aufrufen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den nächsten Eintrag in der Karte; finden Sie unter [CMapStringToString::CPair](#cpair). Wenn das Element das letzte in der Zuordnung ist, ist der Wert NULL.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum iterieren durch alle Elemente in der Zuordnung. Rufen Sie das erste Element mit einem Aufruf von `PGetFirstAssoc` und durchlaufen Sie dann auf der Karte mit aufeinander folgende Aufrufe von `PGetNextAssoc`.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).

##  <a name="plookup"></a>  CMapStringToString::PLookup

Sucht nach der zu einem angegebenen Schlüssel zugeordnete Wert.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Ein Zeiger auf den Schlüssel für das Element, nach dem gesucht werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den angegebenen Schlüssel.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode für ein kartenelement mit einem Schlüssel zu suchen, die mit den angegebenen Schlüssel übereinstimmt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

