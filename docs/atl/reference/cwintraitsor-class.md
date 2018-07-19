---
title: CWinTraitsOR-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a996b1f2a9b81e9d74548f3e69883cee447ac3a0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881616"
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
 *t_dwStyle*  
 Standard-Window-Stile.  
  
 *t_dwExStyle*  
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
 *dwStyle*  
 Formatvorlagen, die für die Erstellung eines Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination der Formate, die übergeben werden *DwStyle* und die Anwendungen gemäß `t_dwStyle`, mit dem logischen OR-Operator.  
  
##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle  
 Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) die erweiterten Stile von Abrufen der `CWinTraits` Objekt und die Standardformatvorlagen, anhand des `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *dwExStyle*  
 Erweiterte Stile, die für die Erstellung eines Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von erweiterten Stile, die übergeben werden *DwExStyle* und standardmäßig vom angegebenen `t_dwExStyle`, mit dem logischen OR-Operator  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Einführung in Fenstermerkmale](../../atl/understanding-window-traits.md)

