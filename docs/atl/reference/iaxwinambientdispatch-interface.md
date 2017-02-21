---
title: "IAxWinAmbientDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinAmbientDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatch interface"
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# IAxWinAmbientDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Schnittstelle stellt Methoden zum Angeben von Eigenschaften des gehosteten Steuerelements oder des Containers bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
interface IAxWinAmbientDispatch : IDispatch  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[get\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::get_AllowContextMenu.md)|Die **AllowContextMenu**\-Eigenschaft gibt an, ob das gehostete Steuerelement ermöglicht wird, sein eigenes Kontextmenü anzuzeigen.|  
|[get\_AllowShowUI](../Topic/IAxWinAmbientDispatch::get_AllowShowUI.md)|Die **AllowShowUI**\-Eigenschaft gibt an, ob das gehostete Steuerelement ermöglicht wird, um eine eigene Benutzeroberfläche anzuzeigen.|  
|[get\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::get_AllowWindowlessActivation.md)|Die **AllowWindowlessActivation**\-Eigenschaft gibt an, ob der Container fensterlose Aktivierung zulässig.|  
|[get\_BackColor](../Topic/IAxWinAmbientDispatch::get_BackColor.md)|Die Eigenschaft gibt die `BackColor` eine Hintergrundfarbe des Containers an.|  
|[get\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::get_DisplayAsDefault.md)|**DisplayAsDefault** ist eine Ambient\-Eigenschaft, die einem Steuerelement ermöglicht, um festzustellen, ob es das Standardsteuerelement ist.|  
|[get\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::get_DocHostDoubleClickFlags.md)|Die **DocHostDoubleClickFlags**\-Eigenschaft gibt den Vorgang an, der als Reaktion auf einen Doppelklick stattfinden soll.|  
|[get\_DocHostFlags](../Topic/IAxWinAmbientDispatch::get_DocHostFlags.md)|Die Eigenschaft gibt die **DocHostFlags** Benutzeroberflächenfunktionen des Hostobjekts an.|  
|[get\_Font](../Topic/IAxWinAmbientDispatch::get_Font.md)|Die Eigenschaft gibt die **Font** Umgebungspinsel Schriftart des Containers an.|  
|[get\_ForeColor](../Topic/IAxWinAmbientDispatch::get_ForeColor.md)|Die Eigenschaft gibt die `ForeColor` Umgebungspinsel Vordergrundfarbe des Containers an.|  
|[get\_LocaleID](../Topic/IAxWinAmbientDispatch::get_LocaleID.md)|Die Eigenschaft gibt die **LocaleID** Umgebungspinsel Gebietsschema\-ID des Containers an.|  
|[get\_MessageReflect](../Topic/IAxWinAmbientDispatch::get_MessageReflect.md)|Die **MessageReflect** Ambient\-Eigenschaft gibt an, ob der Container Meldungen an das gehostete Steuerelement an.|  
|[get\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::get_OptionKeyPath.md)|Die **OptionKeyPath**\-Eigenschaft gibt den Registrierungsschlüsselpfad zu den Benutzereinstellungen an.|  
|[get\_ShowGrabHandles](../Topic/IAxWinAmbientDispatch::get_ShowGrabHandles.md)|Die **ShowGrabHandles** Ambient\-Eigenschaft ermöglicht es dem Steuerelement, um festzustellen, ob sie mit Ziehpunkten sich zeichnet.|  
|[Get\_ShowHatching](../Topic/IAxWinAmbientDispatch::get_ShowHatching.md)|Die **ShowHatching** Ambient\-Eigenschaft ermöglicht es dem Steuerelement, um festzustellen, ob sie sich schraffierte zeichnet.|  
|[get\_UserMode](../Topic/IAxWinAmbientDispatch::get_UserMode.md)|Die **UserMode**\-Eigenschaft gibt den Ambienten Benutzermodus des Containers an.|  
|[put\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::put_AllowContextMenu.md)|Die **AllowContextMenu**\-Eigenschaft gibt an, ob das gehostete Steuerelement ermöglicht wird, sein eigenes Kontextmenü anzuzeigen.|  
|[put\_AllowShowUI](../Topic/IAxWinAmbientDispatch::put_AllowShowUI.md)|Die **AllowShowUI**\-Eigenschaft gibt an, ob das gehostete Steuerelement ermöglicht wird, um eine eigene Benutzeroberfläche anzuzeigen.|  
|[put\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::put_AllowWindowlessActivation.md)|Die **AllowWindowlessActivation**\-Eigenschaft gibt an, ob der Container fensterlose Aktivierung zulässig.|  
|[put\_BackColor](../Topic/IAxWinAmbientDispatch::put_BackColor.md)|Die Eigenschaft gibt die `BackColor` eine Hintergrundfarbe des Containers an.|  
|[put\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::put_DisplayAsDefault.md)|**DisplayAsDefault** ist eine Ambient\-Eigenschaft, die einem Steuerelement ermöglicht, um festzustellen, ob es das Standardsteuerelement ist.|  
|[put\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::put_DocHostDoubleClickFlags.md)|Die **DocHostDoubleClickFlags**\-Eigenschaft gibt den Vorgang an, der als Reaktion auf einen Doppelklick stattfinden soll.|  
|[put\_DocHostFlags](../Topic/IAxWinAmbientDispatch::put_DocHostFlags.md)|Die Eigenschaft gibt die **DocHostFlags** Benutzeroberflächenfunktionen des Hostobjekts an.|  
|[put\_Font](../Topic/IAxWinAmbientDispatch::put_Font.md)|Die Eigenschaft gibt die **Font** Umgebungspinsel Schriftart des Containers an.|  
|[put\_ForeColor](../Topic/IAxWinAmbientDispatch::put_ForeColor.md)|Die Eigenschaft gibt die `ForeColor` Umgebungspinsel Vordergrundfarbe des Containers an.|  
|[put\_LocaleID](../Topic/IAxWinAmbientDispatch::put_LocaleID.md)|Die Eigenschaft gibt die **LocaleID** Umgebungspinsel Gebietsschema\-ID des Containers an.|  
|[put\_MessageReflect](../Topic/IAxWinAmbientDispatch::put_MessageReflect.md)|Die **MessageReflect** Ambient\-Eigenschaft gibt an, ob der Container Meldungen an das gehostete Steuerelement an.|  
|[put\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::put_OptionKeyPath.md)|Die **OptionKeyPath**\-Eigenschaft gibt den Registrierungsschlüsselpfad zu den Benutzereinstellungen an.|  
|[put\_UserMode](../Topic/IAxWinAmbientDispatch::put_UserMode.md)|Die **UserMode**\-Eigenschaft gibt den Ambienten Benutzermodus des Containers an.|  
  
## Hinweise  
 Diese Schnittstelle wird von ATL ActiveX\-Steuerelement verfügbar gemacht, das Objekte hostet.  Rufen Sie die Methoden für diese Schnittstelle, um die Ambient\-Eigenschaften festzulegen auf, die an das gehostete Steuerelement oder andere Aspekte des Verhaltens des Containers anzugeben verfügbar sind.  Um die Eigenschaften zu ergänzen kann von `IAxWinAmbientDispatch`, verwenden [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md) bereit.  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) versucht zu den Lastartinformationen über `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` vom Typbibliothek, die den Code enthält.  
  
 Wenn Sie ATL90.dll zu verknüpfen, lädt **AXHost** die Typinformationen aus der Typbibliothek in der DLL.  
  
 Siehe [Hosten von ActiveX\-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für weitere Details.  
  
## Anforderungen  
 Die Definition dieser Schnittstelle ist in verschiedene Formen, wie in der Tabelle unten dargestellt verfügbar.  
  
|Definitions\-Typ|Datei|  
|----------------------|-----------|  
|IDL|atliface.idl|  
|Typbibliothek|ATL.dll|  
|C\+\+|atliface.h \(auch enthaltene ATLBase.h\)|  
  
## Siehe auch  
 [IAxWinAmbientDispatchEx Interface](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow Interface](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)