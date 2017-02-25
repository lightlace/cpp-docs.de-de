---
title: "CManualAccessor-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor"
  - "ATL.CManualAccessor"
  - "CManualAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CManualAccessor-Klasse"
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CManualAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Accessortyp dar, der für erweiterte Verwendung entworfen wurde.  
  
## Syntax  
  
```  
class CManualAccessor : public CAccessorBase  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|Fügt einem Bindungseintrag den Ausgabespalten hinzu.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|Fügt einem Parametereintrag dem Parameteraccessor hinzu.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Belegt Spaltenbindung für die strukturierte und initialisiert die Spaltendatenmembern Speicher.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Belegt für die Parameterbindung strukturiert und initialisiert die Parameterdatenmember Speicher.|  
  
## Hinweise  
 Mithilfe von `CManualAccessor` können Sie die Parameter und Ausgabespaltenbindung durch Laufzeitfunktionsaufrufe angeben.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor\-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)