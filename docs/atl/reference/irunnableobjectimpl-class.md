---
title: "IRunnableObjectImpl Class"
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
  - "IRunnableObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Container, running controls"
  - "Steuerelemente [ATL], Ausführen"
  - "Steuerelemente [C++], container running in ATL"
  - "IRunnableObject, ATL-Implementierung"
  - "IRunnableObjectImpl class"
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IRunnableObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung der Schnittstelle [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IRunnableObjectImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IRunnableObjectImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](../Topic/IRunnableObjectImpl::GetRunningClass.md)|Gibt die CLSID des ausgeführten Steuerelements zurück.  Die ATL\-Implementierung legt die CLSID zu `GUID_NULL` fest und gibt **E\_UNEXPECTED** zurück.|  
|[IRunnableObjectImpl::IsRunning](../Topic/IRunnableObjectImpl::IsRunning.md)|Bestimmt, ob das Steuerelement ausgeführt wird.  Die ATL\-Implementierung gibt **TRUE** zurück.|  
|[IRunnableObjectImpl::LockRunning](../Topic/IRunnableObjectImpl::LockRunning.md)|Sperrt das Steuerelement in den Zustand "Aktiv".  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IRunnableObjectImpl::Run](../Topic/IRunnableObjectImpl::Run.md)|Erzwingt das Steuerelement, um ausgeführt zu werden.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IRunnableObjectImpl::SetContainedObject](../Topic/IRunnableObjectImpl::SetContainedObject.md)|Gibt an, dass das Steuerelement eingebettet ist.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
  
## Hinweise  
 Die Schnittstelle ermöglicht [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) einen Container, um zu bestimmen, ob ein Steuerelement ausgeführt wird, erzwingen, um es ausgeführt werden oder sperren es in den Zustand "Aktiv".  \- Klasse `IRunnableObjectImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)