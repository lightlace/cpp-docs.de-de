---
title: "Präprozessor-Grammatik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c64c5a1855d80d5abc60d959bd68b33a380583b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik
**#define***Bezeichner* *-Token-String*abonnieren    
  
 *#***definieren***Bezeichner*[**(** *Bezeichner*opt**,** *...*  **,** *Bezeichner*opt **)**] *-Token-String*abonnieren    
  
 **definiert (***Bezeichner* **)**   
  
 **definiert***Bezeichner*   
  
 `#include`**"***Path-Spec***"**  
  
 `#include` **\<**  *Path-Spec***>**  
  
 **#line***Ziffernfolge***"** *Filename* **"**abonnieren      
  
 *#***Undef***Bezeichner*   
  
 **#error***-Token-Zeichenfolge*   
  
 **#pragma***-Token-Zeichenfolge*   
  
 *bedingte* :  
 *If-Teil Elif-Teile*opt*else-Teil*opt*Endif-Zeile*  
  
 *If-Teil* :  
 *If-linetext*  
  
 *If-Line-* :  
 **#if***Konstantenausdruck*   
  
 **#ifdef***Bezeichner*   
  
 **#ifndef***Bezeichner*   
  
 *Elif-Teile* :  
 *Elif-Line-text*  
  
 *Elif-Teile Elif-Line-text*  
  
 *Elif-Line-* :  
 **#elif***Konstantenausdruck*   
  
 *else-Teil* :  
 *Else-linetext*  
  
 *Else-Line* :  
 `#else`  
  
 *Endif-Line-* :  
 `#endif`  
  
 *Ziffernfolge* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *Ziffer* : einer der  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *Token-String* :  
 Zeichenfolge von Tokens  
  
 *Token* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *FileName* :  
 Gültiger Dateiname des Betriebssystems  
  
 *Path-Spec* :  
 Gültiger Dateipfad  
  
 *Text* :  
 Eine beliebige Textsequenz  
  
> [!NOTE]
>  Die folgenden Nichtterminale werden der [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*: `constant`, `constant` - *Ausdruck* , *Bezeichner*, *Schlüsselwort*, `operator`, und `punctuator`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)