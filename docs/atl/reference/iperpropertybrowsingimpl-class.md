---
title: "IPerPropertyBrowsingImpl Class"
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
  - "ATL.IPerPropertyBrowsingImpl"
  - "IPerPropertyBrowsing"
  - "ATL::IPerPropertyBrowsingImpl"
  - "ATL::IPerPropertyBrowsingImpl<T>"
  - "IPerPropertyBrowsingImpl"
  - "ATL.IPerPropertyBrowsingImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPerPropertyBrowsing, ATL-Implementierung"
  - "IPerPropertyBrowsingImpl class"
  - "Eigenschaftenseiten, accessing information"
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IPerPropertyBrowsingImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und ermöglicht einem Client, um auf die Informationen in den Eigenschaftenseiten eines Objekts zuzugreifen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :  
public IPerPropertyBrowsing  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPerPropertyBrowsingImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](../Topic/IPerPropertyBrowsingImpl::GetDisplayString.md)|Ruft eine Zeichenfolge ab, die eine angegebene Eigenschaft beschreibt.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](../Topic/IPerPropertyBrowsingImpl::GetPredefinedStrings.md)|Ruft ein Zeichenfolgenarray gemäß den Werten ab, die eine angegebene Eigenschaft annehmen kann.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](../Topic/IPerPropertyBrowsingImpl::GetPredefinedValue.md)|Ruft **VARIANT** ab, das den Wert einer Eigenschaft enthält, die von einem angegebenen DISPID identifiziert wird.  Das DISPID wird mit dem Zeichenfolgennamen zugeordnet, der von `GetPredefinedStrings` abgerufen wird.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](../Topic/IPerPropertyBrowsingImpl::MapPropertyToPage.md)|Ruft die CLSID der Eigenschaftenseite ab, die einer angegebenen Eigenschaft zugeordnet ist.|  
  
## Hinweise  
 Die [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432)\-Schnittstelle ermöglicht einem Client, um auf die Informationen in den Eigenschaftenseiten eines Objekts zuzugreifen.  \- Klasse `IPerPropertyBrowsingImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
> [!NOTE]
>  Wenn Sie Microsoft Access als die Containeranwendung verwenden, müssen Sie die Klasse von `IPerPropertyBrowsingImpl` berechnen.  Andernfalls lädt Zugriff nicht das Steuerelement.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [IPropertyPageImpl Class](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)