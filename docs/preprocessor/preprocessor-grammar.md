---
title: Präprozessor-Grammatik | Microsoft-Dokumentation
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
ms.openlocfilehash: 1871d1b8281f4dd74733133ede70ed80430246b3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539421"
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik
**#define***Bezeichner* *-Token-Zeichenfolge*deaktivieren    
  
*#* **Definieren Sie***Bezeichner*[**(** *Bezeichner*opt **,** *...*  **,** *Bezeichner*opt **)**] *-Token-Zeichenfolge*deaktivieren    
  
**definiert (***Bezeichner* **)**   
  
**definiert***Bezeichner*   
  
`#include` **"***Path-Spec***"**  
  
`#include` **\<***Path-spec***>**  
  
**#line***Ziffernfolge***"** *Filename* **"** deaktivieren      
  
*#* **Undef***Bezeichner*   
  
**#error***-Token-Zeichenfolge*   
  
**#pragma***-Token-Zeichenfolge*   
  
*bedingte* :  
*Elif Teile von If-Part*opt*else-Teil*opt*Endif-Zeile*  
  
*If-Part* :  
*if-linetext*  
  
*If-Line-* :  
**#if***konstanter Ausdruck*  
  
**#ifdef***Bezeichner*  
  
**#ifndef***Bezeichner*  
  
*Elif-Teile* :  
*Elif-Line text*  
  
*Elif-Teile Elif-Line text*  
  
*Elif-Line-* :  
**#elif***konstanter Ausdruck*  
  
*else-Teil* :  
*else-linetext*  
  
*Else-Line* :  
`#else`  
  
*Endif-Line-* :  
`#endif`  
  
*Digit-Sequence* :  
*digit*  
  
*digit-sequence digit*  
  
*Ziffer* : eines der  
**0 1 2 3 4 5 6 7 8 9**  
  
*Token-Zeichenfolge* :  
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
> Die folgenden Nichtterminale werden in der [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*: `constant`, `constant` - *Ausdruck* , *Bezeichner*, *Schlüsselwort*, `operator`, und `punctuator`.  
  
## <a name="see-also"></a>Siehe auch  
 
[Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)