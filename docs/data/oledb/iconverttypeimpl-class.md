---
title: "IConvertTypeImpl-Klasse"
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
  - "ATL.IConvertTypeImpl<T>"
  - "IConvertTypeImpl"
  - "ATL.IConvertTypeImpl"
  - "ATL::IConvertTypeImpl"
  - "ATL::IConvertTypeImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IConvertTypeImpl-Klasse"
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IConvertTypeImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung der [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IConvertTypeImpl` abgeleitet.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[CanConvert](../../data/oledb/iconverttypeimpl-canconvert.md)|Gibt Informationen zur Verfügbarkeit von Typkonvertierungen auf einen Befehl oder auf einem Rowset.|  
  
## Hinweise  
 Diese Schnittstelle ist auf Befehlen, Rowsets und Indexrowsets erforderlich.  **IConvertTypeImpl**  implementiert die Schnittstelle, indem zur Konvertierung delegiert das Objekt, das durch OLE DB angegeben wird.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)