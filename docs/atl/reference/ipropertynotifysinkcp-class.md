---
title: "IPropertyNotifySinkCP Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyNotifySinkCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verbindungspunkte [C++], Verwalten"
  - "IPropertyNotifySinkCP class"
  - "sinks, notifying of changes"
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPropertyNotifySinkCP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse macht [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)\-Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt verfügbar.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      , class  
      CDV   
      = CComDynamicUnkArray >  
class IPropertyNotifySinkCP :   
public IConnectionPointImpl< T, &IID_IPropertyNotifySink, CDV>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Eine Klasse, die die Verbindungen zwischen einem Verbindungspunkt und dessen Senken verwaltet.  Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), der unbegrenzte Verbindungen zulässig.  Sie können [CComUnkArray](../../atl/reference/ccomunkarray-class.md) auch verwenden, das eine feste Anzahl von Verbindungen angibt.  
  
## Hinweise  
 `IPropertyNotifySinkCP` erbt alle Methoden durch seine Basisklasse, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 Die Schnittstelle ermöglicht einem [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Senkenobjekt, Benachrichtigungen über Eigenschaftenänderungen zu empfangen.  \- Klasse `IPropertyNotifySinkCP` macht diese Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt verfügbar.  Der Client muss die `IPropertyNotifySink`\-Methoden für die Senke implementieren.  
  
 Leiten Sie die Klasse von `IPropertyNotifySinkCP`, wenn Sie einen Verbindungspunkt erstellen möchten, der die `IPropertyNotifySink`\-Schnittstelle darstellt.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [IConnectionPointImpl Class](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl Class](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)