---
title: Präprozessor-Grammatik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d14a3e00e18a2d3ac69dd472ac4056a379ada224
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843365"
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik
**#define***Bezeichner* *-Token-String*abonnieren  
  
 *#* **Definieren Sie***Bezeichner*[**(** *Bezeichner*opt **,** *...*  **,** *Bezeichner*opt **)**] *-Token-String*abonnieren  
  
 **definiert (***Bezeichner* **)**  
  
 **definiert***Bezeichner*  
  
 `#include` **"***Path-Spec***"**  
  
 `#include` **\<***Path-spec***>**  
  
 **#line***Ziffernfolge***"** *Filename* **"** abonnieren  
  
 *#* **Undef***Bezeichner*   
  
 **#error***-Token-Zeichenfolge*  
  
 **#pragma***-Token-Zeichenfolge*   
  
 *bedingte* :  
 *If-Teil Elif-Teile*opt*else-Teil*opt*Endif-Zeile*  
  
 *If-Teil* :  
 *if-linetext*  
  
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
 *else-linetext*  
  
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