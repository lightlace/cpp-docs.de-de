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
ms.openlocfilehash: 9388ca1751ee27fb25d6751c961d23e5243f2918
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495135"
---
# <a name="_u_menuorid-class"></a>_U_MENUorID-Klasse

Diese Klasse stellt Wrapper für `CreateWindow` und `CreateWindowEx`bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

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

Diese Argument Adapter Klasse ermöglicht, dass entweder IDs (uint) oder Menü Handles (hmenüs) an eine Funktion übergeben werden, ohne dass eine explizite Umwandlung für den Teil des Aufrufers erforderlich ist.

Diese Klasse ist für die Implementierung von Wrappern für die Windows-API konzipiert, insbesondere für die Funktionen "up [Window](/windows/win32/api/winuser/nf-winuser-createwindoww) " und " [deatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) ", die beide ein HMENU-Argument akzeptieren, das möglicherweise eine untergeordnete Fenster Kennung (uint) anstelle eines Menü Handles ist. Beispielsweise können Sie diese Klasse als Parameter für [CWindowImpl:: Create](cwindowimpl-class.md#create)verwenden.

Die-Klasse definiert zwei Konstruktorüberladungen: eine akzeptiert ein uint-Argument, und die andere akzeptiert ein HMENU-Argument. Das uint-Argument wird lediglich in ein HMENU im Konstruktor umgewandelt, und das Ergebnis wird im einzelnen Datenmember der Klasse, [m_hMenu](#_u_menuorid__m_hmenu), gespeichert. Das Argument für den HMENU-Konstruktor wird ohne Konvertierung direkt gespeichert.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin. h

##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu

Die-Klasse enthält den Wert, der an einen ihrer Konstruktoren als öffentliches HMENU-Datenmember übergeben wird.

```
HMENU m_hMenu;
```

##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID

Das uint-Argument wird lediglich in ein HMENU im Konstruktor umgewandelt, und das Ergebnis wird im einzelnen Datenmember der Klasse, [m_hMenu](#_u_menuorid__m_hmenu), gespeichert.

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Ein Bezeichner des untergeordneten Fensters.

*hMenu*<br/>
Ein Menü handle.

### <a name="remarks"></a>Hinweise

Das Argument für den HMENU-Konstruktor wird ohne Konvertierung direkt gespeichert.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
