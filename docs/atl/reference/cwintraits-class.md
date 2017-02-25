---
title: "CWinTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinTraits"
  - "CMDIChildWinTraits"
  - "ATL.CWinTraits"
  - "CFrameWinTraits"
  - "ATL::CWinTraits"
  - "CControlWinTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlWinTraits class"
  - "CFrameWinTraits class"
  - "CMDIChildWinTraits class"
  - "CWinTraits class"
  - "window styles, default values for ATL"
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CWinTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Methode für die Normung der Formate bereit, die zur ein Fensterobjekt verwendet werden, erstellt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORD t_dwExStyle= 0  
>  
class CWinTraits  
```  
  
#### Parameter  
 `t_dwStyle`  
 Standard Standardfensterstile.  
  
 `t_dwExStyle`  
 Erweiterte Fensterstile des Standards.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWinTraits::GetWndExStyle](../Topic/CWinTraits::GetWndExStyle.md)|\(Statisch\) Ruft die erweiterten Stile für das `CWinTraits`\-Objekt ab.|  
|[CWinTraits::GetWndStyle](../Topic/CWinTraits::GetWndStyle.md)|\(Statisch\) Ruft die Standardformate für das `CWinTraits`\-Objekt ab.|  
  
## Hinweise  
 Diese Klasse [Fenstermerkmale](../../atl/understanding-window-traits.md) stellt eine einfache Methode für die Normung der Formate bereit, die für die Erstellung eines ATL\-Fensterobjekts verwendet werden.  Verwenden Sie eine Spezialisierung dieser Klasse als Vorlagenparameter zu [CWindowImpl](../../atl/reference/cwindowimpl-class.md) oder andere von Fensterklassen ATL, um den standardmäßigen Standard und die erweiterten Stile anzugeben, die für Instanzen dieser Fensterklasse verwendet werden.  
  
 Verwenden Sie diese Vorlage, wenn Sie standardmäßige Fensterstile bereitstellen möchten, die nur verwendet werden, wenn keine anderen Formate im Aufruf von [CWindowImpl::Create](../Topic/CWindowImpl::Create.md) angegeben werden.  
  
 ATL stellt drei vordefinierte Spezialisierungen dieser Vorlage für häufig verwendete Kombinationen von Fensterstilen bereit:  
  
 `CControlWinTraits`  
 Ist für ein Standardsteuerelementfenster.  Die folgenden Standardformate werden verwendet: **WS\_CHILD**, **WS\_VISIBLE**, **WS\_CLIPCHILDREN** und **WS\_CLIPSIBLINGS**.  Es gibt keine erweiterten Stile.  
  
 `CFrameWinTraits`  
 Ist für ein Standardrahmenfenster.  Das Standardformate verwendete zählen: **WS\_OVERLAPPEDWINDOW**, **WS\_CLIPCHILDREN** und **WS\_CLIPSIBLINGS**.  Das erweiterte Formate verwendete zählen: **WS\_EX\_APPWINDOW** und **WS\_EX\_WINDOWEDGE**.  
  
 `CMDIChildWinTraits`  
 Ist für ein Standarduntergeordnetes mdi\-fenster.  Das Standardformate verwendete zählen: **WS\_OVERLAPPEDWINDOW**, **WS\_CHILD**, **WS\_VISIBLE**, **WS\_CLIPCHILDREN** und **WS\_CLIPSIBLINGS**.  Das erweiterte Formate verwendete zählen: **WS\_EX\_MDICHILD**.  
  
 Wenn Sie sicherstellen möchten, dass bestimmte Formate für alle Instanzen der Fensterklasse beim Ermöglichen anderer Formate, pro Instanz stattdessen festgelegt wird, verwendet [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) festgelegt werden.  
  
## Anforderungen  
 **Header:** atlwin.h  
  
## Siehe auch  
 [Class Members](assetId:///dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Understanding Window Traits](../../atl/understanding-window-traits.md)