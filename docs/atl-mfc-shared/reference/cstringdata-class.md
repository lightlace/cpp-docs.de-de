---
title: CStringData-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
dev_langs:
- C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: effc4166fa25cec03ea62a5dd35a5396d2d2a3f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419788"
---
# <a name="cstringdata-class"></a>CStringData-Klasse

Diese Klasse stellt die Daten von einem String-Objekt.

## <a name="syntax"></a>Syntax

```
struct CStringData
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|["AddRef"](#addref)|Inkrementiert den Verweiszähler des String-Objekts.|
|[data](#data)|Ruft die Zeichendaten eines Zeichenfolgenobjekts ab.|
|[IsLocked](#islocked)|Bestimmt, ob der Puffer des zugeordneten String-Objekt gesperrt ist.|
|[IsShared](#isshared)|Bestimmt, ob der Puffer des Objekts zugeordnete Zeichenfolge zurzeit freigegeben wird.|
|[Sperre](#lock)|Sperrt den Puffer mit den zugehörigen String-Objekt.|
|[Version](#release)|Gibt das angegebene String-Objekt frei.|
|[Entsperren](#unlock)|Entsperrt den Puffer mit den zugehörigen String-Objekt.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[nAllocLength](#nalloclength)|Länge der zugeordneten Daten in `XCHAR`s (ohne abschließende Null-Zeichen)|
|[nDataLength](#ndatalength)|Länge der aktuell verwendeten Daten in `XCHAR`s (ohne abschließende Null-Zeichen)|
|[nRefs](#nrefs)|Der aktuelle Verweiszähler des Objekts.|
|[pStringMgr](#pstringmgr)|Ein Zeiger auf die Zeichenfolgen-Manager von diesem String-Objekt.|

## <a name="remarks"></a>Hinweise

Diese Klasse sollte nur von Entwicklern zum Implementieren von benutzerdefinierten Zeichenfolgen-Manager verwendet werden. Weitere Informationen zu benutzerdefinierten Zeichenfolgen-Manager, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

Diese Klasse kapselt die verschiedenen Typen von Informationen und Daten im Zusammenhang mit einem höheren String-Objekt, z. B. [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), oder [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) -Objekte. Jede höhere String-Objekt enthält einen Zeiger auf die zugehörigen `CStringData` Objekt, können mehrere String-Objekte, um auf das gleiche Zeichenfolgenobjekt für Daten zu verweisen. Diese Beziehung wird durch die Anzahl der Verweise dargestellt (`nRefs`) von der `CStringData` Objekt.

> [!NOTE]
>  In bestimmten Fällen eine String-Datentyp (z. B. `CFixedString`) ein Datenobjekt für die Zeichenfolge mit mehr als eine höhere String-Objekt wird nicht gemeinsam nutzen. Weitere Informationen hierzu finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

Diese Daten besteht aus:

- Der Speicher-Manager (des Typs [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) der Zeichenfolge.

- Die aktuelle Länge ( [nDataLength](#ndatalength)) der Zeichenfolge.

- Die zugewiesene Länge ( [nAllocLength](#nalloclength)) der Zeichenfolge. Zur Verbesserung der Leistung kann dies die aktuelle Länge der Zeichenfolge unterscheiden

- Die aktuelle Verweisanzahl ( [nRefs](#nrefs)) von der `CStringData` Objekt. Dieser Wert wird verwendet, bei der Bestimmung, wie viele String-Objekte den gleichen gemeinsam `CStringData` Objekt.

- Welches Zeichen tatsächlich Puffers ( [Daten](#data)) der Zeichenfolge.

   > [!NOTE]
   > Der tatsächlichen Zeichenpuffer String-Objekt wird von der Zeichenfolge-Manager zugeordnet und wird angefügt, um die `CStringData` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpstr.h

##  <a name="addref"></a>  CStringData::AddRef

Inkrementiert den Verweiszähler des String-Objekt.

```
void AddRef() throw();
```

### <a name="remarks"></a>Hinweise

Inkrementiert den Verweiszähler des String-Objekt.

> [!NOTE]
>  Rufen Sie diese Methode nicht auf eine Zeichenfolge mit einer negativen verweiszählung, da eine negative Anzahl gibt an, dass der Zeichenfolgenpuffer gesperrt ist.

##  <a name="data"></a>  CStringData::data

Gibt einen Zeiger auf den Zeichenpuffer eines Zeichenfolgenobjekts zurück.

```
void* data() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Zeichenpuffer String-Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den aktuellen Zeichenpuffer zugeordneten String-Objekt zurück.

> [!NOTE]
>  Dieser Puffer ist nicht zugeordnet, durch die `CStringData` Objekt aber von der Zeichenfolge-Manager bei Bedarf. Wenn zugeordnet, wird der Puffer auf das Datenobjekt Zeichenfolge angefügt.

##  <a name="islocked"></a>  CStringData::IsLocked

Bestimmt, ob es sich bei der Zeichenpuffer gesperrt ist.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Puffer gesperrt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um zu bestimmen, ob der Puffer aus Zeichen eines Zeichenfolgenobjekts derzeit gesperrt ist.

##  <a name="isshared"></a>  CStringData::IsShared

Bestimmt, ob es sich bei der Zeichenpuffer gemeinsam verwendet wird.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Puffer freigegeben ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um zu bestimmen, ob es sich bei der Zeichenpuffer ein Zeichenfolge-Datenobjekt derzeit von mehreren Zeichenfolgenobjekte gemeinsam verwendet wird.

##  <a name="lock"></a>  CStringData::Lock

Sperrt den Zeichenpuffer zugeordneten String-Objekt.

```
void Lock() throw();
```

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können Sperren des Puffers Zeichen eines Zeichenfolgenobjekts Daten. Sperren und entsperren wird verwendet, wenn der Entwickler direkter Zugriff auf den Zeichenpuffer erforderlich ist. Ein gutes Beispiel für die Sperre wird veranschaulicht, durch die [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) Methoden `CSimpleStringT`.

> [!NOTE]
>  Nur kann ein Zeichenpuffer gesperrt werden, falls der Puffer in höhere Zeichenfolgenobjekte nicht freigegeben wird.

##  <a name="nalloclength"></a>  CStringData::nAllocLength

Die Länge des Zeichenpuffers zugewiesenen.

```
int nAllocLength;
```

### <a name="remarks"></a>Hinweise

Speichert die Länge des zugeordneten Puffers in `XCHAR`s (ohne abschließenden Nullzeichen).

##  <a name="ndatalength"></a>  CStringData::nDataLength

Aktuelle Länge der String-Objekt.

```
int nDataLength;
```

### <a name="remarks"></a>Hinweise

Speichert die Länge der aktuell verwendeten Daten in `XCHAR`s (ohne abschließenden Nullzeichen).

##  <a name="nrefs"></a>  CStringData::nRefs

Der Verweiszähler des String-Objekts.

```
long nRefs;
```

### <a name="remarks"></a>Hinweise

Speichert den Verweiszähler des String-Objekts. Diese Zahl gibt an, die Anzahl der höheren String-Objekten, die das String-Objekt zugeordnet sind. Ein negativer Wert gibt an, dass das Datenobjekt für die Zeichenfolge zurzeit gesperrt ist.

##  <a name="pstringmgr"></a>  CStringData::pStringMgr

Der Speicher-Manager, der das zugeordnete String-Objekt.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>Hinweise

Speichert die Speicher-Manager für das Objekt zugeordnete Zeichenfolge. Weitere Informationen zu Speicher-Manager und Zeichenfolgen, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="release"></a>  CStringData::Release

Dekrementiert den Verweiszähler des String-Objekts.

```
void Release() throw();
```

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können dekrementiert den Verweiszähler Freigeben der `CStringData` Struktur, wenn der Verweiszähler null erreicht. Dies erfolgt häufig, wenn ein Zeichenfolgenobjekt, das gelöscht wird, und muss daher nicht mehr auf das String-Objekt zu verweisen.

Der folgende Code würde aufrufen, z. B. `CStringData::Release` für das String-Objekt zugeordneten `str1`:

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

##  <a name="unlock"></a>  CStringData::Unlock

Entsperrt den Zeichenpuffer zugeordneten String-Objekt.

```
void Unlock() throw();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den Puffer aus Zeichen eines Zeichenfolgenobjekts Daten zu entsperren. Nachdem Sie ein Puffer entsperrt ist, ist freigegeben, und Verweis gezählt werden kann.

> [!NOTE]
>  Jeder Aufruf von `Lock` muss durch einen entsprechenden Aufruf übereinstimmen `Unlock`.

Sperren und entsperren wird verwendet, wenn der Entwickler muss sicherstellen, dass die Daten der Zeichenfolge nicht freigegeben werden. Ein gutes Beispiel für die Sperre wird veranschaulicht, durch die [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) und [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) Methoden `CSimpleStringT`.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

