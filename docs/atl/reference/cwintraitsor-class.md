---
title: Klasse CWinTraitsOR | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cd077c7f79c3099d0e825a48233e7a8b269c0d04
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraitsor-class"></a>CWinTraitsOR-Klasse
Diese Klasse stellt eine Methode für die Standardisierung der Formatvorlagen verwendet, wenn ein Window-Objekt zu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Ruft die erweiterten Stile für das `CWinTraitsOR` Objekt.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Ruft die standard-Formate für die `CWinTraitsOR` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese [Fenster Merkmale](../../atl/understanding-window-traits.md) -Klasse stellt eine einfache Methode für die Erstellung von ATL-Fensterobjekts verwendeten Stile zu standardisieren. Verwenden Sie eine Spezialisierung dieser Klasse als einen Vorlagenparameter an [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder einem anderen ATL Fensterklassen an, der minimale Satz von standardmäßigen und die erweiterten Stile für verwendet werden Instanzen dieser Fensterklasse.  
  
 Eine Spezialisierung der Vorlage verwenden, wenn Sie sicherstellen möchten, dass bestimmte Stile für alle Instanzen der Fensterklasse festgelegt sind zugleich anderen Formatvorlagen auf Instanzebene im Aufruf von festgelegt werden [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Wenn Standard Fensterstile bereitzustellen, die verwendet wird, nur, wenn keine andere Stile im Aufruf angegeben werden sollen `CWindowImpl::Create`, verwenden Sie [CWinTraits](../../atl/reference/cwintraits-class.md) stattdessen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) den Standardformaten der Abrufen der `CWinTraits` -Objekt und die Standardstile angegebenen `t_dwStyle`.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Stile, die für die Erstellung eines Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Formatvorlagen, die übergeben werden `dwStyle` und die Einsen durch angegebene `t_dwStyle`, mit dem logischen OR-Operator.  
  
##  <a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 Mit dieser Funktion können Sie eine Kombination aus (mit logischen OR-Operators) die erweiterten Stile der Abrufen der `CWinTraits` -Objekt und die Standardstile angegebenen `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Erweiterte Stile, die für die Erstellung eines Fensters verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von erweiterten Stile, die übergeben werden `dwExStyle` und diejenigen angegebenen `t_dwExStyle`, mit dem logischen OR-Operator  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Grundlegendes zum Fenster "traits"](../../atl/understanding-window-traits.md)


