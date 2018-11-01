---
title: CMap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: 3991ae4c7455aa8e6eb377112cb89c057e9567e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627317"
---
# <a name="cmap-class"></a>CMap-Klasse

Eine Wörterbuchauflistungsklasse, die eindeutigen Schlüsseln Werte zuordnet.

## <a name="syntax"></a>Syntax

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Parameter

*KEY*<br/>
Die Klasse des Objekts als Schlüssel für die Karte verwendet.

*ARG_KEY*<br/>
Zum Datentyp *Schlüssel* Argumente, in der Regel einen Verweis auf *Schlüssel*.

*WERT*<br/>
Die Klasse des Objekts in der Zuordnung gespeichert.

*ARG_VALUE*<br/>
Zum Datentyp *Wert* Argumente, in der Regel einen Verweis auf *Wert*.

## <a name="members"></a>Member

### <a name="public-structures"></a>Öffentliche Strukturen

|name|Beschreibung|
|----------|-----------------|
|[CMap::CPair](#cpair)|Eine geschachtelte Struktur mit einem Schlüssel-Wert und der Wert des zugeordneten Objekts.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMap::CMap](#cmap)|Erstellt eine Auflistung, die Schlüsseln Werte zuordnet.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMap::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|
|[CMap::GetHashTableSize](#gethashtablesize)|Gibt die Anzahl der Elemente in der Hashtabelle zurück.|
|[CMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|
|[CMap::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Zuordnung zurück.|
|[CMap::GetStartPosition](#getstartposition)|Gibt die Position des ersten Elements zurück.|
|[CMap::InitHashTable](#inithashtable)|Initialisiert die Hashtabelle und eine Größe angegeben.|
|[CMap::IsEmpty](#isempty)|Testet, ob die Karten im Detail leere Bedingung (keine Elemente).|
|[CMap::Lookup](#lookup)|Sucht nach der zu einem angegebenen Schlüssel zugeordnete Wert.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Gibt einen Zeiger auf das erste Element zurück.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|Ruft einen Zeiger auf das nächste Element durchlaufen werden können.|
|[CMap::PLookup](#plookup)|Gibt einen Zeiger auf einen Schlüssel, dessen Wert dem angegebenen Wert übereinstimmt.|
|[CMap::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Zuordnung an.|
|[CMap::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|
|[CMap::SetAt](#setat)|Fügt ein Element in der Karte; ersetzt ein vorhandenes Element an, wenn ein passender Schlüssel gefunden wird.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CMap::operator]](#operator_at)|Fügt ein Element in der Zuordnung – Operator Ersetzung für `SetAt`.|

## <a name="remarks"></a>Hinweise

Nachdem Sie die Schlüssel-Wert-Paar (Element) in die Zuordnung eingefügt haben, können effizient abrufen oder löschen das Paar mit dem Schlüssel für den Zugriff. Sie können auch alle Elemente in der Zuordnung durchlaufen.

Eine Variable vom Typ POSITION wird für den alternativen Zugriff auf Einträge verwendet. Sie können eine POSITION einen Eintrag "Speichern" und zum iterieren durch die Zuordnung verwenden. Sie denken möglicherweise, dass es sich bei dieser Iteration sequenzielle von Schlüssel-Wert ist; Es ist nicht. Die Reihenfolge der abgerufenen Elemente ist unbestimmt.

Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CMap` Klasse. Finden Sie unter [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) in Abschnitt Makros und Globals der **MFC-Referenz**.

`CMap` überschreibt [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) um Serialisierung und die Sicherung der Elemente zu unterstützen. Wenn eine Zuordnung mit einem Archiv gespeichert ist `Serialize`, jedem kartenelement der Reihe nach serialisiert. Die standardmäßige Implementierung der `SerializeElements` Hilfsfunktion ist eine bitweise schreiben. Für Informationen zur Serialisierung der Auflistungselemente Zeiger abgeleitet `CObject` oder andere benutzerdefinierte Typen, finden Sie unter [Vorgehensweise: Erstellen einer typsicheren Auflistung](../../mfc/how-to-make-a-type-safe-collection.md).

Wenn Sie ein Speicherabbild zu Diagnosezwecken der einzelnen Elemente in der Zuordnung (die Schlüssel und Werte) benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.

Wenn eine `CMap` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, die Schlüssel und Werte werden entfernt.

Map-klassenableitung ist ähnlich wie die Ableitung der Liste. Finden Sie im Artikel [Sammlungen](../../mfc/collections.md) für die Ableitung einer Klasse spezielle Liste veranschaulicht.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Anforderungen

**Header:** afxtempl.h

##  <a name="cmap"></a>  CMap::CMap

Erstellt eine leere Zuordnung.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Gibt die Granularität der speicherbelegung zum Erweitern der Zuordnung.

### <a name="remarks"></a>Hinweise

Mit zunehmender die Karte wird in Einheiten von Arbeitsspeicher zugeordnet *nBlockSize* Einträge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

##  <a name="cpair"></a>  CMap::CPair

Enthält ein Schlüssel-Wert und der Wert des zugeordneten Objekts.

### <a name="remarks"></a>Hinweise

Dies ist eine geschachtelte Struktur in Klasse [CMap](../../mfc/reference/cmap-class.md).

Die Struktur besteht aus zwei Feldern:

- `key` Der tatsächliche Wert, der den Typ des Schlüssels.

- `value` Der Wert des zugeordneten Objekts.

Es wird verwendet, um die Rückgabewerte aus speichern [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), und [CMap::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Beispiel

Ein Beispiel der Nutzung finden Sie im Beispiel für [CMap::PLookup](#plookup).

##  <a name="getcount"></a>  CMap::GetCount

Ruft die Anzahl der Elemente in der Zuordnung ab.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::Lookup](#lookup).

##  <a name="gethashtablesize"></a>  CMap::GetHashTableSize

Bestimmt die Anzahl der Elemente in der Hashtabelle für die Karte an.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der Hashtabelle.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

##  <a name="getnextassoc"></a>  CMap::GetNextAssoc

Ruft das kartenelement auf `rNextPosition`, und aktualisiert dann `rNextPosition` zum Verweisen auf das nächste Element in der Zuordnung.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parameter

*rNextPosition*<br/>
Gibt einen Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetNextAssoc` oder `GetStartPosition` aufrufen.

*KEY*<br/>
Der Vorlagenparameter, die den Typ des Schlüssels mit der Karte.

*rKey*<br/>
Gibt den zurückgegebenen Schlüssel des Elements abgerufen.

*WERT*<br/>
Der Vorlagenparameter, der den Typ des Werts von der Karte angibt.

*rValue*<br/>
Gibt den Rückgabewert des abgerufenen Elements an.

### <a name="remarks"></a>Hinweise

Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht unbedingt identisch mit der Sequenz von Schlüssel-Wert ist.

Ist das abgerufene Element das letzte in der Zuordnung klicken Sie dann den neuen Wert des *rNextPosition* auf NULL festgelegt ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::SetAt](#setat).

##  <a name="getsize"></a>  CMap::GetSize

Gibt die Anzahl der Elemente zurück.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der Zuordnung.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Abrufen der Anzahl der Elemente in der Zuordnung.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="getstartposition"></a>  CMap::GetStartPosition

Startet eine Iteration für die Zuordnung durch Rückgabe eines Werts von POSITION, die übergeben werden kann eine `GetNextAssoc` aufrufen.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Positionswert, der Position des ersten Durchlaufen der Zuordnung angibt; oder NULL, wenn die Zuordnung leer ist.

### <a name="remarks"></a>Hinweise

Die Sequenz der Iteration ist nicht vorhersagbar; der "ersten Element in der Zuordnung" hat daher keine besondere Bedeutung.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::SetAt](#setat).

##  <a name="inithashtable"></a>  CMap::InitHashTable

Initialisiert die Hashtabelle.

```
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Parameter

*hashSize*<br/>
Anzahl von Einträgen in der Hashtabelle.

*bAllocNow*<br/>
Bei "true", weist die Hashtabelle, bei der Initialisierung an; Andernfalls wird in der Tabelle zugeordnet, wenn erforderlich.

### <a name="remarks"></a>Hinweise

Für eine optimale Leistung sollte die Hashtabellengröße eine Primzahl. Um Konflikte zu minimieren, sollte die Größe etwa 20 Prozent größer als das größte erwartete DataSet.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::Lookup](#lookup).

##  <a name="isempty"></a>  CMap::IsEmpty

Bestimmt, ob die Zuordnung leer ist.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn diese Zuordnung enthält keine Elemente; andernfalls 0.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::RemoveAll](#removeall).

##  <a name="lookup"></a>  CMap::Lookup

Sucht nach der zu einem angegebenen Schlüssel zugeordnete Wert.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parameter

*ARG_KEY*<br/>
Angabe des Typs der Template-Parameter der *Schlüssel* Wert.

*key*<br/>
Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.

*WERT*<br/>
Gibt den Typ des Werts, der gesucht werden sollen.

*rValue*<br/>
Empfängt den Wert der nachgeschlagenen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

`Lookup` verwendet einen Hashalgorithmus auf um das kartenelement schnell mit einem Schlüssel zu finden, die mit den angegebenen Schlüssel übereinstimmt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="operator_at"></a>  CMap::operator]

Einen geeigneten Ersatz für die `SetAt` Member-Funktion.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Parameter

*WERT*<br/>
Template-Parameter, die den Typ des Map-Werts angibt.

*ARG_KEY*<br/>
Der Vorlagenparameter, der der Typ des Werts des Schlüssels angibt.

*key*<br/>
Der Schlüssel zum Abrufen des Werts aus der Zuordnung verwendet wird.

### <a name="remarks"></a>Hinweise

Es kann daher nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden. Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt.

Es gibt keine "rechts" (r), die dieser Operator entspricht, da es sich bei besteht die Möglichkeit, die ein Schlüssel in der Zuordnung nicht gefunden werden kann. Verwenden der `Lookup` Member-Funktion für Abruf von Listenelementen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::Lookup](#lookup).

##  <a name="pgetfirstassoc"></a>  CMap::PGetFirstAssoc

Gibt den ersten Eintrag, der das Map-Objekt zurück.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den ersten Eintrag in der Karte; finden Sie unter [CMap::CPair](#cpair). Wenn die Zuordnung keine Einträge enthält, ist der Wert NULL.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um einen Zeiger mit das erste Element im Map-Objekt zurückzugeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

##  <a name="pgetnextassoc"></a>  CMap::PGetNextAssoc

Ruft das Map-Element verweist *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Parameter

*pAssocRet*<br/>
Verweist auf einen Eintrag für die Zuordnung von einem vorherigen zurückgegebene [PGetNextAssoc](#pgetnextassoc) oder [CMap::PGetFirstAssoc](#pgetfirstassoc) aufrufen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den nächsten Eintrag in der Karte; finden Sie unter [CMap::CPair](#cpair). Wenn das Element das letzte in der Zuordnung ist, ist der Wert NULL.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum iterieren durch alle Elemente in der Zuordnung. Rufen Sie das erste Element mit einem Aufruf von `PGetFirstAssoc` und durchlaufen Sie dann auf der Karte mit aufeinander folgende Aufrufe von `PGetNextAssoc`.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::PGetFirstAssoc](#pgetfirstassoc).

##  <a name="plookup"></a>  CMap::PLookup

Sucht den Wert, der einem angegebenen Schlüssel zugeordnet.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüssel für das Element, nach dem gesucht werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Schlüsselstruktur; finden Sie unter [CMap::CPair](#cpair). Wenn keine Übereinstimmung gefunden wird, `CMap::PLookup` gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode für ein kartenelement mit einem Schlüssel zu suchen, die mit den angegebenen Schlüssel übereinstimmt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

##  <a name="removeall"></a>  CMap::RemoveAll

Entfernt alle Werte aus dieser Zuordnung durch Aufrufen der Hilfsfunktion für das globale `DestructElements`.

```
void RemoveAll();
```

### <a name="remarks"></a>Hinweise

Die Funktion funktioniert ordnungsgemäß, wenn die Zuordnung bereits leer ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

##  <a name="removekey"></a>  CMap::RemoveKey

Durchsucht den Map-Eintrag, der dem angegebenen Schlüssel entspricht; Klicken Sie dann, wenn der Schlüssel gefunden wird, entfernt der Eintrag.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Parameter

*ARG_KEY*<br/>
Der Vorlagenparameter, der der Typ des Schlüssels angibt.

*key*<br/>
Der Schlüssel für das Element entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `DestructElements` Hilfsfunktion wird verwendet, um den Eintrag zu entfernen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CMap::SetAt](#setat).

##  <a name="setat"></a>  CMap::SetAt

Hauptsächlich als Mittel zum Einfügen eines Elements in einer Zuordnung.

```
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Parameter

*ARG_KEY*<br/>
Angabe des Typs der Template-Parameter der *Schlüssel* Parameter.

*key*<br/>
Gibt den Schlüssel des neuen Elements.

*ARG_VALUE*<br/>
Angabe des Typs der Template-Parameter der *NewValue* Parameter.

*newValue*<br/>
Gibt den Wert des neuen Elements.

### <a name="remarks"></a>Hinweise

Der Schlüssel wird zuerst gesucht. Wenn der Schlüssel, gefunden wird und klicken Sie dann der entsprechende Wert geändert wird, Andernfalls wird ein neues Schlüssel-Wert-Paar erstellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
