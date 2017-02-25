---
title: "_pAtlModule | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLBASE/_pAtlModule"
  - "_pAtlModule"
  - "ATL::_pAtlModule"
  - "ATL._pAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pAtlModule variable"
  - "pAtlModule variable"
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# _pAtlModule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine globale Variable, die einen Zeiger auf das aktuelle Modul speichert.  
  
## Syntax  
  
```  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
  
## Hinweise  
 Methoden auf dieser globalen Variable können verwendet werden, um die Funktionen bereitzustellen, dass Sie jetzt die \(veraltet\), Klasse [CComModule](../../atl/reference/ccommodule-class.md) in Visual C\+\+ 6.0 bereitgestellt werden.  
  
## Beispiel  
 [!CODE [NVC_ATL_Windowing#97](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#97)]  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Global Variables](../../atl/reference/atl-global-variables.md)