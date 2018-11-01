---
title: _U_MENUorID-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: dacb747978fd77d5ad8a464acc675c3509f5a815
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499735"
---
# <a name="umenuorid-class"></a>_U_MENUorID-Klasse

Diese Klasse stellt den Wrapper für `CreateWindow` und `CreateWindowEx`.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class _U_MENUorID
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Der Konstruktor.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Ein Handle für ein Menü.|

## <a name="remarks"></a>Hinweise

Dieses Argument-Adapterklasse ermöglicht entweder-IDs (jenem) oder im Menü-Handles (HMENUs) an eine Funktion übergeben werden, ohne eine explizite Umwandlung seitens des Aufrufers.

Diese Klasse zum Implementieren der Windows-API-Wrapper dient insbesondere die [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) und [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Funktionen, die beide ein HMENU-Argument, das ein untergeordnetes Fenster möglicherweise akzeptieren Bezeichner (UINT), anstatt ein Menühandle. Beispielsweise sehen Sie diese Klasse verwendet als Parameter an [CWindowImpl:: Create](cwindowimpl-class.md#create).

Die Klasse definiert zwei Konstruktorüberladungen: eine ein UINT-Argument akzeptiert und die andere ein HMENU-Argument akzeptiert. Das Argument "uint" umgewandelt wird nur ein HMENU im Konstruktor und in das Ergebnis gespeichert werden, in der Klasse der einzelnen Datenmember, [M_hMenu](#_u_menuorid__m_hmenu). Das Argument für das HMENU-Konstruktor wird direkt ohne Konvertierung gespeichert.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="_u_menuorid__m_hmenu"></a>  _U_MENUorID::m_hMenu

Die Klasse enthält den Wert als einen öffentlichen Datenmember von HMENU an eines ihrer Konstruktoren übergeben.

```
HMENU m_hMenu;
```

##  <a name="_u_menuorid___u_menuorid"></a>  _U_MENUorID::_U_MENUorID

Das Argument "uint" umgewandelt wird nur ein HMENU im Konstruktor und in das Ergebnis gespeichert werden, in der Klasse der einzelnen Datenmember, [M_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Ein Bezeichner des untergeordneten Fensters.

*hMenu*<br/>
Ein Menühandle.

### <a name="remarks"></a>Hinweise

Das Argument für das HMENU-Konstruktor wird direkt ohne Konvertierung gespeichert.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
