---
title: CWinTraitsOR Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs: C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac6cf07fcd6d3703ffb6b483ba19a2d12520cb0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR-Klasse
Diese Klasse stellt eine Methode für die um beim Erstellen eines Fensters Objekts verwendeten Stile zu standardisieren.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>Parameter  
 `t_dwStyle`  
 Standard-Fensterstile.  
  
 `t_dwExStyle`  
 Standard-erweiterten Fensterstile.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Ruft die erweiterten Stile für die `CWinTraitsOR` Objekt.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Ruft die standardmäßige Formate für die `CWinTraitsOR` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Dies [Fenster Traits](../../atl/understanding-window-traits.md) Klasse bietet eine einfache Methode zum für die Erstellung eines ATL-Fenster-Objekts verwendeten Stile zu standardisieren. Verwenden Sie eine Spezialisierung dieser Klasse als einen Vorlagenparameter [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder einen anderen ATL Fensterklassen, geben Sie den minimalen Satz von standardmäßigen und erweiterte Formate für verwendet werden Instanzen dieser Fensterklasse.  
  
 Verwenden Sie eine Spezialisierung der Vorlage aus, wenn Sie sicher, dass für bestimmte Formate für alle Instanzen der Fensterklasse zugleich anderen instanzweise im Aufruf festgelegt werden sollen möchten [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Wenn Standard Fensterstile bereitzustellen, die verwendet werden, wenn keine andere Stile im Aufruf angegeben werden sollen `CWindowImpl::Create`, verwenden Sie [CWinTraits](../../atl/reference/cwintraits-class.md) stattdessen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) den Standardformaten der Abrufen der `CWinTraits` -Objekt und die Standardstile gemäß `t_dwStyle`.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Formatvorlagen, die für die Erstellung eines Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination der Formate, die übergeben werden `dwStyle` und der standardmäßige gravierende gemäß `t_dwStyle`, mit dem logischen OR-Operator.  
  
##  <a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) die erweiterten Stile der Abrufen der `CWinTraits` -Objekt und die Standardstile gemäß `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Erweiterten Stile, die für die Erstellung eines Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von erweiterten Stile, die übergeben werden `dwExStyle` und standardmäßig vom angegebenen `t_dwExStyle`, mit dem logischen OR-Operator  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Einführung in Fenstermerkmale](../../atl/understanding-window-traits.md)

