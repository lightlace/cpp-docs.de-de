---
title: "CWindowImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWindowImpl"
  - "ATL.CWindowImpl"
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowImpl class"
  - "subclassing windows, ATL"
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CWindowImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Methoden für das Erstellen eines Fensters oder von Unterklassen eines Fensters bereit  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class TBase= CWindow,  
class TWinTraits= CControlWinTraits   
>  
class ATL_NO_VTABLE CWindowImpl :  
public CWindowImplBaseT< TBase, TWinTraits>  
```  
  
#### Parameter  
 `T`  
 Die neue Klasse, die von `CWindowImpl` abgeleitet ist.  
  
 *TBase*  
 Die Basisklasse der Klasse.  Die Basisklasse lautet standardmäßig [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 Eine [Trait\-Klasse](../../atl/understanding-window-traits.md), die Formatvorlagen für das Fenster definiert.  Der Standardwert ist `CControlWinTraits`.  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CWindowImpl::Create](../Topic/CWindowImpl::Create.md)|Erstellt ein Fenster.|  
  
### CWindowImplBaseT\-Methoden  
  
|||  
|-|-|  
|[DefWindowProc](../Topic/CWindowImpl::DefWindowProc.md)|Stellt die Standardverarbeitung von Nachrichten bereit.|  
|[GetCurrentMessage](../Topic/CWindowImpl::GetCurrentMessage.md)|Die gibt die aktuelle Nachricht zurück.|  
|[GetWindowProc](../Topic/CWindowImpl::GetWindowProc.md)|Gibt die aktuelle Fensterprozedur zurück.|  
|[OnFinalMessage](../Topic/CWindowImpl::OnFinalMessage.md)|Wird nach dem Empfang der letzten Nachricht aufgerufen \(in der Regel `WM_NCDESTROY`\).|  
|[SubclassWindow](../Topic/CWindowImpl::SubclassWindow.md)|Erstellt Unterklassen eines Fensters.|  
|[UnsubclassWindow](../Topic/CWindowImpl::UnsubclassWindow.md)|Stellt ein zuvor untergeordnetes Fenster wieder her.|  
  
### Statische Methoden  
  
|||  
|-|-|  
|[GetWndClassInfo](../Topic/CWindowImpl::GetWndClassInfo.md)|Gibt eine statische [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)\-Instanz zurück, mit der die Fensterklasseninformationen verwaltet werden.|  
|[WindowProc](../Topic/CWindowImpl::WindowProc.md)|Verarbeitet die Nachrichten, die an das Fenster gesendet werden.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_pfnSuperWindowProc](../Topic/CWindowImpl::m_pfnSuperWindowProc.md)|Zeigt auf die ursprüngliche Fensterprozedur der Fensterklasse.|  
  
## Hinweise  
 Mit `CWindowImpl` können Sie ein Fenster erstellen oder ein vorhandenes Fenster unterordnen. Die Fensterprozedur `CWindowImpl` verwendet eine Nachrichtenzuordnung, um Nachrichten auf die entsprechenden Handler zu leiten.  
  
 `CWindowImpl::Create` erstellt ein Fenster auf der Grundlage der Fensterklasseninformationen, das durch [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) verwaltet wird.  `CWindowImpl` enthält das [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md)\-Makro. Dies bedeutet, dass mit `CWndClassInfo` eine neue Windows\-Klasse registriert wird.  Wenn Sie eine vorhandene Fensterklasse überordnen möchten, leiten Sie die Klasse von `CWindowImpl` ab, und fügen Sie das Makro [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md) ein.  In diesem Fall wird mit `CWndClassInfo` eine Fensterklasse registriert, die auf einer vorhandenen Klasse basiert, aber `CWindowImpl::WindowProc` verwendet.  Beispiel:  
  
 [!CODE [NVC_ATL_Windowing#43](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#43)]  
  
> [!NOTE]
>  Da `CWndClassInfo` nur die Informationen für eine Fensterklasse verwaltet, basiert jedes Fenster, das durch eine Instanz von `CWindowImpl` erstellt wird, auf der gleichen Fensterklasse.  
  
 `CWindowImpl` unterstützt auch die Erstellung von Unterklassen von Fenstern.  Die `SubclassWindow`\-Methode fügt ein vorhandenes Fenster an das `CWindowImpl`\-Objekt an und ändert die Fensterprozedur in `CWindowImpl::WindowProc`.  Jede Instanz von `CWindowImpl` kann ein anderes Fenster unterordnen.  
  
> [!NOTE]
>  Rufen Sie für jedes `CWindowImpl`\-Objekt entweder **Erstellen** oder `SubclassWindow` auf.  Rufen Sie nicht beide Methoden für dasselbe Objekt auf.  
  
 Neben `CWindowImpl` stellt ATL [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) bereit, um ein Fenster zu erstellen, das in einem anderen Objekt enthalten ist.  
  
 Mit dem Basisklassendestruktor \(~**CWindowImplRoot**\) wird sichergestellt, dass das Fenster verfügbar wird, bevor das Objekt beschädigt wird.  
  
 `CWindowImpl` ist von **CWindowImplBaseT** abgeleitet, das von **CWindowImplRoot** abgeleitet ist, das wiederum von **TBase** und [CMessageMap](../../atl/reference/cmessagemap-class.md) abgeleitet ist.  
  
|Weitere Informationen zu|Siehe|  
|------------------------------|-----------|  
|Erstellen von Steuerelementen|[ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Verwenden von Fenstern in ATL|[ATL\-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL\-Projekt\-Assistent|[Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)|  
  
## Vererbungshierarchie  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## Anforderungen  
 **Header:** atlwin.h  
  
## Siehe auch  
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)