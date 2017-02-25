---
title: "IAxWinAmbientDispatchEx Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IAxWinAmbientDispatchEx"
  - "IAxWinAmbientDispatchEx"
  - "ATL::IAxWinAmbientDispatchEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatchEx interface"
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# IAxWinAmbientDispatchEx Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Schnittstelle implementiert ergänzende Ambient\-Eigenschaften für ein gehostetes Steuerelement.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      MIDL_INTERFACE( "B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5" )  
IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[SetAmbientDispatch](../Topic/IAxWinAmbientDispatchEx::SetAmbientDispatch.md)|Diese Methode wird aufgerufen, um die standardmäßige Ambient\-Eigenschaft\-Schnittstelle mit einer benutzerdefinierten Schnittstelle zu ergänzen.|  
  
## Hinweise  
 Schließen Sie diese Schnittstelle in ATL\-Anwendungen, die statisch mit ATL verknüpft und ActiveX\-Steuerelemente gehostet werden, insbesondere ActiveX\-Steuerelemente ein, die Ambient\-Eigenschaften haben.  Nicht einschließlich diese Schnittstelle generiert diese Assertion: "Vergaßen Sie, die LIBID zu CComModule::Init zu übergeben?"  
  
 Diese Schnittstelle wird von ATL ActiveX\-Steuerelement verfügbar gemacht, das Objekte hostet.  Ist von [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), fügt `IAxWinAmbientDispatchEx` eine Methode hinzu, die es Ihnen ermöglicht, die Ambient\-Eigenschaft\-Schnittstelle zu ergänzen, die von ATL mit einem von eigenen bereitgestellt wird.  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) versucht zu den Lastartinformationen über `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` aus der Typbibliothek, die den Code enthält.  
  
 Wenn Sie ATL90.dll zu verknüpfen, lädt **AXHost** die Typinformationen aus der Typbibliothek in der DLL.  
  
 Siehe [Hosten von ActiveX\-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für weitere Details.  
  
## Anforderungen  
 Die Definition dieser Schnittstelle ist in mehreren Formen, wie in der folgenden Tabelle verfügbar.  
  
|Definitions\-Typ|Datei|  
|----------------------|-----------|  
|IDL|atliface.idl|  
|Typbibliothek|ATL.dll|  
|C\+\+|atliface.h \(auch enthaltene ATLBase.h\)|  
  
## Siehe auch  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)