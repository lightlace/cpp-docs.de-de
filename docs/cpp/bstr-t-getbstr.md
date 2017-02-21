---
title: "_bstr_t::GetBSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "GetBSTR"
  - "_bstr_t::GetBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBSTR-Methode"
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::GetBSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Zeigt auf den Anfang des `BSTR`, das vom `_bstr_t` umschlossen ist.  
  
## Syntax  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## Rückgabewert  
 Der Anfang des `BSTR`, der vom `_bstr_t` umschlossen ist.  
  
## Hinweise  
 `GetBSTR` wirkt sich auf alle `_bstr_t`\-Objekte aus, die ein `BSTR` freigeben.  Mehr als eine `_bstr_t` kann eine `BSTR` durch die Verwendung des Kopierkonstruktors und des `operator=` freigeben.  
  
## Beispiel  
 Unter [\_bstr\_t::Assign](../cpp/bstr-t-assign.md) finden Sie ein Beispiel für die Verwendung von `GetBSTR`.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)