---
title: CComUnkArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cab0ea4ecf4bfabede365b9e0fbc9d4a02e2515
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057449"
---
# <a name="ccomunkarray-class"></a>CComUnkArray-Klasse

Diese Klasse speichert `IUnknown` Zeiger, die als Parameter verwendet werden soll, und die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.

## <a name="syntax"></a>Syntax

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>Parameter

*nMaxSize*<br/>
Die maximale Anzahl von `IUnknown` Zeigern, die im statischen Array gespeichert werden können.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComUnkArray::Add](#add)|Rufen Sie diese Methode zum Hinzufügen einer `IUnknown` Zeiger auf das Array.|
|[CComUnkArray::begin](#begin)|Gibt einen Zeiger auf das erste `IUnknown` Zeiger in der Auflistung.|
|[CComUnkArray::end](#end)|Gibt einen Zeiger auf eine Stelle hinter dem letzten `IUnknown` Zeiger in der Auflistung.|
|[CComUnkArray::GetCookie](#getcookie)|Rufen Sie diese Methode, um das Cookie zugeordnet erhalten einen bestimmten `IUnknown` Zeiger.|
|[CComUnkArray::GetUnknown](#getunknown)|Rufen Sie diese Methode zum Abrufen der `IUnknown` Zeiger, die einem angegebenen Cookie zugeordnet.|
|[CComUnkArray::Remove](#remove)|Rufen Sie diese Methode zum Entfernen einer `IUnknown` Zeiger aus dem Array.|

## <a name="remarks"></a>Hinweise

`CComUnkArray` enthält eine feste Anzahl von `IUnknown` Zeiger, die jeweils eine Schnittstelle für eine Verbindung verweist. `CComUnkArray` kann verwendet werden, als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse. `CComUnkArray<1>` ist eine Spezialisierung einer Klassenvorlage von `CComUnkArray` , die für einen Verbindungspunkt optimiert wurde.

Die `CComUnkArray` Methoden [beginnen](#begin) und [End](#end) kann zum Durchlaufen aller Verbindungspunkte (z. B., wenn ein Ereignis ausgelöst wird) verwendet werden.

Finden Sie unter [Hinzufügen von Verbindungspunkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md) zeigen Sie ausführliche Informationen zum Automatisieren der Erstellung der Verbindung Proxys.

> [!NOTE]
> **Hinweis** Klasse [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) dient der **Klasse hinzufügen** Assistenten beim Erstellen eines Steuerelements die Verbindungspunkte hat. Wenn Sie die Anzahl von Verbindungspunkten manuell angeben möchten, ändern Sie den Verweis aus `CComDynamicUnkArray` zu `CComUnkArray<` *n* `>`, wobei *n* ist die Anzahl von Verbindungspunkten Erforderlich.

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="add"></a>  CComUnkArray::Add

Rufen Sie diese Methode zum Hinzufügen einer `IUnknown` Zeiger auf das Array.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
Rufen Sie diese Methode zum Hinzufügen einer `IUnknown` Zeiger auf das Array.

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie, das den neu hinzugefügten Zeiger, oder 0 zugeordnet, wenn das Array nicht groß genug ist, enthält den neuen Zeiger ist.

##  <a name="begin"></a>  CComUnkArray::begin

Gibt einen Zeiger auf den Anfang der Auflistung von `IUnknown` Schnittstellenzeigern.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `IUnknown` Schnittstellenzeiger auf.

### <a name="remarks"></a>Hinweise

Die Auflistung enthält Zeiger auf die Schnittstellen, die lokal gespeichert werden, als `IUnknown`. Wandeln Sie jedes `IUnknown` echte Schnittstellentyp Schnittstelle, und klicken Sie dann über diese rufen. Sie müssen nicht zuerst für die Schnittstelle Abfragen.

Vor der Verwendung der `IUnknown` -Schnittstelle, sollten Sie überprüfen, dass er nicht NULL ist.

##  <a name="ccomunkarray"></a>  CComUnkArray::CComUnkArray

Der Konstruktor.

```
CComUnkArray();
```

### <a name="remarks"></a>Hinweise

Legt die Auflistung zum Speichern `nMaxSize` `IUnknown` Zeiger und initialisiert die Zeiger auf NULL.

##  <a name="end"></a>  CComUnkArray::end

Gibt einen Zeiger auf eine Stelle hinter dem letzten `IUnknown` Zeiger in der Auflistung.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `IUnknown` Schnittstellenzeiger auf.

### <a name="remarks"></a>Hinweise

Die `CComUnkArray` Methoden `begin` und `end` können verwendet werden, um alle Verbindungspunkte, z. B. durchlaufen zu lassen, wenn ein Ereignis ausgelöst wird.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

##  <a name="getcookie"></a>  CComUnkArray::GetCookie

Rufen Sie diese Methode, um das Cookie zugeordnet erhalten einen bestimmten `IUnknown` Zeiger.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parameter

*ppFind*<br/>
Die `IUnknown` Zeiger für das dem zugehörigen Cookies erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt das zugeordnete Cookie zurück der `IUnknown` Zeiger oder 0, wenn kein übereinstimmender `IUnknown` Zeiger befindet.

### <a name="remarks"></a>Hinweise

Es ist mehr als eine Instanz des gleichen `IUnknown` -Zeiger ist, diese Funktion gibt das Cookie für den ersten zurück.

##  <a name="getunknown"></a>  CComUnkArray::GetUnknown

Rufen Sie diese Methode zum Abrufen der `IUnknown` Zeiger, die einem angegebenen Cookie zugeordnet.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parameter

*dwCookie*<br/>
Das Cookie für die zugeordneten `IUnknown` Zeiger ist erforderlich.

### <a name="return-value"></a>Rückgabewert

Gibt die `IUnknown` Zeiger oder NULL, wenn keine übereinstimmenden Cookie gefunden wird.

##  <a name="remove"></a>  CComUnkArray::Remove

Rufen Sie diese Methode zum Entfernen einer `IUnknown` Zeiger aus dem Array.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parameter

*dwCookie*<br/>
Das Cookie verweisen auf die `IUnknown` Zeiger aus dem Array entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Zeiger entfernt, andernfalls FALSE ist.

## <a name="see-also"></a>Siehe auch

[CComDynamicUnkArray-Klasse](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
