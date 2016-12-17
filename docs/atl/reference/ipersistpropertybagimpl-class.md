---
title: "IPersistPropertyBagImpl Class"
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
  - "IPersistPropertyBagImpl"
  - "ATL.IPersistPropertyBagImpl<T>"
  - "ATL::IPersistPropertyBagImpl"
  - "ATL::IPersistPropertyBagImpl<T>"
  - "ATL.IPersistPropertyBagImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistPropertyBagImpl class"
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistPropertyBagImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und können Objekte, um die Eigenschaften zu einer Client\-angegebenen Eigenschaftensammlung zu speichern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template <   
class T   
>  
class ATL_NO_VTABLE IPersistPropertyBagImpl :  
public IPersistPropertyBag  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPersistPropertyBagImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](../Topic/IPersistPropertyBagImpl::GetClassID.md)|Ruft die CLSID des Objekts ab.|  
|[IPersistPropertyBagImpl::InitNew](../Topic/IPersistPropertyBagImpl::InitNew.md)|Initialisiert ein neu erstelltes Objekt.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IPersistPropertyBagImpl::Load](../Topic/IPersistPropertyBagImpl::Load.md)|Lädt die Eigenschaften des Objekts von einer Client\-angegebenen Eigenschaftensammlung.|  
|[IPersistPropertyBagImpl::Save](../Topic/IPersistPropertyBagImpl::Save.md)|Speichert die Eigenschaften des Objekts in eine vom Client Eigenschaftensammlung.|  
  
## Hinweise  
 Die [IPersistPropertyBag](https://msdn.microsoft.com/en-us/library/aa768205.aspx)\-Schnittstelle können Objekte, um die Eigenschaften zu einer Client\-angegebenen Eigenschaftensammlung zu speichern.  \- Klasse `IPersistPropertyBagImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **IPersistPropertyBag** funktioniert in Verbindung mit [IPropertyBag](https://msdn.microsoft.com/en-us/library/aa768196.aspx) und [IErrorLog](https://msdn.microsoft.com/en-us/library/aa768231.aspx).  Diese letzten zwei Schnittstellen müssen vom Client implementiert werden.  Durch `IPropertyBag` speichert der Client und lädt die einzelnen Eigenschaften des Objekts.  Durch **IErrorLog** können das Objekt und der Client melden alle auftretenden Fehler.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [BEGIN\_PROP\_MAP](../Topic/BEGIN_PROP_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)