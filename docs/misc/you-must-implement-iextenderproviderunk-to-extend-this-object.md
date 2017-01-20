---
title: "You must implement IExtenderProviderUnk to extend this object."
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_EXT_NONDISPATCHEXTENDEE"
ms.assetid: e0d4087f-9fa9-4fa9-92d9-7aed3103b2d8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# You must implement IExtenderProviderUnk to extend this object.
Das Extendee\-Objekt basiert auf der IUnknown\-Schnittstelle und nicht auf der IDispatch\-Schnittstelle.  
  
### So beheben Sie diesen Fehler  
  
1.  Für den Extenderanbieter muss IExtenderProviderUnk und nicht IExtenderProvider implementiert werden.  
  
## Siehe auch  
 <xref:EnvDTE.IExtenderProviderUnk>   
 <xref:EnvDTE.IExtenderProvider>   
 <xref:EnvDTE.ObjectExtenders>