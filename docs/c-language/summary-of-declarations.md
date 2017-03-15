---
title: Zusammenfassung der Deklarationen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
caps.latest.revision: 11
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: cf1442e98cdd7489a395bec211cda1bbb037bae2
ms.lasthandoff: 02/24/2017

---
# <a name="summary-of-declarations"></a>Zusammenfassung der Deklarationen
`declaration`:  
 *declaration-specifiers attribute-seq* opt*init-declarator-list*opt**;**  
  
 /\* *attribute-seq* ist Microsoft-spezifisch */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers*opt  
  
 *type-specifier declaration-specifiers*opt  
  
 *type-qualifier declaration-specifiers*opt  
  
 *attribute-seq* :            /\* *attribute-seq* ist Microsoft-spezifisch \*/  
 *attribute attribute-seq* opt  
  
 *attribute* : eines von      /* Microsoft-spezifisch \*/  
 ||||  
|-|-|-|  
|[__asm](../assembler/inline/asm.md)|[__clrcall](../cpp/clrcall.md)|[__stdcall](../cpp/stdcall.md)|  
|[__based](../cpp/based-grammar.md)|[__fastcall](../cpp/fastcall.md)|[__thiscall](../cpp/thiscall.md)|  
|[__cdecl](../cpp/cdecl.md)|[__inline](../cpp/inline-functions-cpp.md)|[__vectorcall](../cpp/vectorcall.md)|  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list*  **,**  *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* Für skalare Initialisierung \*/  
  
 *storage-class-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **__declspec (**  *extended-decl-modifier-seq*  **)** /* Microsoft-spezifisch \*/  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 `__int8` /* Microsoft-spezifisch \*/  
  
 `__int16` /* Microsoft-spezifisch \*/  
  
 `__int32` /* Microsoft-spezifisch \*/  
  
 `__int64` /* Microsoft-spezifisch \*/  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 *type-qualifier*:  
 **const**  
  
 `volatile`  
  
 `declarator`:  
 `pointer`opt*direct-declarator*  
  
 *direct-declarator*:  
 *identifier*  
  
 **(**  *declarator*  **)**  
  
 *direct-declarator*  **[**  *constant-expression* opt**]**  
  
 *direct-declarator*  **(**  *parameter-type-list*  **)** /* Neuer Deklarator \*/  
  
 *direct-declarator*  **(**  *identifier-list*opt**)** /* Veralteter Deklarator \*/  
  
 `pointer`:  
 **\*** *type-qualifier-list*opt  
  
 **\*** *type-qualifier-list*opt`pointer`  
  
 *parameter-type-list*:                           /\* Die Parameterliste \*/  
 *parameter-list*  
  
 *parameter-list* **, ...**  
  
 *parameter-list*:  
 *parameter-declaration*  
  
 *parameter-list*  **,**  *parameter-declaration*  
  
 *type-qualifier-list*:  
 *type-qualifier*  
  
 *type-qualifier-list type-qualifier*  
  
 *enum-specifier*:  
 **enum**  *identifier*opt**{** *enumerator-list* **}**  
  
 **enum**  *identifier*  
  
 *enumerator-list*:  
 *enumerator*  
  
 *enumerator-list*  **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration-constant*  
  
 *enumeration-constant*  **=**  *constant-expression*  
  
 *enumeration-constant*:  
 *identifier*  
  
 *struct-or-union-specifier*:  
 *struct-or-union identifier*opt**{** *struct-declaration-list* **}** *struct-or-union identifier*  
  
 *struct-or-union*:  
 **struct**  
  
 **union**  
  
 *struct-declaration-list*:  
 *struct-declaration*  
  
 *struct-declaration-list struct-declaration*  
  
 *struct-declaration*:  
 *specifier-qualifier-list struct-declarator-list*  **;**  
  
 *specifier-qualifier-list*:  
 *type-specifier specifier-qualifier-list*opt  
  
 *type-qualifier specifier-qualifier-list*opt  
  
 *struct-declarator-list*:  
 *struct-declarator struct-declarator-list*  **,**  *struct-declarator*  
  
 *struct-declarator*:  
 *declarator*  
  
 *type-specifier declarator*opt**:** *constant-expression*  
  
 *parameter-declaration*:  
 *declaration-specifiers declarator* /* Benannter Deklarator \*/  
  
 *declaration-specifiers abstract-declarator*opt**/\*** Anonymer Deklarator **\*/**  
  
 *identifier-list*: **/\*** Für alten Deklarator **\* /**  
 *identifier*  
  
 *identifier-list*  **,**  *identifier*  
  
 *abstract-declarator*: **/\*** Verwendet mit anonymen Deklaratoren **\*/**  
 *Zeiger*  
  
 `pointer`opt*direct-abstract-declarator*  
  
 *direct-abstract-declarator*:  
 **(**  *abstract-declarator*  **)**  
  
 *direct-abstract-declarator*opt**[** *constant-expression*opt**]**  
  
 *direct-abstract-declarator*opt**(** *parameter-type-list* opt**)**  
  
 *initializer*:  
 *assignment-expression*  
  
 **{**  *initializer-list*  **}** /* Für Aggregatinitialisierung \*/  
  
 **{**  *initializer-list*  **, }**  
  
 *initializer-list*:  
 *initializer*  
  
 *initializer-list*  **,**  *initializer*  
  
 *type-name*:  
 *specifier-qualifier-list abstract-declarator*opt  
  
 *typedef-name*:  
 *identifier*  
  
 *extended-decl-modifier-seq*:/\*    Microsoft-spezifisch \*/  
 *extended-decl-modifier*opt  
  
 *extended-decl-modifier-seq extended-decl-modifier*  
  
 *extended-decl-modifier*:   /\* Microsoft-spezifisch \*/  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)   
 [Phrasenstrukturgrammatik](../c-language/phrase-structure-grammar.md)   
 [Veraltete Aufrufkonventionen](../cpp/obsolete-calling-conventions.md)
