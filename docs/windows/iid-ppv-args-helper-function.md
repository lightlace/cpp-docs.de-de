---
title: "IID_PPV_ARGS_Helper-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/IID_PPV_ARGS_Helper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IID_PPV_ARGS_Helper-Funktion"
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IID_PPV_ARGS_Helper-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob der Typ des Arguments von der angegebenen `IUnknown`\-Schnittstelle abgeleitet wird.  
  
> [!IMPORTANT]
>  Diese Vorlagenspezialisierung unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  Verwendung [IID\_PPV\_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx).  
  
## Syntax  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### Parameter  
 `T`  
 Der Typ des Arguments `pp`.  
  
 `pp`  
 Ein doppelt\-indirekter Zeiger.  
  
## Rückgabewert  
 Argument `pp` wandelte zu einem Zeiger\-zu\-einZeiger in `void` um.  
  
## Hinweise  
 Ein Fehler wird generiert, wenn der Vorlagenparameter `T` nicht von `IUnknown` abgeleitet.  
  
## Anforderungen  
 **Header:**  client.h  
  
## Siehe auch  
 [Reference \(Windows Runtime Library\)](assetId:///00000000-0000-0000-0000-000000000000)