---
title: "Aggregation and Class Factory Macros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], ATL macros"
  - "class factories, ATL macros"
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
caps.latest.revision: 17
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Aggregation and Class Factory Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Makros stellen Methoden zum Steuern von Aggregation und des Deklarierens von Class Factory.  
  
|||  
|-|-|  
|[DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)|Deklariert, dass das Objekt aggregiert werden kann \(Standardeinstellung\).|  
|[DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)|Deklariert die Klassenfactory, um [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), die ATL\-Standardklassenfactory zu sein.|  
|[DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md)|Deklariert das Klassenfactoryobjekt, um die Klassenfactory zu sein.|  
|[DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)|Deklariert [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), um die Klassenfactory zu sein.|  
|[DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)|Deklariert [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), um die Klassenfactory zu sein.|  
|[DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)|Deklariert [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), um die Klassenfactory zu sein.|  
|[DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md)|Deklariert eine virtuelle Funktion `GetControllingUnknown`.|  
|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|Deklariert, dass das Objekt nicht aggregiert werden kann.|  
|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|Deklariert, dass das Objekt aggregiert werden muss.|  
|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|Überprüft den Wert aus dem äußeren unbekannten und deklariert das Objekt aggregierbar oder nicht aggregierbar, bzw.|  
|[DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md)|Schützt das äußere Objekt vom Löschen während der Erstellung eines inneren Objekts.|  
|[DECLARE\_VIEW\_STATUS](../Topic/DECLARE_VIEW_STATUS.md)|Gibt die **VIEWSTATUS**\-Flags an den Container an.|  
  
## Siehe auch  
 [Macros](../../atl/reference/atl-macros.md)