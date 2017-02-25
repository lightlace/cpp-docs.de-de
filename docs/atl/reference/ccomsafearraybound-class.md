---
title: "CComSafeArrayBound Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComSafeArrayBound"
  - "ATL::CComSafeArrayBound"
  - "CComSafeArrayBound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArrayBound class"
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComSafeArrayBound Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für eine [SAFEARRAYBOUND](assetId:///303a9bdb-71d6-4f14-8747-84cf84936c6d)\-Struktur.  
  
## Syntax  
  
```  
  
class CComSafeArrayBound : public SAFEARRAYBOUND  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[CComSafeArrayBound](../Topic/CComSafeArrayBound::CComSafeArrayBound.md)|Der \-Konstruktor.|  
|[GetCount](../Topic/CComSafeArrayBound::GetCount.md)|Rufen Sie diese Methode auf, um die Anzahl der Elemente zurückzugeben.|  
|[GetLowerBound](../Topic/CComSafeArrayBound::GetLowerBound.md)|Rufen Sie diese Methode auf, um die Untergrenze zurückzugeben.|  
|[GetUpperBound](../Topic/CComSafeArrayBound::GetUpperBound.md)|Rufen Sie diese Methode auf, um die Obergrenze zurückzugeben.|  
|[SetCount](../Topic/CComSafeArrayBound::SetCount.md)|Rufen Sie diese Methode auf, um die Anzahl von Elementen anzugeben.|  
|[SetLowerBound](../Topic/CComSafeArrayBound::SetLowerBound.md)|Rufen Sie diese Methode auf, um die Untergrenze festzulegen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \=](../Topic/CComSafeArrayBound::operator%20=.md)|Legt `CComSafeArrayBound` auf einen neuen Wert fest.|  
  
## Hinweise  
 Diese Klasse ist ein Wrapper für die **SAFEARRAYBOUND**\-Struktur, die durch [CComSafeArray](../../atl/reference/ccomsafearray-class.md) verwendet wird.  Sie stellt Methoden zum Abfragen bereit und das der Ober\- und Untergrenze einer einzelnen Dimension von `CComSafeArray` festlegen, befassen Sie und die Anzahl der Elemente ein, die sie enthält.  Ein mehrdimensionales `CComSafeArray`\-Objekt verwendet ein Array `CComSafeArrayBound`\-Objekte, eines für jede Dimension.  Wenn Sie Methoden wie [GetCount](../Topic/CComSafeArrayBound::GetCount.md) verwenden, beachten Sie, dass diese Methode nicht die Gesamtzahl der Elemente in einem mehrdimensionalen Array zurückgibt.  
  
 **Header:** atlsafe.h  
  
## Anforderungen  
 **Header:** atlsafe.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)