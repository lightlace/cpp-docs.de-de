---
title: "ISpecifyPropertyPagesImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ISpecifyPropertyPagesImpl"
  - "ATL.ISpecifyPropertyPagesImpl<T>"
  - "ATL::ISpecifyPropertyPagesImpl"
  - "ATL::ISpecifyPropertyPagesImpl<T>"
  - "ATL.ISpecifyPropertyPagesImpl"
  - "ISpecifyPropertyPagesImpl Class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages"
  - "ISpecifyPropertyPagesImpl class"
  - "Eigenschaftenseiten, CLSIDs associated with"
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# ISpecifyPropertyPagesImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung der Schnittstelle [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl :  
public ISpecifyPropertyPages  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `ISpecifyPropertyPagesImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](../Topic/ISpecifyPropertyPagesImpl::GetPages.md)|Füllt ein gezähltes Array UUID\-Werte aus.  Jedes UUID entspricht dem CLSID für eine der Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.|  
  
## Hinweise  
 Die [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217)\-Schnittstelle ermöglicht einem Client, erhält eine Liste der CLSID für die Eigenschaftenseiten, die von einem Objekt unterstützt werden.  \- Klasse `ISpecifyPropertyPagesImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
> [!NOTE]
>  Führen Sie nicht die Schnittstelle verfügbar **ISpecifyPropertyPages** wenn das Objekt nicht Eigenschaftenseiten unterstützt.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [IPropertyPageImpl Class](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)