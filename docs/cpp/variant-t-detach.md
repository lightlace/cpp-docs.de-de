---
title: "_variant_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Detach"
  - "_variant_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach-Methode"
  - "VARIANT-Objekt"
  - "VARIANT-Objekt, detatch"
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _variant_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Trennt das gekapselte **VARIANT**\-Objekt von diesem `_variant_t`\-Objekt.  
  
## Syntax  
  
```  
  
VARIANT Detach( );  
  
```  
  
## Rückgabewert  
 Gekapseltes **VARIANT**\-Objekt.  
  
## Hinweise  
 Das gekapselte **VARIANT**\-Objekt wird extrahiert und zurückgegeben, nachfolgend wird das `_variant_t`\-Objekt geleert, ohne es zu löschen.  Diese Memberfunktion entfernt **VARIANT** aus der Kapselung und legt **VARTYPE** für dieses `_variant_t`\-Objekt auf `VT_EMPTY` fest.  Sie können entscheiden, ob Sie das zurückgegebene **VARIANT**\-Objekt durch den Aufruf der [VariantClear](assetId:///28741d81-8404-4f85-95d3-5c209ec13835)\-Funktion freigeben.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)