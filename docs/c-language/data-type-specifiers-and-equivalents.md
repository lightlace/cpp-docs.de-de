---
title: "Datentypspezifizierer und Entsprechungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Datentypen [C++], Entsprechungen"
  - "Datentypen [C++], Bezeichner"
  - "Bezeichner, Datentyp"
  - "Zeichenerweiterung von ganzzahligen Typen"
  - "Einfache Typen, Namen"
  - "Typnamen [C++], Einfach"
  - "Typspezifizierer [C++], Liste"
  - "Erweitern von Ganzzahlen"
  - "Nullerweiterung"
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Datentypspezifizierer und Entsprechungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Buch wird anstelle der langen Formen im Allgemeinen die Form der Typspezifizierer verwendet, die in der folgenden Tabelle aufgelistet sind, und es wird davon ausgegangen, dass der Typ `char` standardmäßig signiert ist.  Daher entspricht in diesem Buch `char` **signed char**.  
  
### Typspezifizierer und Entsprechungen  
  
|Typspezifizierer|Entsprechung\(en\)|  
|----------------------|------------------------|  
|**signed char**1|`char`|  
|**signed int**|**signed**, `int`|  
|**signed short int**|**short**, `signed short`|  
|**signed long int**|**long**, **signed long**|  
|`unsigned char`|—|  
|`unsigned int`|`unsigned`|  
|**unsigned short int**|**unsigned short**|  
|**unsigned long int**|`unsigned long`|  
|**float**|—|  
|`long double`2|—|  
  
 1   Wenn Sie den `char`\-Typ standardmäßig als nicht signiert ausführen \(durch Angabe der \/J\-Compileroption\), können Sie **signed char** nicht als `char` abkürzen.  
  
 2   in 32\-Bit\-Betriebssystemen ordnet der Microsoft C\-Compiler **long double**  dem Typ **double** zu.  
  
 **Microsoft\-spezifisch**  
  
 Sie können die \/J\-Compileroption angeben, um den standardmäßigen `char`\-Typ von signiert in nicht signiert zu ändern.  Wenn diese Option aktiviert ist, hat `char` dieselbe Bedeutung wie `unsigned char`, und Sie müssen das **signed**\-Schlüsselwort verwenden, um einen signierten Zeichenwert anzugeben.  Wenn ein `char`\-Wert explizit als signiert deklariert ist, hat die \/J\-Option keine Auswirkung darauf, und der Wert wird um das Vorzeichen erweitert, wenn er zu einem `int`\-Typ erweitert wurde.  Der `char`\-Typ wird mit Null erweitert, wenn er auf den `int`\-Typ erweitert wird.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Typspezifizierer](../c-language/c-type-specifiers.md)