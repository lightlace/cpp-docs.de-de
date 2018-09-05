---
title: Präprozessor-Grammatik | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/04/2018
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
ms.openlocfilehash: 56df4d0bfdaf87ace87a9f9dcbde85166929e642
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766115"
---
# <a name="preprocessor-grammar"></a>Präprozessor-Grammatik

*Steuerelement-Line-*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** *Bezeichner* *-Token-Zeichenfolge*<sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#define** <em>Bezeichner</em>**(** *Bezeichner*<sub>opt</sub> **,** ... **,** *Bezeichner*<sub>opt</sub> **)** *-Token-Zeichenfolge*<sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **"** *Path-Spec* **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#include** **\<** *Path-Spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#line** *Ziffernfolge***"** *Filename* **"**<sub>deaktivieren  </sub><br/>
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
&nbsp;&nbsp;&nbsp;&nbsp;*Ziffer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Digit-Sequence* *Ziffer*

*Ziffer* : eines der<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*Token-Zeichenfolge* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Zeichenfolge von tokens

*Token* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Schlüsselwort*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Konstante*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Operator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Markierungszeichen*

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