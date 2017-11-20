---
title: "Typ „char“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1046de3ca21cecf99c070a24a041e5c627d2961
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="type-char"></a>Typ "char"
Der `char`-Typ wird verwendet, um den ganzzahligen Wert eines Members des darstellbaren Zeichensatzes zu speichern. Dieser ganzzahlige Wert ist der ASCII-Code, der dem angegebenen Zeichen entspricht.  
  
 **Microsoft-spezifisch**  
  
 Zeichenwerte des Typs `unsigned char` haben einen Bereich von 0 bis zu den hexadezimalen Zahlen 0xFF. Ein **signed char** hat den Bereich 0x80 bis 0x7F. Diese Bereiche entsprechen 0 bis 255 dezimal bzw. -128 bis +127 dezimal. Die /J-Compileroption ändert den Standard von **signed** in `unsigned`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)