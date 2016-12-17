---
title: "Pr&#228;prozessorgrammatik"
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
  - "Grammatik, Präprozessor"
  - "Präprozessor"
  - "Präprozessor, Grammatik"
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Pr&#228;prozessorgrammatik
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#define**  *identifier* *token\-string*opt  
  
 *\#* **define**  *identifier*\[**\(** *identifier*opt**,** *...* **,** *identifier*opt **\)**\] *token\-string*opt  
  
 **defined\(**  *identifier* **\)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path\-spec***"**  
  
 `#include` **\<***path\-spec***\>**  
  
 **\#line**  *digit\-sequence*  **"** *filename* **"** opt  
  
 *\#* **undef**  *identifier*  
  
 **\#error**  *token\-string*  
  
 **\#pragma**  *token\-string*  
  
 *conditional* :  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part* :  
 *if\-linetext*  
  
 *if\-line* :  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts* :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line* :  
 **\#elif**  *constant\-expression*  
  
 *else\-part* :  
 *else\-linetext*  
  
 *else\-line* :  
 `#else`  
  
 *endif\-line* :  
 `#endif`  
  
 *digit\-sequence* :  
 *digit*  
  
 *digit\-sequence\-Stelle*  
  
 *digit* : Eine von:  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *token\-string* :  
 Zeichenfolge von Tokens  
  
 *token* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename* :  
 Gültiger Dateiname des Betriebssystems  
  
 *path\-spec* :  
 Gültiger Dateipfad  
  
 *text* :  
 Eine beliebige Textsequenz  
  
> [!NOTE]
>  Die folgenden Nichtterminale werden in Anhang A, [Zusammenfassung der Grammatik](../misc/grammar-summary-cpp.md), der *C\+\+\-Programmiersprachenreferenz* weiter ausgeführt: `constant`, `constant`\-*expression*, *identifier*, *keyword*, `operator` und `punctuator`.  
  
## Siehe auch  
 [Grammatikzusammenfassung](../preprocessor/grammar-summary-c-cpp.md)