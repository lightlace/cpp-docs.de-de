---
title: CStrBufT-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43c460d45e0f1ce41cebd463bc3ba6b7f295d9ca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411182"
---
# <a name="cstrbuft-class"></a>CStrBufT-Klasse

Diese Klasse stellt automatische ressourcenbereinigung für `GetBuffer` und `ReleaseBuffer` aufruft, die auf einem vorhandenen `CStringT` Objekt.

## <a name="syntax"></a>Syntax

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Parameter

*TCharType*  
Der Zeichentyp, der die `CStrBufT` Klasse. Einer der folgenden Werte ist möglich:

- **Char** (für ANSI-Zeichenfolgen)

- **"wchar_t"** (für Unicode-Zeichenfolgen)

- TCHAR (nach ANSI- und Unicode-Zeichenfolgen)

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|PCXSTR|Ein Zeiger auf eine Konstante Zeichenfolge.|
|PXSTR|Ein Zeiger auf eine Zeichenfolge.|
|`StringType`|Der String-Typ, dessen Puffer wird vom spezialisierungen dieser Klassenvorlage bearbeitet werden.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|Der Konstruktor für das Zeichenfolgenobjekt für Puffer.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStrBufT::SetLength](#setlength)|Legt die Puffer Zeichenlänge des Objekts zugeordnete Zeichenfolge fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Ruft eine **const** Zeiger auf den Zeichenpuffer zugeordneten String-Objekt.|
|[CStrBufT::operator PXSTR](#operator_pxstr)|Ruft einen Zeiger auf den Zeichenpuffer zugeordneten String-Objekt ab.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|Bestimmen Sie automatisch die neue Länge der Zeichenfolge an die Version an.|
|[CStrBufT::SET_LENGTH](#set_length)|Legen Sie die Länge des Zeichenfolgenobjekts GetBuffer Zeitpunkt|

## <a name="remarks"></a>Hinweise

Diese Klasse dient als Wrapperklasse für den Ersatz der Aufrufe [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), oder [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) und `ReleaseBuffer`.

In erster Linie als Hilfsklasse entworfen `CStrBufT` bietet eine bequeme Möglichkeit für Entwickler mit den Zeichenpuffer eines Zeichenfolgenobjekts arbeiten, ohne kümmern, wie oder wann aufzurufen `ReleaseBuffer`. Dies ist möglich, da das Wrapperobjekt den Gültigkeitsbereich auf natürliche Weise bei einer Ausnahme oder mehrere Codepfade für vorhandenen verlässt; verursacht, dessen Destruktor Zeichenfolgenressource freizugeben.

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpstr.h

##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH

Bestimmen Sie automatisch die neue Länge der Zeichenfolge an die Version an.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Hinweise

Bestimmen Sie automatisch die neue Länge der Zeichenfolge an die Version an. Die Zeichenfolge muss Null-terminiert sein.

##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT

Erstellt ein Pufferobjekt.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Parameter

*str*  
Das String-Objekt, das den Puffer zugeordnet ist. In der Regel wird der Entwickler der voreingestellten Typdefinitionen verwenden `CStrBuf` (TCHAR-Variante), `CStrBufA` (**Char** Variant-Wert) und `CStrBufW` (**"wchar_t"** Variant-Wert).

*nMinLength*  
Die minimale Länge des Zeichenpuffers.

*dwFlags*  
Bestimmt, ob die Zeichenfolgenlänge automatisch bestimmt wird. Einer der folgenden Werte ist möglich:

- Zeichenfolgenlänge AUTO_LENGTH wird automatisch bestimmt, wann [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) aufgerufen wird. Die Zeichenfolge muss Null-terminiert sein. Der Standardwert.

- Zeichenfolgenlänge SET_LENGTH wird festgelegt, wenn [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) aufgerufen wird.

### <a name="remarks"></a>Hinweise

Erstellt einen Zeichenfolgenpuffer für das Objekt zugeordnete Zeichenfolge. Während der Konstruktion [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) oder [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) aufgerufen wird.

Beachten Sie, dass der Kopierkonstruktor **private**.

##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR

Greift direkt in die zugeordnete Zeichenfolge-Objekts als Zeichenfolge im C-Stil gespeicherten Zeichen auf.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeichenzeiger auf Daten von der Zeichenfolge.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um einen Zeiger auf den Zeichenpuffer einer String-Objekt zurückzugeben. Der Inhalt der String-Objekt können nicht mit diesen Zeiger nicht geändert werden.

##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR

Greift direkt in die zugeordnete Zeichenfolge-Objekts als Zeichenfolge im C-Stil gespeicherten Zeichen auf.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeichenzeiger auf Daten von der Zeichenfolge.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um einen Zeiger auf den Zeichenpuffer einer String-Objekt zurückzugeben. Der Entwickler kann es sich um den Inhalt der String-Objekt mit diesem Zeiger ändern.

##  <a name="pcxstr"></a>  CStrBufT::PCXSTR

Ein Zeiger auf eine Konstante Zeichenfolge.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

##  <a name="pxstr"></a>  CStrBufT::PXSTR

Ein Zeiger auf eine Zeichenfolge.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

##  <a name="set_length"></a>  CStrBufT::SET_LENGTH

Legen Sie die Länge des Zeichenfolgenobjekts am `GetBuffer` Zeit.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Hinweise

Legen Sie die Länge des Zeichenfolgenobjekts GetBuffer Zeitpunkt ein.

Bestimmt, ob [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) werden aufgerufen, wenn das Zeichenfolgenobjekt-Puffer erstellt wird.

##  <a name="setlength"></a>  CStrBufT::SetLength

Legt die Länge des Zeichenpuffers fest.

```
void SetLength(int nLength);
```

### <a name="parameters"></a>Parameter

*nLength*  
Die neue Länge des Zeichenpuffers von String-Objekt.

> [!NOTE]
>  Muss kleiner oder gleich der im Konstruktor der angegebenen Mindestgröße des Puffers-Länge `CStrBufT`.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können Sie legt die Länge der Zeichenfolge, die vom Pufferobjekt dargestellt.

##  <a name="stringtype"></a>  CStrBufT::StringType

Der String-Typ, dessen Puffer wird vom spezialisierungen dieser Klassenvorlage bearbeitet werden.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Hinweise

`TCharType` Der Zeichentyp ist verwendet werden, die Klassenvorlage spezialisiert werden kann.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

