---
title: Numerisch, Boolean und Zeigerliterale (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- literals, C++
- constants, literals
- literals
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
caps.latest.revision: 16
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5c4a9a7aca2f11956e0ba47cced37a86733dcce8
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="numeric-boolean-and-pointer-literals--c"></a>Numerisch, Boolean und Zeigerliterale (C++)
Bei einem Literal handelt es sich um ein Programmelement, das direkt einen Wert darstellt. In diesem Artikel werden Literale der Typen Ganzzahl, Gleitkomma, Boolesch und Zeiger erläutert. Informationen über Zeichenfolgen- und Zeichenliterale finden Sie unter [Zeichenfolgen und Zeichen Literale (C++)](../cpp/string-and-character-literals-cpp.md). Sie können auch Ihre eigenen Literale auf Grundlage dieser Kategorien definieren; Weitere Informationen finden Sie unter [benutzerdefinierte Literale (C++)](../cpp/user-defined-literals-cpp.md)  
  
 . Sie können Literale in vielen Kontexten verwenden, aber am häufigsten zum Initialisieren von benannten Variablen und zum Weitergeben der Argumente an Funktionen:  
  
```  
const int answer = 42; // integer literal  
double d = sin(108.87);     //floating point literal passed to sin function  
bool b = true;              // boolean literal  
MyClass* mc = nullptr;      // pointer literal  
  
```  
  
 In manchen Fällen ist es wichtig, dem Compiler darüber zu informieren, wie er ein Literal interpretieren soll oder welcher bestimmte Typ ihm erteilt werden soll. Dies setzen Sie um, indem Sie Prä- und Suffixe an das Literal anfügen. Beispielsweise informiert das Präfix „0x“ den Compiler darüber, die darauffolgende Zahl als einen hexadezimalen Wert, beispielsweise „0x35“, zu interpretieren. Das ULL-Suffix informiert den Compiler darüber, den Wert als einen `unsigned long long`-Typ wie in 5894345ULL zu behandeln. In den folgenden Abschnitten finden Sie die vollständige Liste der Prä- und Suffixe für jeden Literaltyp.  
  
## <a name="syntax"></a>Syntax  
  
## <a name="integer-literals"></a>Ganzzahlenliteral  
 Ganzzahlenliterale beginnen mit einer Ziffer und weisen weder Bruchteile noch Exponenten auf. Sie können Integerliterale im Dezimal-, Oktal- oder Hexadezimalformat angeben. Sie können Typen mit oder ohne Vorzeichen und lange oder kurze Typen angeben.  
  
 Wenn weder ein Prä- noch ein Suffix vorhanden ist, weist der Compiler einen integralen `int`-Literalwerttyp (32 Bit) zu, wenn der Wert passt, ansonsten weist er einen `long long`-Typ (64 Bit) zu.  
  
 Starten Sie zum Angeben eines integralen Dezimalliterals die Spezifikation mit einer Ziffer ungleich 0. Zum Beispiel:  
  
```  
int i = 157;   // Decimal literal  
int j = 0198;       // Not a decimal number; erroneous octal literal  
int k = 0365;       // Leading zero specifies octal literal, not decimal  
int m = 36'000'000  // digit separators make large values more readable  
int   
```  
  
 Um ein oktales Integralliteral anzugeben, beginnen Sie die Angabe mit 0, gefolgt von einer Ziffernfolge im Bereich von 0 bis 7. Die Ziffern 8 und 9 sind Fehler, wenn sie ein oktales Literal angeben. Zum Beispiel:  
  
```  
int i = 0377;   // Octal literal  
int j = 0397;        // Error: 9 is not an octal digit  
```  
  
 Um eine integrale Hexadezimalliterale anzugeben, beginnen Sie die Angabe mit `0x` oder `0X` (die Groß-/Kleinschreibung von "x" ist nicht relevant), gefolgt von einer Ziffernfolge im Bereich `0` bis `9` und `a` (oder `A`) bis `f` (oder `F`). Hexadezimalzahlen `a` (oder `A`) bis `f` (oder `F`) stellen Werte im Bereich von 10 bis 15 dar. Zum Beispiel:  
  
```  
int i = 0x3fff;   // Hexadecimal literal  
int j = 0X3FFF;        // Equal to i  
```  
  
 Um einen Typ ohne Vorzeichen anzugeben, verwenden Sie entweder die **u** oder **U** Suffix. Um einen langen Typ anzugeben, verwenden Sie entweder die **l** oder **L** Suffix. Um einen integralen 64-Bit-Typ anzugeben, verwenden Sie das Suffix „LL“ oder „ll“. Das Suffix „i64“ wird weiterhin unterstützt, sollte jedoch vermieden werden, da es für Microsoft spezifisch und nicht übertragbar ist. Zum Beispiel:  
  
```  
unsigned val_1 = 328u;             // Unsigned value  
long val_2 = 0x7FFFFFL;                 // Long value specified   
                                        //  as hex literal  
unsigned long val_3 = 0776745ul;        // Unsigned long value  
auto val_4 = 108LL;                           // signed long long  
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long   
```  
  
 **Zahlentrennzeichen**: können Sie das einfache Anführungszeichen (Apostroph) zum Trennen der Werte in größere Zahlen zur besseren Lesbarkeit. Trennzeichen haben keine Auswirkungen auf die Kompilierung.  
  
```  
long long i = 24'847'458'121  
```  
  
## <a name="floating-point-literals"></a>Gleitkommaliterale  
 Gleitkommaliterale geben Werte an, die Nachkommastellen aufweisen müssen. Diese Werte enthalten Dezimaltrennzeichen (**.**) und können Exponenten enthalten.  
  
 Gleitkommaliterale haben eine „Mantisse“, die den Wert der Zahl angibt, einen „Exponenten“, der die Größe der Zahl angibt, und ein optionales Suffix, das den Literaltyp angibt. Die Mantisse wird wie folgt angegeben: eine Ziffernsequenz, gefolgt von einem Punkt, gefolgt von einer optionalen Ziffernsequenz, die die Nachkommastellen der Zahl darstellen. Beispiel:  
  
```  
18.46  
38.  
```  
  
 Sofern vorhanden, gibt der Exponent die Größe der Zahl als Zehnerpotenz an (siehe folgendes Beispiel):  
  
```  
18.46e0      // 18.46  
18.46e1           // 184.6  
```  
  
 Der Exponent kann angegeben werden, mithilfe von **e** oder **E**, haben dieselben Bedeutung, gefolgt von einem optionalen Vorzeichen (+ oder -) und einer Folge von Ziffern.  Wenn ein Exponent vorhanden ist, ist das nachfolgende Dezimaltrennzeichen in ganzen Zahlen wie `18E0` nicht erforderlich.  
  
 Gleitkommaliterale gehören standardmäßig dem Typ **doppelte**. Mit den Suffixen **f** oder **l** (oder **F** oder **L** – das Suffix ist nicht in der Groß-/Kleinschreibung unterschieden), das Literal kann angegeben werden, als ** "float"** oder `long double`zugeordnet.  
  
 Obwohl `long double` und **doppelte** die gleiche Darstellung haben, sind sie nicht den gleichen Typ. Sie können beispielsweise überladene Funktionen haben:  
  
```  
void func( double );  
```  
  
 und  
  
```  
void func( long double );  
```  
  
## <a name="boolean-literals"></a>Boolesche Literale  
 `true` und `false` sind boolesche Literale.  
  
## <a name="pointer-literal-c11"></a>Zeigerliteral (C++11)  
 C++ stellt die [Nullptr](../cpp/nullptr.md) literal zeigerindikator 0 (null) initialisiert. In übertragbarem Code sollte `nullptr` anstelle von Integraltypnullen oder -makros wie NULL verwendet werden.  
  
## <a name="binary-literals-c14"></a>Binäre Literale (C++14)  
 Ein binäres Literale kann durch die Verwendung des Präfix `0B` oder `0b`, gefolgt durch eine Sequenz von mehreren 1 und 0 angegeben werden.  
  
```  
  
auto x = 0B001101 ; // int  
auto y = 0b000001 ; // int  
```  
  
## <a name="avoid-using-literals-as-magic-constants"></a>Vermeiden der Verwendung von Literalen als „magische Konstanten“  
 Auch wenn Sie Literale direkt in Ausdrücken und Anweisungen verwenden können, ist es nicht immer ein guter Programmierstil:  
  
```  
if (num < 100)  
    return "Success";  
  
```  
  
 Im vorherigen Beispiel empfiehlt sich eher die Verwendung einer benannten Konstante, die eine klare Bedeutung vermittelt, beispielsweise „MAXIMUM_ERROR_THRESHOLD“. Wenn Endbenutzer den Rückgabewert „Success“ anzeigen, empfiehlt sich eher die Verwendung einer benannten Zeichenfolgenkonstante, die an einer einzelnen Position in einer Datei gespeichert werden kann, wo sie in mehrere Sprachen lokalisiert werden kann. Die Verwendung von benannten Konstanten hilft anderen Benutzern und Ihnen, den Zweck des Codes zu verstehen.  
  
## <a name="see-also"></a>Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)   
 [C++-Zeichenfolgenliterale](../cpp/string-and-character-literals-cpp.md)   
 [C++ benutzerdefinierte Literale](../cpp/user-defined-literals-cpp.md)
