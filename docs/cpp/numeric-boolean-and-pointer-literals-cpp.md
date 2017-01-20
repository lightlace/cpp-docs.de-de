---
title: "Numerisch, Boolean und Zeigerliterale (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstanten, Literale"
  - "Literale"
  - "Literale, C++"
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Numerisch, Boolean und Zeigerliterale (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei einem Literal handelt es sich um ein Programmelement, das direkt einen Wert darstellt.  In diesem Artikel werden Literale der Typen Ganzzahl, Gleitkomma, Boolesch und Zeiger erläutert.  Informationen über Zeichenfolgen\- und Zeichenliterale finden Sie unter [Zeichen\- und Zeichenfolgenliterale \(C\+\+\)](../cpp/string-and-character-literals-cpp.md).  Sie können auch Ihre eigenen Literale auf Grundlage dieser Kategorien definieren. Weitere Informationen finden Sie unter [Benutzerdefinierte Literale \(C\+\+\)](../cpp/user-defined-literals-cpp.md)  
  
 .  Sie können Literale in vielen Kontexten verwenden, aber am häufigsten zum Initialisieren von benannten Variablen und zum Weitergeben der Argumente an Funktionen:  
  
```  
const int answer = 42; // integer literal  
double d = sin(108.87);     //floating point literal passed to sin function  
bool b = true;              // boolean literal  
MyClass* mc = nullptr;      // pointer literal  
  
```  
  
 In manchen Fällen ist es wichtig, dem Compiler darüber zu informieren, wie er ein Literal interpretieren soll oder welcher bestimmte Typ ihm erteilt werden soll.  Dies setzen Sie um, indem Sie Prä\- und Suffixe an das Literal anfügen.  Beispielsweise informiert das Präfix „0x“ den Compiler darüber, die darauffolgende Zahl als einen hexadezimalen Wert, beispielsweise „0x35“, zu interpretieren.  Das ULL\-Suffix informiert den Compiler darüber, den Wert als einen `unsigned long long`\-Typ wie in 5894345ULL zu behandeln.  In den folgenden Abschnitten finden Sie die vollständige Liste der Prä\- und Suffixe für jeden Literaltyp.  
  
## Syntax  
  
## Ganzzahlenliteral  
 Ganzzahlenliterale beginnen mit einer Ziffer und weisen weder Bruchteile noch Exponenten auf.  Sie können Integerliterale im Dezimal\-, Oktal\- oder Hexadezimalformat angeben.  Sie können Typen mit oder ohne Vorzeichen und lange oder kurze Typen angeben.  
  
 Wenn weder ein Prä\- noch ein Suffix vorhanden ist, weist der Compiler einen integralen `int`\-Literalwerttyp \(32 Bit\) zu, wenn der Wert passt, ansonsten weist er einen `long long`\-Typ \(64 Bit\) zu.  
  
 Starten Sie zum Angeben eines integralen Dezimalliterals die Spezifikation mit einer Ziffer ungleich 0.  Beispiel:  
  
```  
int i = 157;   // Decimal literal  
int j = 0198;       // Not a decimal number; erroneous octal literal  
int k = 0365;       // Leading zero specifies octal literal, not decimal  
int m = 36'000'000  // digit separators make large values more readable  
int   
```  
  
 Um ein oktales Integralliteral anzugeben, beginnen Sie die Angabe mit 0, gefolgt von einer Ziffernfolge im Bereich von 0 bis 7.  Die Ziffern 8 und 9 sind Fehler, wenn sie ein oktales Literal angeben.  Beispiel:  
  
```  
int i = 0377;   // Octal literal  
int j = 0397;        // Error: 9 is not an octal digit  
```  
  
 Um eine integrale Hexadezimalliterale anzugeben, beginnen Sie die Angabe mit `0x` oder `0X` \(die Groß\-\/Kleinschreibung von "x" ist nicht relevant\), gefolgt von einer Ziffernfolge im Bereich `0` bis `9` und `a` \(oder `A`\) bis `f` \(oder `F`\).  Hexadezimalzahlen `a` \(oder `A`\) bis `f` \(oder `F`\) stellen Werte im Bereich von 10 bis 15 dar.  Beispiel:  
  
```  
int i = 0x3fff;   // Hexadecimal literal  
int j = 0X3FFF;        // Equal to i  
```  
  
 Um einen Typ ohne Vorzeichen anzugeben, verwenden Sie entweder das Suffix **u** oder das Suffix **U**.  Um einen langen Typ anzugeben, verwenden Sie entweder das Suffix **l** oder das Suffix **L**.  Um einen integralen 64\-Bit\-Typ anzugeben, verwenden Sie das Suffix „LL“ oder „ll“.  Das Suffix „i64“ wird weiterhin unterstützt, sollte jedoch vermieden werden, da es für Microsoft spezifisch und nicht übertragbar ist.  Beispiel:  
  
```  
unsigned val_1 = 328u;             // Unsigned value  
long val_2 = 0x7FFFFFL;                 // Long value specified   
                                        //  as hex literal  
unsigned long val_3 = 0776745ul;        // Unsigned long value  
auto val_4 = 108LL;                           // signed long long  
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long   
```  
  
 **Zifferngruppierung**: Zur besseren Lesbarkeit können Sie das einfache Anführungszeichen \(Apostroph\) als Trennzeichen für größere Zahlen verwenden.  Trennzeichen haben keine Auswirkungen auf die Kompilierung.  
  
```  
long long i = 24'847'458'121  
```  
  
## Gleitkommaliterale  
 Gleitkommaliterale geben Werte an, die Nachkommastellen aufweisen müssen.  Diese Werte enthalten Dezimaltrennzeichen \(**.**\) und können Exponenten enthalten.  
  
 Gleitkommaliterale haben eine „Mantisse“, die den Wert der Zahl angibt, einen „Exponenten“, der die Größe der Zahl angibt, und ein optionales Suffix, das den Literaltyp angibt.  Die Mantisse wird wie folgt angegeben: eine Ziffernsequenz, gefolgt von einem Punkt, gefolgt von einer optionalen Ziffernsequenz, die die Nachkommastellen der Zahl darstellen.  Beispiel:  
  
```  
18.46  
38.  
```  
  
 Sofern vorhanden, gibt der Exponent die Größe der Zahl als Zehnerpotenz an \(siehe folgendes Beispiel\):  
  
```  
18.46e0      // 18.46  
18.46e1           // 184.6  
```  
  
 Der Exponent wird wie folgt angegeben: **e** oder **E** \(beide Buchstaben haben dieselbe Bedeutung\), gefolgt von einem optionalen Zeichen \(\+ oder \-\) und einer Ziffernsequenz.  Wenn ein Exponent vorhanden ist, ist das nachfolgende Dezimaltrennzeichen in ganzen Zahlen wie `18E0` nicht erforderlich.  
  
 Gleitkommaliterale gehören standardmäßig dem Typ **double** an.  Bei Verwendung des Suffixes **f** oder **L** \(bzw. **F** oder **L**, beim Suffix wird die Groß\-\/Kleinschreibung nicht beachtet\) kann das Literal als **float** bzw. `long double` angegeben werden.  
  
 Obwohl die Darstellung von `long double` und **double** identisch ist, sind sie nicht derselbe Typ.  Sie können beispielsweise überladene Funktionen haben:  
  
```  
void func( double );  
```  
  
 und  
  
```  
void func( long double );  
```  
  
## Boolesche Literale  
 `true` und `false` sind boolesche Literale.  
  
## Zeigerliteral \(C\+\+11\)  
 In C\+\+ wird das [nullptr](../cpp/nullptr.md)\-Literal zum Angeben eines 0\-initialisierten Zeigers eingeführt.  In übertragbarem Code sollte `nullptr` anstelle von Integraltypnullen oder \-makros wie NULL verwendet werden.  
  
## Binäre Literale \(C\+\+14\)  
 Ein binäres Literale kann durch die Verwendung des Präfix `0B` oder `0b`, gefolgt durch eine Sequenz von mehreren 1 und 0 angegeben werden.  
  
```  
  
auto x = 0B001101 ; // int  
auto y = 0b000001 ; // int  
```  
  
## Vermeiden der Verwendung von Literalen als „magische Konstanten“  
 Auch wenn Sie Literale direkt in Ausdrücken und Anweisungen verwenden können, ist es nicht immer ein guter Programmierstil:  
  
```  
if (num < 100)  
    return "Success";  
  
```  
  
 Im vorherigen Beispiel empfiehlt sich eher die Verwendung einer benannten Konstante, die eine klare Bedeutung vermittelt, beispielsweise „MAXIMUM\_ERROR\_THRESHOLD“.  Wenn Endbenutzer den Rückgabewert „Success“ anzeigen, empfiehlt sich eher die Verwendung einer benannten Zeichenfolgenkonstante, die an einer einzelnen Position in einer Datei gespeichert werden kann, wo sie in mehrere Sprachen lokalisiert werden kann.  Die Verwendung von benannten Konstanten hilft anderen Benutzern und Ihnen, den Zweck des Codes zu verstehen.  
  
## Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)   
 [C\+\+\-Ganzzahlkonstanten](assetId:///1f3b58a4-8346-4533-ba6e-df26d76f8dcf)   
 [C\+\+\-Zeichenliterale](assetId:///a7901c61-524d-47c6-beb6-d9dacc2e72ed)   
 [C\+\+\-Gleitkommakonstanten](assetId:///f6273f24-a876-4484-a7a2-e82275692ad3)   
 [C\+\+\-Zeichenfolgenliterale](../cpp/string-and-character-literals-cpp.md)   
 [Benutzerdefinierte C\+\+\-Literale](../cpp/user-defined-literals-cpp.md)