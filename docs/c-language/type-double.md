---
title: "Typ „double“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 331e41cd5f333a1f2c628d50e6c4a34a3bc9dd96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-double"></a>Typ "double"
Werte mit doppelter Genauigkeit und doppeltem Typ besitzen 8 Bytes. Das Format ist ähnlich wie das Gleitkommaformat, außer dass es einen 11-Bit-Exponenten in Excess-1023-Notation und eine 52-Bit-Mantisse sowie das implizite höchstwertige 1 Bit hat. Dieses Format erlaubt einen Bereich von etwa 1.7E-308 bis 1.7E+308 für den Typ „double“.  
  
 **Microsoft-spezifisch**  
  
 Der Typ "double" enthält 64 Bit: 1 für das Zeichen, 11 für den Exponent und 52 für die Mantisse. Sein Bereich ist +/-1.7E308 mit mindestens 15 Dezimalstellen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)