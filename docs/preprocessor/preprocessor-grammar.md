---
title: Präprozessorgrammatik
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
ms.openlocfilehash: f0916e3cc9bbdb398db693286dacc4517df03557
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222261"
---
# <a name="preprocessor-grammar"></a>Präprozessorgrammatik

*Steuerungs Zeile*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *Bezeichner* *Tokenzeichenfolge* <sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#define** *Bezeichner* **(** &#x2800;&#x200B;<sub>bezeichneropt</sub> **,** ... **,** *Bezeichner* &#x200B; <sub></sub>opt&#x2800; **)** *Token-Zeichen*folgen<sub>opt</sub>\
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **"** _Pfadspezifikation_ **"** \
&nbsp;&nbsp;&nbsp;&nbsp; **#include** **\<** _Pfadspezifikation_ **>** \
&nbsp;&nbsp;&nbsp;&nbsp; **#Line** *Ziffern Sequenz* **"** _Dateiname_ **"** &#x200B; <sub>opt</sub>  \
&nbsp;&nbsp;&nbsp;&nbsp; **#undef** *Bezeichner*\
&nbsp;&nbsp;&nbsp;&nbsp; **#Error** *Tokenzeichenfolge*\
&nbsp;&nbsp;&nbsp;&nbsp; **#pragma** *token-string*

*Constant-Expression*: \
&nbsp;&nbsp;&nbsp;&nbsp;**definiert (** &#x2800;*Bezeichner*&#x2800; **)** \
&nbsp;&nbsp;&nbsp;&nbsp;**definiert** *Bezeichner*\
&nbsp;&nbsp;&nbsp;&nbsp;beliebiger anderer konstanter Ausdruck

*bedingt*: \
&nbsp;&nbsp;&nbsp;&nbsp;*if-Part* *elif-Parts* <sub>opt</sub> *else-Part* <sub>opt</sub> *EndIf-Zeile*

*if-Part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*if-Line* *Text*

*if-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#if** *Constant-Expression*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifdef** *Bezeichner*\
&nbsp;&nbsp;&nbsp;&nbsp; **#ifndef** *Bezeichner*

*elif-Parts*: \
&nbsp;&nbsp;&nbsp;&nbsp;*elif-Line* *Text*\
&nbsp;&nbsp;&nbsp;&nbsp;*elif-Parts* *elif-Line* *Text*

*elif-Line*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#elif** *Constant-Expression*

*else-Part*: \
&nbsp;&nbsp;&nbsp;&nbsp;*else-Zeile* *Text*

*else-Zeile*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#else**

*EndIf-Zeile*: \
&nbsp;&nbsp;&nbsp;&nbsp; **#endif**

*Ziffern Sequenz*: \
&nbsp;&nbsp;&nbsp;&nbsp;*mittleren*\
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*Ziffer*: eine von \
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

*Tokenzeichenfolge*: \
&nbsp;&nbsp;&nbsp;&nbsp;Zeichenfolge von Token

*Token*: \
&nbsp;&nbsp;&nbsp;&nbsp;*Schlüsselwort*\
&nbsp;&nbsp;&nbsp;&nbsp;*Figur*\
&nbsp;&nbsp;&nbsp;&nbsp;*Bend*\
&nbsp;&nbsp;&nbsp;&nbsp;*KOM*\
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*Dateiname*: \
&nbsp;&nbsp;&nbsp;&nbsp;Gültiger Dateiname des Betriebssystems

*Pfadspezifikation*: \
&nbsp;&nbsp;&nbsp;&nbsp;Gültiger Dateipfad

*Text*: \
&nbsp;&nbsp;&nbsp;&nbsp;Beliebige Text Sequenz

> [!NOTE]
> Die folgenden nicht terminale werden im Abschnitt ["lexikalische Konventionen](../cpp/lexical-conventions.md) " der  *C++ Sprachreferenz*erweitert: *Konstante*, *konstanter Ausdruck*, Bezeichner, *Schlüsselwort*, *Operator*und  *interpunktionator*.

## <a name="see-also"></a>Siehe auch

[Grammatik Zusammenfassung (CC++/)](../preprocessor/grammar-summary-c-cpp.md)
