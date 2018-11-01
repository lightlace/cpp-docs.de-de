---
title: Präprozessor-Grammatik
ms.date: 09/04/2018
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: 17768b7ec1442f2af1abf76596527d4df69b1534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614187"
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik

*Steuerelement-Line-*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *Bezeichner* *-Token-Zeichenfolge*<sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>Bezeichner</em>**(** *Bezeichner*<sub>opt</sub> **,** ... **,** *Bezeichner*<sub>opt</sub> **)** *-Token-Zeichenfolge*<sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *Path-Spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *Path-Spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *Ziffernfolge***"** *Filename* **"**<sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#undef** *Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#error** *-Token-Zeichenfolge*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#pragma** *-Token-Zeichenfolge*

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**definiert (** *Bezeichner* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**definiert** *Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;ein anderer konstanter Ausdruck

*bedingte* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*If-Part* *Elif-Teile*<sub>opt</sub> *else-Teil*<sub>opt</sub> *Endif-Zeile*

*If-Part* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*If-Line-* *Text*

*If-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if** *konstanter Ausdruck*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef** *Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef** *Bezeichner*

*Elif-Teile* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Elif-Line-* *Text*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Elif-Teile* *Elif-Line-* *Text*

*Elif-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif** *konstanter Ausdruck*

*else-Teil* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Else-Line* *Text*

*Else-Line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*Endif-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

*Digit-Sequence* :<br/>
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