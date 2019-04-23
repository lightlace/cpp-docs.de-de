---
title: Präprozessor-Grammatik
ms.date: 09/04/2018
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: 6177cf5fddba549e410842ef3f270edcc13d4782
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032413"
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik

*control-line*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *identifier* *token-string*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>identifier</em>**(** *identifier*<sub>opt</sub> **,** ... **,** *identifier*<sub>opt</sub> **)** *token-string*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *path-spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *path-spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *digit-sequence*  **"** *filename* **"**<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#undef** *Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#error** *token-string*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#pragma** *token-string*

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**definiert (** *Bezeichner* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**definiert** *Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;ein anderer konstanter Ausdruck

*bedingte* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if-part* *elif-parts*<sub>opt</sub> *else-part*<sub>opt</sub> *endif-line*

*If-Part* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if-line* *text*

*If-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if** *constant-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef** *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef** *identifier*

*Elif-Teile* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif-line* *text*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif-parts* *elif-line* *text*

*elif-line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif** *constant-expression*

*else-Teil* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*else-line* *text*

*Else-Line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*Endif-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

*digit-sequence* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*Ziffer* : eines der<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*Token-Zeichenfolge* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Zeichenfolge von tokens

*Token* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*keyword*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*operator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*FileName* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Rechtliche Betriebssystem-Dateiname

*Path-Spec* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Gültiger Dateipfad

*Text* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Eine beliebige Sequenz von text

> [!NOTE]
> Die folgenden Nichtterminale werden in der [lexikalische Konventionen](../cpp/lexical-conventions.md) Teil der *C++-Sprachreferenz*: *Konstanten*, *konstanter Ausdruck* , *Bezeichner*, *Schlüsselwort*, *Operator*, und *Punctuator*.

## <a name="see-also"></a>Siehe auch

[Grammatikzusammenfassung (C/C++)](../preprocessor/grammar-summary-c-cpp.md)