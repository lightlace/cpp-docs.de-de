---
title: Typ „double“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0eb8fb3952b1825bff730d5d22222b56cdb4ecf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="type-double"></a>Typ "double"
Werte mit doppelter Genauigkeit und doppeltem Typ besitzen 8 Bytes. Das Format ist ähnlich wie das Gleitkommaformat, außer dass es einen 11-Bit-Exponenten in Excess-1023-Notation und eine 52-Bit-Mantisse sowie das implizite höchstwertige 1 Bit hat. Dieses Format erlaubt einen Bereich von etwa 1.7E-308 bis 1.7E+308 für den Typ „double“.  
  
 **Microsoft-spezifisch**  
  
 Der Typ "double" enthält 64 Bit: 1 für das Zeichen, 11 für den Exponent und 52 für die Mantisse. Sein Bereich ist +/-1.7E308 mit mindestens 15 Dezimalstellen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)