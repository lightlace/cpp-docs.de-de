---
title: "Changing the Default Class Factory and Aggregation Model | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "aggregation [C++], Mit ATL"
  - "CComClassFactory class, making the default"
  - "CComCoClass class, default class factory and aggregation model"
  - "class factories, Ändern der Standardwerte"
  - "default class factory"
  - "default class factory, ATL"
  - "Standardwerte [C++], aggregation model in ATL"
  - "Standardwerte [C++], class factory"
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Changing the Default Class Factory and Aggregation Model
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL\-Verwendung [CComCoClass](../atl/reference/ccomcoclass-class.md), die Standardklassenfactory und \-Aggregation definieren modelliert für das Objekt.  `CComCoClass` gibt die folgenden zwei Makros an:  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) deklariert die Klassenfactory, um [CComClassFactory](../atl/reference/ccomclassfactory-class.md) zu sein.  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) deklariert, dass das Objekt aggregiert werden kann.  
  
 Sie können einen dieser Vorgaben überschreiben, indem Sie ein anderes Makro in der Klassendefinition angeben.  Um beispielsweise [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) anstelle `CComClassFactory` zu verwenden, geben Sie die [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)\-Makro an:  
  
 [!CODE [NVC_ATL_COM#2](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#2)]  
  
 Zwei andere Makros, die eine Klassenfactory definieren, sind [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) und [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md).  
  
 ATL verwendet auch den `typedef` Mechanismus, um Standardverhalten zu implementieren.  Zum Beispiel verwendet das `DECLARE_AGGREGATABLE`\-Makro `typedef`, um einen Typ zu definieren, der **\_CreatorClass** aufgerufen wird, der während ATL verwiesen wird.  Beachten Sie das in einer abgeleiteten Klasse, `typedef` mithilfe der gleichen Namen, den `typedef` der Basisklasse ATL mit der Definition und für das Überschreiben des Standardverhaltens ergibt.  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)