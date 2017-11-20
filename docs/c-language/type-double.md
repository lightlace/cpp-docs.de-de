---
title: "Typ „double“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aa4e81164a02774f7f9aa034f2c1a5492233600d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="type-double"></a>Typ "double"
Werte mit doppelter Genauigkeit und doppeltem Typ besitzen 8 Bytes. Das Format ist ähnlich wie das Gleitkommaformat, außer dass es einen 11-Bit-Exponenten in Excess-1023-Notation und eine 52-Bit-Mantisse sowie das implizite höchstwertige 1 Bit hat. Dieses Format erlaubt einen Bereich von etwa 1.7E-308 bis 1.7E+308 für den Typ „double“.  
  
 **Microsoft-spezifisch**  
  
 Der Typ "double" enthält 64 Bit: 1 für das Zeichen, 11 für den Exponent und 52 für die Mantisse. Sein Bereich ist +/-1.7E308 mit mindestens 15 Dezimalstellen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)