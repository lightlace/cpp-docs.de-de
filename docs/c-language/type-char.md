---
title: "Typ „char“ | Microsoft-Dokumentation"
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
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9e3df3b4fd3e2763ef1704133cb111ee8ac067e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-char"></a>Typ "char"
Der `char`-Typ wird verwendet, um den ganzzahligen Wert eines Members des darstellbaren Zeichensatzes zu speichern. Dieser ganzzahlige Wert ist der ASCII-Code, der dem angegebenen Zeichen entspricht.  
  
 **Microsoft-spezifisch**  
  
 Zeichenwerte des Typs `unsigned char` haben einen Bereich von 0 bis zu den hexadezimalen Zahlen 0xFF. Ein **signed char** hat den Bereich 0x80 bis 0x7F. Diese Bereiche entsprechen 0 bis 255 dezimal bzw. -128 bis +127 dezimal. Die /J-Compileroption ändert den Standard von **signed** in `unsigned`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)