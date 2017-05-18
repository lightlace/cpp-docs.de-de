---
title: Datentypspezifizierer und Entsprechungen | Microsoft-Dokumentation
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
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
caps.latest.revision: 8
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: de625abc04fcfde9d39205d024f09dc64d6c82ae
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="data-type-specifiers-and-equivalents"></a>Datentypspezifizierer und Entsprechungen
In diesem Buch wird anstelle der langen Formen im Allgemeinen die Form der Typspezifizierer verwendet, die in der folgenden Tabelle aufgelistet sind, und es wird davon ausgegangen, dass der Typ `char` standardmäßig signiert ist. Daher entspricht in diesem Buch `char` **signed char**.  
  
### <a name="type-specifiers-and-equivalents"></a>Typspezifizierer und Entsprechungen  
  
|Typspezifizierer|Entsprechung(en)|  
|--------------------|---------------------|  
|**signed char**1|**char**|  
|**signed int**|**signed**, **int**|  
|**signed short int**|**short**, **signed short**|  
|**signed long int**|**long**, **signed long**|  
|**unsigned char**|—|  
|**unsigned int**|**unsigned**|  
|**unsigned short int**|**unsigned short**|  
|**unsigned long int**|**unsigned long**|  
|**float**|—|  
|**long double**2|—|  
  
 1. Wenn Sie den **char**-Typ standardmäßig auf „unsigned“ festlegen (durch Angabe der /J-Compileroption), können Sie **signed char** nicht als **char** abkürzen.  
  
 2. In 32-Bit- und 64-Bit-Betriebssystemen ordnet der Microsoft C-Compiler **long double** dem Typ **double** zu.  
  
 **Microsoft-spezifisch**  
  
 Sie können die /J-Compileroption angeben, um den standardmäßigen **char**-Typ von „signed“ in „unsigned“ zu ändern. Wenn diese Option aktiviert ist, hat **char** dieselbe Bedeutung wie **unsigned char**, und Sie müssen das Schlüsselwort **signed** verwenden, um einen Zeichenwert mit Vorzeichen angeben zu können. Wenn ein **char**-Wert explizit als „signed“ deklariert ist, hat die /J-Option keine Auswirkung darauf, und der Wert wird um das Vorzeichen erweitert, wenn er zu einem **int**-Typ erweitert wurde. Der **char**-Typ wird mit 0 (null) erweitert, wenn er auf den **int**-Typ erweitert wird.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Typspezifizierer](../c-language/c-type-specifiers.md)
