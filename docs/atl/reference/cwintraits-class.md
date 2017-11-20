---
title: CWinTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs: C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fecb7c614320c202a1159a527b34159c01099af6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cwintraits-class"></a>CWinTraits-Klasse
Diese Klasse stellt eine Methode für die um beim Erstellen eines Fensters Objekts verwendeten Stile zu standardisieren.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statisch) Ruft die erweiterten Stile für die `CWinTraits` Objekt.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statisch) Ruft die standardmäßige Formate für die `CWinTraits` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Dies [Fenster Traits](../../atl/understanding-window-traits.md) Klasse bietet eine einfache Methode zum für die Erstellung eines ATL-Fenster-Objekts verwendeten Stile zu standardisieren. Verwenden Sie eine Spezialisierung dieser Klasse als einen Vorlagenparameter [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder einen anderen ATL Fensterklassen an die standardmäßige und erweiterte verwendeten Standardstile für Instanzen dieser Fensterklasse.  
  
 Wenn Standard Fensterstile bereitzustellen, die verwendet werden, wenn keine andere Stile im Aufruf angegeben werden sollen, verwenden Sie diese Vorlage [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 ATL stellt drei vordefinierte spezialisierungen dieser Vorlage für häufig verwendete Parameterkombinationen Fensterstile:  
  
 `CControlWinTraits`  
 Für ein Fenster Standardsteuerelement konzipiert. Die folgenden standard-Stile werden verwendet: **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, und **WS_CLIPSIBLINGS**. Es sind keine erweiterten Stile.  
  
 `CFrameWinTraits`  
 Für eine standard-Frame-Fensters konzipiert. Enthalten die standard-Stile verwendet: **WS_OVERLAPPEDWINDOW**, **WS_CLIPCHILDREN**, und **WS_CLIPSIBLINGS**. Schließen Sie die erweiterten Stile verwendet: **WS_EX_APPWINDOW** und **WS_EX_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Für eine standardmäßige untergeordnetes MDI-Fenster konzipiert. Enthalten die standard-Stile verwendet: **WS_OVERLAPPEDWINDOW**, **WS_CHILD**, **WS_VISIBLE**, **WS_CLIPCHILDREN**, und **WS_CLIPSIBLINGS**. Schließen Sie die erweiterten Stile verwendet: **WS_EX_MDICHILD**.  
  
 Wenn Sie sicher, dass für bestimmte Formate für alle Instanzen der Fensterklasse zugleich anderen Formate, auf der Grundlage einer pro Instanz festgelegt werden verwenden möchten [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) stattdessen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="getwndstyle"></a>CWinTraits::GetWndStyle  
 Mit dieser Funktion können Sie die standardmäßige Formate der Abrufen der `CWinTraits` Objekt.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Standard-Stile für die Erstellung eines Fensters verwendet. Wenn `dwStyle` ist 0, den stilwerten der Vorlage ( `t_dwStyle`) werden zurückgegeben. Wenn `dwStyle` ungleich NULL ist `dwStyle` wird zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Der standard Fensterstile des Objekts.  
  
##  <a name="getwndexstyle"></a>CWinTraits::GetWndExStyle  
 Mit dieser Funktion wird zum Abrufen der erweiterten Stile eines der `CWinTraits` Objekt.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Erweiterten Stile, die für die Erstellung eines Fensters verwendet werden. Wenn `dwExStyle` ist 0, den stilwerten der Vorlage ( `t_dwExStyle`) werden zurückgegeben. Wenn `dwExStyle` ungleich NULL ist `dwExStyle` wird zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erweiterten Fensterstile des Objekts.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenmember](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Einführung in Fenstermerkmale](../../atl/understanding-window-traits.md)
