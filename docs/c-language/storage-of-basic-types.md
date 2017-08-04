---
title: Speicherung von einfachen Typen | Microsoft-Dokumentation
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
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5a42f5c0e4592fc397ac51d610ed6ca1495c4504
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="storage-of-basic-types"></a>Speicherung von einfachen Typen
In der folgenden Tabelle wird der Speicher zusammengefasst, welcher jedem Basistyp zugeordnet ist.  
  
### <a name="sizes-of-fundamental-types"></a>Größen von grundlegenden Typen  
  
|Typ|Speicher|  
|----------|-------------|  
|`char`, `unsigned char`, **char mit Vorzeichen**|1 Byte|  
|**short**, **unsigned short**|2 Bytes|  
|`int`, `unsigned int`|4 Bytes|  
|**long**, `unsigned long`|4 Bytes|  
|**float**|4 Bytes|  
|**double**|8 Bytes|  
|`long double`|8 Bytes|  
  
 Die C-Datentypen fallen in allgemeine Kategorien. Die „ganzzahligen Typen“ enthalten `char`, `int`, **short**, **long**, **signed**, `unsigned` und `enum`. Die „Gleitkommatypen“ enthalten **float**, **double** und `long double`. Die "arithmetischen Typen" umfassen alle Gleitkomma- und Ganzzahltypen.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)
