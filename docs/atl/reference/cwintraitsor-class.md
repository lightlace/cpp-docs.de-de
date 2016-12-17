---
title: "CWinTraitsOR Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CWinTraitsOR"
  - "ATL::CWinTraitsOR"
  - "CWinTraitsOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinTraitsOR class"
  - "window styles, default values for ATL"
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CWinTraitsOR Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Methode für die Normung der Formate bereit, die zur ein Fensterobjekt verwendet werden, erstellt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORDt_dwExStyle= 0,  
class TWinTraits = CControlWinTraits   
>  
class CWinTraitsOR  
```  
  
#### Parameter  
 `t_dwStyle`  
 Standard Fensterstile.  
  
 `t_dwExStyle`  
 Erweiterte Fensterstile des Standards.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](../Topic/CWinTraitsOR::GetWndExStyle.md)|Ruft die erweiterten `CWinTraitsOR` Stile für das Objekt ab.|  
|[CWinTraitsOR::GetWndStyle](../Topic/CWinTraitsOR::GetWndStyle.md)|Ruft die Standardformate für das `CWinTraitsOR`\-Objekt ab.|  
  
## Hinweise  
 Diese Klasse [Fenstermerkmale](../../atl/understanding-window-traits.md) stellt eine einfache Methode für die Normung der Formate bereit, die für die Erstellung eines ATL\-Fensterobjekts verwendet werden.  Verwenden Sie eine Spezialisierung dieser Klasse als Vorlagenparameter zu [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder andere von Fensterklassen ATL, um das Minimum an, das von für Instanzen dieser Fensterklasse verwendet werden standardmäßigen und erweiterten Formaten, festgelegt ist.  
  
 Verwenden Sie eine Spezialisierung dieser Vorlage, wenn Sie sicherstellen möchten, dass bestimmte Formate für alle Instanzen der Fensterklasse beim Ermöglichen anderer Formate, im Aufruf von [CWindowImpl::Create](../Topic/CWindowImpl::Create.md) pro Instanz festgelegt werden festgelegt werden.  
  
 Wenn Sie Standard Fensterstile bereitstellen möchten, die nur verwendet werden, wenn keine anderen Formate im Aufruf von `CWindowImpl::Create` angegeben werden, verwenden Sie stattdessen [CWinTraits](../../atl/reference/cwintraits-class.md).  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)