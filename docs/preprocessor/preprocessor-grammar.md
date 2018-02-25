---
title: "Präprozessor-Grammatik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b3597b035e3ea4bfa1670aa405109f4c01a077
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik
**#define***Bezeichner* *-Token-String*abonnieren    
  
 *#* **Definieren Sie***Bezeichner*[**(** *Bezeichner*opt**,** *...*  **,** *Bezeichner*opt **)**] *-Token-String*abonnieren    
  
 **definiert (***Bezeichner* **)**   
  
 **definiert***Bezeichner*   
  
 `#include` **"***Path-Spec***"**  
  
 `#include` **\<***path-spec***>**  
  
 **#line***Ziffernfolge***"** *Filename* **"**abonnieren      
  
 *#* **undef**  *identifier*  
  
 **#error***-Token-Zeichenfolge*   
  
 **#pragma**  *token-string*  
  
 *conditional* :  
 *If-Teil Elif-Teile*opt*else-Teil*opt*Endif-Zeile*  
  
 *If-Teil* :  
 *if-linetext*  
  
 *if-line* :  
 **#if***Konstantenausdruck*   
  
 **#ifdef**  *identifier*  
  
 **#ifndef***Bezeichner*   
  
 *Elif-Teile* :  
 *elif-line text*  
  
 *elif-parts elif-line text*  
  
 *elif-line* :  
 **#elif**  *constant-expression*  
  
 *else-Teil* :  
 *else-linetext*  
  
 *else-line* :  
 `#else`  
  
 *endif-line* :  
 `#endif`  
  
 *Ziffernfolge* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *Ziffer* : einer der  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *Token-String* :  
 Zeichenfolge von Tokens  
  
 *token* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *FileName* :  
 Gültiger Dateiname des Betriebssystems  
  
 *path-spec* :  
 Gültiger Dateipfad  
  
 *text* :  
 Eine beliebige Textsequenz  
  
> [!NOTE]
>  Die folgenden Nichtterminale werden der [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*: `constant`, `constant` - *Ausdruck* , *Bezeichner*, *Schlüsselwort*, `operator`, und `punctuator`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)