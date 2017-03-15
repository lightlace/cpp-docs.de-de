---
title: "_variant_t::ChangeType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::ChangeType"
  - "_variant_t.ChangeType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChangeType-Methode"
  - "VARIANT-Objekt"
  - "VARIANT-Objekt, ChangeType"
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::ChangeType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ändert den Typ des `_variant_t`\-Objekts in den angegebenen **VARTYPE**.  
  
## Syntax  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### Parameter  
 `vartype`  
 Der **VARTYPE** für dieses `_variant_t`\-Objekt.  
  
 `pSrc`  
 Ein Zeiger auf das `_variant_t`\-Objekt, das umgewandelt werden soll.  Wenn dieser Wert **NULL** ist, wird die Konvertierung direkt ausgeführt.  
  
## Hinweise  
 Diese Memberfunktion konvertiert ein `_variant_t`\-Objekt in das angegebene **VARTYPE**.  Wenn `pSrc` **NULL** ist, erfolgt die Konvertierung direkt. Andernfalls wird dieses `_variant_t`\-Objekt von `pSrc` kopiert und dann konvertiert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)