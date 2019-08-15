---
title: Ccomdynamicunkarray-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: d55a6d6bfbcc6921fa0633753365f5799388dc27
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497247"
---
# <a name="ccomdynamicunkarray-class"></a>Ccomdynamicunkarray-Klasse

Diese Klasse speichert ein Array von `IUnknown` Zeigern.

## <a name="syntax"></a>Syntax

```
class CComDynamicUnkArray
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Konstruktor. Initialisiert die Auflistungs Werte in NULL und die Sammlungs Größe auf 0 (null).|
|[CComDynamicUnkArray::~CComDynamicUnkArray](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|Mit dieser Methode können Sie einen `IUnknown` Zeiger auf das Array hinzufügen.|
|[CComDynamicUnkArray::begin](#begin)|Gibt einen Zeiger auf den ersten `IUnknown` Zeiger in der Auflistung zurück.|
|[CComDynamicUnkArray::clear](#clear)|Leert das Array.|
|[CComDynamicUnkArray::end](#end)|Gibt einen Zeiger auf einen Zeiger hinter dem `IUnknown` letzten Zeiger in der Auflistung zurück.|
|[CComDynamicUnkArray::GetAt](#getat)|Ruft das Element am angegebenen Index ab.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|Mit dieser Methode können Sie das Cookie abrufen, das einem `IUnknown` bestimmten Zeiger zugeordnet ist.|
|[CComDynamicUnkArray::GetSize](#getsize)|Gibt die Länge eines Arrays zurück.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Mit dieser Methode können Sie den `IUnknown` Zeiger abrufen, der einem bestimmten Cookie zugeordnet ist.|
|[CComDynamicUnkArray::Remove](#remove)|Diese Methode wird aufgerufen, um `IUnknown` einen Zeiger aus dem Array zu entfernen.|

## <a name="remarks"></a>Hinweise

`CComDynamicUnkArray`enthält ein dynamisch zugeordneter `IUnknown` Array von Zeigern, von denen jede eine Schnittstelle auf einem Verbindungspunkt ist. `CComDynamicUnkArray`kann als Parameter für die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) -Vorlagen Klasse verwendet werden.

Die `CComDynamicUnkArray` Methoden [Begin](#begin) und [End](#end) können verwendet werden, um alle Verbindungspunkte zu durchlaufen (z. b. Wenn ein Ereignis ausgelöst wird).

Ausführliche Informationen zum Automatisieren der Erstellung von Verbindungspunkt Proxys finden [Sie unter Hinzufügen von Verbindungs Punkten zu einem Objekt](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Hinweis** Die- `CComDynamicUnkArray` Klasse wird vom Assistenten zum **Hinzufügen von Klassen** verwendet, wenn ein Steuerelement erstellt wird, das Verbindungspunkte aufweist. Wenn Sie die Anzahl der Verbindungspunkte manuell angeben möchten, ändern Sie den Verweis von `CComDynamicUnkArray` auf `CComUnkArray<` *n* `>`, wobei *n* für die Anzahl der erforderlichen Verbindungspunkte steht.

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="add"></a>Ccomdynamicunkarray:: Add

Mit dieser Methode können Sie einen `IUnknown` Zeiger auf das Array hinzufügen.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
Der `IUnknown` Zeiger, der dem Array hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie zurück, das dem neu hinzugefügten Zeiger zugeordnet ist.

##  <a name="begin"></a>Ccomdynamicunkarray:: begin

Gibt einen Zeiger auf den Anfang der Auflistung von `IUnknown` Schnittstellen Zeigern zurück.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf einen `IUnknown` -Schnittstellen Zeiger.

### <a name="remarks"></a>Hinweise

Die-Auflistung enthält Zeiger auf Schnittstellen, `IUnknown`die lokal als gespeichert werden. Sie wandeln jede `IUnknown` Schnittstelle in den echten Schnittstellentyp um und durchlaufen Sie anschließend. Sie müssen die-Schnittstelle nicht zuerst Abfragen.

Bevor Sie die `IUnknown` -Schnittstelle verwenden, sollten Sie überprüfen, ob Sie nicht NULL ist.

##  <a name="clear"></a>Ccomdynamicunkarray:: Clear

Leert das Array.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>Ccomdynamicunkarray:: ccomdynamicunkarray

Der Konstruktor.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Hinweise

Legt die Sammlungs Größe auf NULL fest und initialisiert die Werte auf NULL. Der Dekonstruktor gibt die Auflistung bei Bedarf frei.

##  <a name="dtor"></a>Ccomdynamicunkarray:: ~ ccomdynamicunkarray

Der Destruktor.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Hinweise

Gibt Ressourcen frei, die vom-Klassenkonstruktor zugeordnet werden.

##  <a name="end"></a>Ccomdynamicunkarray:: End

Gibt einen Zeiger auf einen Zeiger hinter dem `IUnknown` letzten Zeiger in der Auflistung zurück.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf einen `IUnknown` -Schnittstellen Zeiger.

##  <a name="getat"></a>Ccomdynamicunkarray:: GetAt

Ruft das Element am angegebenen Index ab.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des abzurufenden Elements.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) -Schnittstelle.

##  <a name="getcookie"></a>Ccomdynamicunkarray:: GetCookie

Mit dieser Methode können Sie das Cookie abrufen, das einem `IUnknown` bestimmten Zeiger zugeordnet ist.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parameter

*ppFind*<br/>
Der `IUnknown` Zeiger, für den das zugeordnete Cookie erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt das Cookie zurück, das `IUnknown` dem Zeiger zugeordnet ist, oder 0 `IUnknown` (null), wenn kein entsprechender Zeiger gefunden wird.

### <a name="remarks"></a>Hinweise

Wenn mehr als eine Instanz desselben `IUnknown` Zeigers vorhanden ist, gibt diese Funktion das Cookie für die erste Instanz zurück.

##  <a name="getsize"></a>Ccomdynamicunkarray:: GetSize

Gibt die Länge eines Arrays zurück.

```
int GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge des Arrays.

##  <a name="getunknown"></a>Ccomdynamicunkarray:: getunknown

Mit dieser Methode können Sie den `IUnknown` Zeiger abrufen, der einem bestimmten Cookie zugeordnet ist.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parameter

*dwCookie*<br/>
Das Cookie, für das der `IUnknown` zugeordnete Zeiger erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt den `IUnknown` -Zeiger zurück, oder NULL, wenn kein entsprechendes Cookie gefunden wird.

##  <a name="remove"></a>Ccomdynamicunkarray:: Remove

Diese Methode wird aufgerufen, um `IUnknown` einen Zeiger aus dem Array zu entfernen.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parameter

*dwCookie*<br/>
Das Cookie, das auf `IUnknown` den Zeiger verweist, der aus dem Array entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der Zeiger entfernt wurde. andernfalls false.

## <a name="see-also"></a>Siehe auch

[CComUnkArray-Klasse](../../atl/reference/ccomunkarray-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
