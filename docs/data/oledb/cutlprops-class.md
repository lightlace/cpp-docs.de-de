---
title: "CUtlProps-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUtlProps-Klasse"
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert Eigenschaften für eine Reihe von OLE DB\-Eigenschaftenschnittstellen \(beispielsweise, `IDBProperties`, `IDBProperties` und `IRowsetInfo`\).  
  
## Syntax  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die `BEGIN_PROPSET_MAP` enthält.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Ruft eine Eigenschaft aus einem Eigenschaft ab.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Wird verwendet, um einen Wert zu prüfen, bevor eine Eigenschaft festgelegt wird.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Handleersuchen um eine optionale Schnittstelle, wenn ein Consumer eine Methode auf einer Objekterstellungsschnittstelle aufruft.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Wird aufgerufen, nachdem dem Festlegen einer Eigenschaft, um zu behandeln, verketteten Eigenschaften.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Legt eine Eigenschaft in einem Eigenschaft fest.|  
  
## Hinweise  
 Der Großteil dieser Klasse ist implementierungsspezifisch.  
  
 `CUtlProps` enthält zwei Member für Eigenschaften intern festlegen: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) und [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Weitere Informationen über Makros, die in einer Eigenschaftensetzuordnung verwendet werden, finden Sie unter [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md) und [END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md).  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)