---
title: "Typ &quot;double&quot; | Microsoft Docs"
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
  - "double-Datentyp"
  - "Mantissen, Gleitkommavariablen"
  - "Portabilität [C++], Typ "double""
  - "Typ "double""
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Typ &quot;double&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Werte mit doppelter Genauigkeit und doppeltem Typ besitzen 8 Bytes.  Das Format ist ähnlich wie das Gleitkommaformat, außer dass es einen 11\-Bit\-Exponenten in Excess\-1023\-Notation und eine 52\-Bit\-Mantisse sowie das implizite höchstwertige 1 Bit hat.  Dieses Format erlaubt einen Bereich von etwa 1.7E\-308 bis 1.7E\+308 für den Typ "double".  
  
 **Microsoft\-spezifisch**  
  
 Der Typ "double" enthält 64 Bit: 1 für das Zeichen, 11 für den Exponent und 52 für die Mantisse.  Sein Bereich ist \+\/–1.7E308 mit mindestens 15 Dezimalstellen.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)