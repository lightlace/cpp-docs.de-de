---
title: CWinTraitsOR-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: ec628fcde40d3cc4601d6b6ddf49fa5599ac5a86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276730"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR-Klasse

Diese Klasse stellt eine Methode für die Standardisierung der Stile, die beim Erstellen eines Objekts im Fenster verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>Parameter

*t_dwStyle*<br/>
Standard-Window-Stile.

*t_dwExStyle*<br/>
Erweiterte Fensterstile wird standardmäßig.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Ruft die erweiterten Stile für die `CWinTraitsOR` Objekt.|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Ruft die standard-Formate für die `CWinTraitsOR` Objekt.|

## <a name="remarks"></a>Hinweise

Dies [Fenstermerkmale](../../atl/understanding-window-traits.md) Klasse bietet eine einfache Methode für die Standardisierung der Stile, die für die Erstellung eines ATL-Fenster-Objekts verwendet. Verwenden Sie eine Spezialisierung dieser Klasse als Vorlagenparameter zu [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder einer anderen ATLs-Fensterklassen an der minimale Satz von Standard- und erweiterte Formate für zu verwendende Instanzen dieser Fensterklasse.

Eine Spezialisierung der diese Vorlage verwenden, sollten Sie sicherstellen, dass bestimmte Formate für alle Instanzen der Fensterklasse festgelegt sind, während andere Stile zulassen auf einer Basis pro Instanz im Aufruf von festgelegt werden [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).

Wenn Standardwert Window-Stile anzugeben, die verwendet werden, wenn keine anderen Arten im Aufruf angegeben werden sollen `CWindowImpl::Create`, verwenden Sie [CWinTraits](../../atl/reference/cwintraits-class.md) stattdessen.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="getwndstyle"></a>  CWinTraitsOR::GetWndStyle

Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) die standard-Formate von Abrufen der `CWinTraits` Objekt und die Standardformatvorlagen, anhand des *T_dwStyle*.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Formatvorlagen, die für die Erstellung eines Fensters verwendet werden.

### <a name="return-value"></a>Rückgabewert

Eine Kombination der Formate, die übergeben werden *DwStyle* und die Anwendungen gemäß `t_dwStyle`, mit dem logischen OR-Operator.

##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle

Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) die erweiterten Stile von Abrufen der `CWinTraits` Objekt und die Standardformatvorlagen, anhand des `t_dwStyle`.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parameter

*dwExStyle*<br/>
Erweiterte Stile, die für die Erstellung eines Fensters verwendet werden.

### <a name="return-value"></a>Rückgabewert

Eine Kombination von erweiterten Stile, die übergeben werden *DwExStyle* und standardmäßig vom angegebenen `t_dwExStyle`, mit dem logischen OR-Operator

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Einführung in Fenstermerkmale](../../atl/understanding-window-traits.md)
