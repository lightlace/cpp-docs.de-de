---
title: Klasse CWinTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: abd62b916f976721bf85fc4bb2a94ffaf5b217ea
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cwintraits-class"></a>CWinTraits-Klasse
Diese Klasse stellt eine Methode für die Standardisierung der Formatvorlagen verwendet, wenn ein Window-Objekt zu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>Parameter  
 `t_dwStyle`  
 Standardfenster Standardstile.  
  
 `t_dwExStyle`  
 Standard-erweiterten Fensterstile.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statisch) Ruft die erweiterten Stile für das `CWinTraits` Objekt.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statisch) Ruft die standard-Formate für die `CWinTraits` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese [Fenster Merkmale](../../atl/understanding-window-traits.md) -Klasse stellt eine einfache Methode für die Erstellung von ATL-Fensterobjekts verwendeten Stile zu standardisieren. Verwenden Sie eine Spezialisierung dieser Klasse als einen Vorlagenparameter an [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder einem anderen ATL Fensterklassen an die standardmäßige und erweiterte verwendeten Standardstile für Instanzen dieser Fensterklasse.  
  
 Verwenden Sie diese Vorlage standardmäßig Fensterstile bereit, die verwendet wird, nur, wenn keine andere Stile im Aufruf angegeben werden [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 ATL stellt drei vordefinierte spezialisierungen dieser Vorlage für häufig verwendete Kombinationen von Window-Stile:  
  
 `CControlWinTraits`  
 Für ein Fenster Standardsteuerelement konzipiert. Die folgenden standard-Formate verwendet werden: **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, und **WS_CLIPSIBLINGS**. Es sind keine erweiterten Stile.  
  
 `CFrameWinTraits`  
 Für einen standard-Frame-Fensters konzipiert. Die standardmäßigen Formatvorlagen enthalten: **WS_OVERLAPPEDWINDOW**, **WS_CLIPCHILDREN**, und **WS_CLIPSIBLINGS**. Die erweiterten Stile, die enthalten: **WS_EX_APPWINDOW** und **WS_EX_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Entwickelt für eine standardmäßige untergeordnete MDI-Fenster. Die standardmäßigen Formatvorlagen enthalten: **WS_OVERLAPPEDWINDOW**, **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, und **WS_CLIPSIBLINGS**. Die erweiterten Stile, die enthalten: **WS_EX_MDICHILD**.  
  
 Wenn Sie sicherstellen möchten, dass bestimmte Formate festgelegt sind, für alle Instanzen der Fensterklasse, während gleichzeitig andere Stile auf einer Basis pro Instanz festgelegt werden [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) stattdessen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraits::GetWndStyle  
 Rufen Sie diese Funktion zum Abrufen der standard-Stile eines der `CWinTraits` Objekt.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Standard-Formate für die Erstellung eines Fensters verwendet. Wenn `dwStyle` ist 0, die Vorlage Style-Werte ( `t_dwStyle`) zurückgegeben werden. Wenn `dwStyle` ungleich NULL ist, wird `dwStyle` zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Fensterstile des Objekts.  
  
##  <a name="getwndexstyle"></a>CWinTraits::GetWndExStyle  
 Mit dieser Funktion können Sie die erweiterten Stile der Abrufen der `CWinTraits` Objekt.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Erweiterte Stile, die für die Erstellung eines Fensters verwendet werden. Wenn `dwExStyle` ist 0, die Vorlage Style-Werte ( `t_dwExStyle`) zurückgegeben werden. Wenn `dwExStyle` ungleich NULL ist, wird `dwExStyle` zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erweiterten Fensterstile des Objekts.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenmember](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Grundlegendes zum Fenster "traits"](../../atl/understanding-window-traits.md)

