---
title: "Implementing CComObjectRootEx"
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
  - "CComObjectRootEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class, Implementieren"
  - "CComObjectRootEx class"
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing CComObjectRootEx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) ist wesentlich; alle ATL\-Objekte müssen über eine Instanz von `CComObjectRootEx` oder [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) bei der Vererbung verfügen.  `CComObjectRootEx` bietet den standardmäßigen `QueryInterface`\-Mechanismus basierend auf COM\-Zuordnungseinträgen.  
  
 Über die COM\-Zuordnung sind die Schnittstellen eines Objekts für einen Client verfügbar, wenn der Client nach einer Schnittstelle fragt.  Die Abfrage wird mittels `CComObjectRootEx::InternalQueryInterface` durchgeführt.  `InternalQueryInterface` verarbeitet nur Schnittstellen in der COM\-Zuordnungstabelle.  
  
 Mit dem Makro [COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20\(ATL\).md) oder mit einer dessen Varianten können Sie Schnittstellen in die COM\-Zuordnungstabelle eingeben.  Mit dem folgenden Code werden beispielsweise die Schnittstellen `IDispatch`, `IBeeper` und `ISupportErrorInfo` in die COM\-Zuordnungstabelle eingegeben:  
  
 [!CODE [NVC_ATL_COM#1](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#1)]  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [COM Map Macros](../atl/reference/com-map-macros.md)