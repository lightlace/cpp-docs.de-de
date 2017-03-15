---
title: "_bstr_t::GetAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::GetAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddress-Methode"
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _bstr_t::GetAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Setzt etwaig vorhandene Zeichenfolgen frei und gibt die Adresse einer neu zugeordneten Zeichenfolge zurück.  
  
## Syntax  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## Rückgabewert  
 Ein Zeiger auf den `BSTR` umschlossen von `_bstr_t`.  
  
## Hinweise  
 `GetAddress` wirkt sich auf alle `_bstr_t`\-Objekte aus, die ein `BSTR` freigeben.  Mehr als eine `_bstr_t` kann eine `BSTR` durch die Verwendung des Kopierkonstruktors und des `operator=` freigeben.  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `GetAddress` finden Sie unter [\_bstr\_t::Assign](../cpp/bstr-t-assign.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)