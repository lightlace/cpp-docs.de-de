---
title: CWinTraits-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb6ee8cd591c4a5b5a4a3701c6974849f9e3238f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069391"
---
# <a name="cwintraits-class"></a>CWinTraits-Klasse

Diese Klasse stellt eine Methode für die Standardisierung der Stile, die beim Erstellen eines Objekts im Fenster verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>Parameter

*t_dwStyle*<br/>
Standardfenster Standardstile.

*t_dwExStyle*<br/>
Erweiterte Fensterstile wird standardmäßig.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statisch) Ruft die erweiterten Stile für die `CWinTraits` Objekt.|
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statisch) Ruft die standard-Formate für die `CWinTraits` Objekt.|

## <a name="remarks"></a>Hinweise

Dies [Fenstermerkmale](../../atl/understanding-window-traits.md) Klasse bietet eine einfache Methode für die Standardisierung der Stile, die für die Erstellung eines ATL-Fenster-Objekts verwendet. Verwenden Sie eine Spezialisierung dieser Klasse als einen Vorlagenparameter [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder einer anderen ATLs-Fensterklassen an die standardmäßige und erweiterte verwendeten Standardstile für Instanzen dieser Fensterklasse.

Verwenden Sie diese Vorlage, wenn Sie möchten, um Standardwert Window-Stile anzugeben, die verwendet werden, wenn keine anderen Arten im Aufruf angegeben werden [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).

ATL bietet drei vordefinierte spezialisierungen dieser Vorlage für häufig verwendeten Kombinationen von Window-Stile:

- `CControlWinTraits`  

   Entwickelt für ein Standardsteuerelement-Fenster. Die folgenden standard-Formate werden verwendet: WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN und WS_CLIPSIBLINGS. Es gibt keine erweiterten Stile.

- `CFrameWinTraits`  

   Entwickelt für eine standard-Frame-Fensters. Enthalten die standard-Formate verwendet: WS_OVERLAPPEDWINDOW WS_CLIPCHILDREN und WS_CLIPSIBLINGS. Die erweiterten Stile verwendet enthalten: WS_EX_APPWINDOW und WS_EX_WINDOWEDGE.

- `CMDIChildWinTraits`  

   Entwickelt für eine standardmäßige untergeordneten MDI-Fensters. Enthalten die standard-Formate verwendet: WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN und WS_CLIPSIBLINGS. Die erweiterten Stile verwendet enthalten: WS_EX_MDICHILD.

Wenn Sie sicher, dass für bestimmte Formate für alle Instanzen der Fensterklasse zugleich andere Stile auf einer Basis pro Instanz festgelegt werden verwenden möchten [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) stattdessen.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle

Mit dieser Funktion können Sie die standard-Formate von Abrufen der `CWinTraits` Objekt.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Standard-Formate für die Erstellung eines Fensters verwendet. Wenn *DwStyle* ist 0, die Vorlage Style-Werte (`t_dwStyle`) zurückgegeben werden. Wenn *DwStyle* ungleich NULL ist, *DwStyle* zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Der standard Fensterstile des Objekts.

##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle

Mit dieser Funktion können Sie die erweiterten Stile von Abrufen der `CWinTraits` Objekt.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parameter

*dwExStyle*<br/>
Erweiterte Stile, die für die Erstellung eines Fensters verwendet werden. Wenn *DwExStyle* ist 0, die Vorlage Style-Werte (`t_dwExStyle`) zurückgegeben werden. Wenn *DwExStyle* ungleich NULL ist, *DwExStyle* zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

Die erweiterten Fensterstile des Objekts.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Einführung in Fenstermerkmale](../../atl/understanding-window-traits.md)
