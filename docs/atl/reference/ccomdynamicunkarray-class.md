---
title: CComDynamicUnkArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e776fd88799999ce175ba2efc137fc0353cbe65a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068467"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray-Klasse

Diese Klasse speichert ein Array von `IUnknown` Zeiger.

## <a name="syntax"></a>Syntax

```
class CComDynamicUnkArray
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Konstruktor. Initialisiert die Auflistungswerte NULL und die Größe der Auflistung auf 0 (null).|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|Rufen Sie diese Methode zum Hinzufügen einer `IUnknown` Zeiger auf das Array.|
|[CComDynamicUnkArray::begin](#begin)|Gibt einen Zeiger auf das erste `IUnknown` Zeiger in der Auflistung.|
|[CComDynamicUnkArray::clear](#clear)|Leert das Array an.|
|[CComDynamicUnkArray::end](#end)|Gibt einen Zeiger auf eine Stelle hinter dem letzten `IUnknown` Zeiger in der Auflistung.|
|[CComDynamicUnkArray::GetAt](#getat)|Ruft das Element am angegebenen Index ab.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|Rufen Sie diese Methode, um das Cookie zugeordnet erhalten einen bestimmten `IUnknown` Zeiger.|
|[CComDynamicUnkArray::GetSize](#getsize)|Gibt die Länge eines Arrays zurück.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Rufen Sie diese Methode zum Abrufen der `IUnknown` Zeiger, die einem angegebenen Cookie zugeordnet.|
|[CComDynamicUnkArray::Remove](#remove)|Rufen Sie diese Methode zum Entfernen einer `IUnknown` Zeiger aus dem Array.|

## <a name="remarks"></a>Hinweise

`CComDynamicUnkArray` enthält ein dynamisch zugeordnetes Array aus `IUnknown` Zeiger, die jeweils eine Schnittstelle für eine Verbindung verweist. `CComDynamicUnkArray` kann verwendet werden, als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse.

Die `CComDynamicUnkArray` Methoden [beginnen](#begin) und [End](#end) kann zum Durchlaufen aller Verbindungspunkte (z. B., wenn ein Ereignis ausgelöst wird) verwendet werden.

Finden Sie unter [Hinzufügen von Verbindungspunkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md) zeigen Sie ausführliche Informationen zum Automatisieren der Erstellung der Verbindung Proxys.

> [!NOTE]
> **Hinweis** Klasse `CComDynamicUnkArray` dient der **Klasse hinzufügen** Assistenten beim Erstellen eines Steuerelements die Verbindungspunkte hat. Wenn Sie die Anzahl von Verbindungspunkten manuell angeben möchten, ändern Sie den Verweis aus `CComDynamicUnkArray` zu `CComUnkArray<` *n* `>`, wobei *n* ist die Anzahl von Verbindungspunkten Erforderlich.

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="add"></a>  CComDynamicUnkArray::Add

Rufen Sie diese Methode zum Hinzufügen einer `IUnknown` Zeiger auf das Array.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
Die `IUnknown` Zeiger auf das Array hinzufügen.

### <a name="return-value"></a>Rückgabewert

Gibt den neu hinzugefügten Zeiger zugeordneten Cookie zurück.

##  <a name="begin"></a>  CComDynamicUnkArray::begin

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

##  <a name="clear"></a>  CComDynamicUnkArray::clear

Leert das Array an.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>  CComDynamicUnkArray::CComDynamicUnkArray

Der Konstruktor.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Hinweise

Legt die Größe der Auflistung auf NULL fest, und die Werte auf NULL initialisiert. Der Destruktor gibt die Auflistung frei, bei Bedarf.

##  <a name="dtor"></a>  CComDynamicUnkArray:: ~ CComDynamicUnkArray

Der Destruktor.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Hinweise

Gibt die von der Konstruktor der Klasse zugeordnete Ressourcen frei.

##  <a name="end"></a>  CComDynamicUnkArray::end

Gibt einen Zeiger auf eine Stelle hinter dem letzten `IUnknown` Zeiger in der Auflistung.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `IUnknown` Schnittstellenzeiger auf.

##  <a name="getat"></a>  CComDynamicUnkArray::GetAt

Ruft das Element am angegebenen Index ab.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des abzurufenden Elements.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) Schnittstelle.

##  <a name="getcookie"></a>  CComDynamicUnkArray::GetCookie

Rufen Sie diese Methode, um das Cookie zugeordnet erhalten einen bestimmten `IUnknown` Zeiger.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parameter

*ppFind*<br/>
Die `IUnknown` Zeiger für das dem zugehörigen Cookies erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt das zugeordnete Cookie zurück der `IUnknown` Zeiger ist, oder 0 (null), wenn kein übereinstimmendes `IUnknown` Zeiger befindet.

### <a name="remarks"></a>Hinweise

Es ist mehr als eine Instanz des gleichen `IUnknown` -Zeiger ist, diese Funktion gibt das Cookie für den ersten zurück.

##  <a name="getsize"></a>  CComDynamicUnkArray::GetSize

Gibt die Länge eines Arrays zurück.

```
int GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge des Arrays.

##  <a name="getunknown"></a>  CComDynamicUnkArray::GetUnknown

Rufen Sie diese Methode zum Abrufen der `IUnknown` Zeiger, die einem angegebenen Cookie zugeordnet.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parameter

*dwCookie*<br/>
Das Cookie für die zugeordneten `IUnknown` Zeiger ist erforderlich.

### <a name="return-value"></a>Rückgabewert

Gibt die `IUnknown` Zeiger oder NULL, wenn keine übereinstimmenden Cookie gefunden wird.

##  <a name="remove"></a>  CComDynamicUnkArray::Remove

Rufen Sie diese Methode zum Entfernen einer `IUnknown` Zeiger aus dem Array.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parameter

*dwCookie*<br/>
Das Cookie verweisen auf die `IUnknown` Zeiger aus dem Array entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Zeiger entfernt wird. andernfalls "false".

## <a name="see-also"></a>Siehe auch

[CComUnkArray-Klasse](../../atl/reference/ccomunkarray-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
