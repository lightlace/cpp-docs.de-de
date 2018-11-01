---
title: CTypedPtrMap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: f09b44c5b898ee0d583db45ca63ee67c3d1c5b47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494860"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap-Klasse

Stellt einen typsicheren Wrapper für Objekte der Zeigerzuordnungsklassen `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`und `CMapStringToPtr`bereit.

## <a name="syntax"></a>Syntax

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Parameter

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger Map-Klasse; muss eine Zeiger-Map-Klasse ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, oder `CMapStringToPtr`).

*KEY*<br/>
Die Klasse des Objekts als Schlüssel für die Karte verwendet.

*WERT*<br/>
Die Klasse des Objekts in der Zuordnung gespeichert.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Ruft das nächste Element durchlaufen werden können.|
|[CTypedPtrMap::Lookup](#lookup)|Gibt eine `KEY` basierend auf einer `VALUE`.|
|[CTypedPtrMap::RemoveKey](#removekey)|Entfernt ein Element mit einem Schlüssel angegeben.|
|[CTypedPtrMap::SetAt](#setat)|Fügt ein Element in der Karte; ersetzt ein vorhandenes Element an, wenn ein passender Schlüssel gefunden wird.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CTypedPtrMap::operator]](#operator_at)|Fügt ein Element in der Zuordnung.|

## <a name="remarks"></a>Hinweise

Bei Verwendung von `CTypedPtrMap`, die Typprüfung C++-Funktion hilft, Fehler aufgrund nicht übereinstimmender Zeigertypen zu vermeiden.

Da alle `CTypedPtrMap` Funktionen werden Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.

Weitere Informationen zur Verwendung von `CTypedPtrMap`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [vorlagenbasierte Klassen](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Anforderungen

**Header:** afxtempl.h

##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc

Ruft das kartenelement auf `rNextPosition`, und aktualisiert dann `rNextPosition` zum Verweisen auf das nächste Element in der Zuordnung.

```
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parameter

*rposition zurück*<br/>
Gibt einen Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetNextAssoc` oder `BASE_CLASS` **:: GetStartPosition** aufrufen.

*KEY*<br/>
Template-Parameter, die den Typ der Map-Schlüssel angibt.

*rKey*<br/>
Gibt den zurückgegebenen Schlüssel des Elements abgerufen.

*WERT*<br/>
Der Vorlagenparameter, die den Typ der Werte von der Zuordnung angibt.

*rValue*<br/>
Gibt den Rückgabewert des abgerufenen Elements an.

### <a name="remarks"></a>Hinweise

Diese Funktion ist besonders hilfreich für die Iteration durch alle Elemente in der Zuordnung. Beachten Sie, dass die Sequenz Position nicht unbedingt identisch mit der Sequenz von Schlüssel-Wert ist.

Ist das abgerufene Element das letzte in der Zuordnung klicken Sie dann den neuen Wert des `rNextPosition` auf NULL festgelegt ist.

Diese Inlinefunktion ruft `BASE_CLASS` **:: GetNextAssoc**.

##  <a name="lookup"></a>  CTypedPtrMap::Lookup

`Lookup` verwendet einen Hashalgorithmus auf um das kartenelement schnell mit einem Schlüssel zu finden, die genau übereinstimmt.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parameter

*BASE_CLASS*<br/>
Template-Parameter, die die Basisklasse dieser Map-Klasse angeben.

*key*<br/>
Der Schlüssel des Elements, das gesucht werden sollen.

*WERT*<br/>
Template-Parameter, die den Typ des in dieser Zuordnung gespeicherten Werte angibt.

*rValue*<br/>
Gibt den Rückgabewert des abgerufenen Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Element gefunden wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Inlinefunktion ruft `BASE_CLASS` **:: Lookup**.

##  <a name="operator_at"></a>  CTypedPtrMap::operator]

Dieser Operator kann nur auf der linken Seite einer zuweisungsanweisung (ein l-Wert) verwendet werden.

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Parameter

*WERT*<br/>
Template-Parameter, die den Typ des in dieser Zuordnung gespeicherten Werte angibt.

*BASE_CLASS*<br/>
Template-Parameter, die die Basisklasse dieser Map-Klasse angeben.

*key*<br/>
Der Schlüssel des Elements, das gesucht werden oder in der Zuordnung erstellt werden.

### <a name="remarks"></a>Hinweise

Wenn kein Map-Element mit dem angegebenen Schlüssel vorhanden ist, wird ein neues Element erstellt. Es gibt keine "rechts" (r), die dieser Operator entspricht, da es sich bei besteht die Möglichkeit, die ein Schlüssel in der Zuordnung nicht gefunden werden kann. Verwenden der `Lookup` Member-Funktion für Abruf von Listenelementen.

##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey

Diese Memberfunktion ruft `BASE_CLASS` **:: RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Parameter

*KEY*<br/>
Template-Parameter, die den Typ der Map-Schlüssel angibt.

*key*<br/>
Der Schlüssel für das Element entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Eintrag gefunden und erfolgreich entfernt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

##  <a name="setat"></a>  CTypedPtrMap::SetAt

Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.

```
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Parameter

*KEY*<br/>
Template-Parameter, die den Typ der Map-Schlüssel angibt.

*key*<br/>
Gibt den Wert des der NewValue Schlüssels an.

*newValue*<br/>
Gibt den Objektzeiger, das der Wert des neuen Elements an.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr-Klasse](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord-Klasse](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr-Klasse](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr-Klasse](../../mfc/reference/cmapstringtoptr-class.md)
