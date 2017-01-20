---
title: "IPropertyPage2Impl Class"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "IPropertyPage2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage2 ATL implementation"
  - "IPropertyPage2Impl class"
  - "Eigenschaftenseiten"
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyPage2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und erbt die Standardimplementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPage2Impl : public IPropertyPageImpl< T>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPropertyPage2Impl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](../Topic/IPropertyPage2Impl::EditProperty.md)|Gibt an, dem Reihe von Eigenschaften steuern den Fokus erhält, wenn die Eigenschaftenseite aktiviert ist.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
  
## Hinweise  
 Die [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996)\-Schnittstelle erweitert [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246), indem sie die `EditProperty`\-Methode hinzugefügt wird.  Diese Methode ermöglicht einem Client, um eine bestimmte Eigenschaft in einem Eigenschaftenseitenobjekt auszuwählen.  
  
 \- Klasse `IPropertyPage2Impl` gibt einfach **E\_NOTIMPL** für **IPropertyPage2::EditProperty** zurück.  erbt jedoch es die Standardimplementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 Wenn Sie eine Eigenschaftenseite erstellen, wird die Klasse in der Regel von `IPropertyPageImpl` abgeleitet.  Um die zusätzliche Unterstützung von **IPropertyPage2** zu ermöglichen, ändern Sie die Klassendefinition und überschreiben Sie die Methode `EditProperty`.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)