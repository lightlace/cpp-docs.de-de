---
title: "Zeichenfolgen- und Zeichenliterale (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "R"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Escapesequenzen"
  - "L-Konstante"
  - "Literalzeichenfolgen"
  - "Literalzeichenfolgen, C++"
  - "NULL-Zeichenfolgen"
  - "NULL-Zeichenfolgen, Mit NULL endende Zeichenfolgen"
  - "NULL, Zeichenkonstante"
  - "Zeichenfolgenliterale"
  - "Zeichenfolgenliterale, Syntax"
  - "Zeichenfolgen [C++], Zeichenfolgenliterale"
  - "Breitzeichen, Zeichenfolgen"
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
caps.latest.revision: 36
caps.handback.revision: "34"
ms.author: "mblome"
manager: "ghogen"
---
# Zeichenfolgen- und Zeichenliterale (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ unterstützt verschiedene Zeichenfolgen\- und Zeichentypen und bietet Möglichkeiten Literalwerte dieser einzelnen Typen auszudrücken. In Ihrem Quellcode stellen Sie die Inhalte Ihrer Zeichen\- und Zeichenfolgenliterale mit einem Zeichensatz dar. Universelle Zeichennamen und Escapezeichen ermöglichen es Ihnen, eine beliebige Zeichenfolge darzustellen, indem Sie nur den grundlegenden Quellzeichensatz verwenden. Ein unformatiertes Zeichenfolgenliteral ermöglicht es Ihnen, die Verwendung von Escapezeichen zu vermeiden, und kann verwendet werden, um alle Typen von Zeichenfolgenliteralen auszudrücken. Sie können auch std::string\-Literale erstellen, ohne zusätzliche Erstellungs\- oder Konvertierungsschritte ausführen zu müssen.  
  
```cpp  
#include <string> using namespace std::string_literals; // enables s-suffix for std::string literals int main() { // Character literals auto c0 =   'A'; // char auto c1 = u8'A'; // char auto c2 =  L'A'; // wchar_t auto c3 =  u'A'; // char16_t auto c4 =  U'A'; // char32_t // String literals auto s0 =   "hello"; // const char* auto s1 = u8"hello"; // const char*, encoded as UTF-8 auto s2 =  L"hello"; // const wchar_t* auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16 auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32 // Raw string literals containing unescaped \ and " auto R0 =   R"("Hello \ world")"; // const char* auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8 auto R2 =  LR"("Hello \ world")"; // const wchar_t* auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16 auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32 // Combining string literals with standard s-suffix auto S0 =   "hello"s; // std::string auto S1 = u8"hello"s; // std::string auto S2 =  L"hello"s; // std::wstring auto S3 =  u"hello"s; // std::u16string auto S4 =  U"hello"s; // std::u32string // Combining raw string literals with standard s-suffix auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char* auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8 auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t* auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16 auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32 }  
```  
  
 Ein Zeichenfolgenliteral kann kein Präfix, auch kein `u8`\-, `L`\-, `u`\- und `U`\-Präfix haben, um Codierung für schmale Zeichen \(Einzelbyte oder Multibyte\), UTF\-8, breite Zeichen \(UCS\-2\- oder UTF\-16\), UTF\-16 bzw. UTF\-32 zu kennzeichnen. Ein unformatiertes Zeichenfolgenliteral kann ein `R`\-, `u8R`\-, `LR`, `uR`\- oder `UR`\-Präfix für die jeweils in unformatierter Version vorliegende Entsprechung dieser Codierungen haben.  Um temporäre oder statische std::string\-Werte zu erstellen, können Sie Zeichenfolgenliterale oder unformatierte Zeichenfolgenliterale mit einem `s`\-Suffix verwenden. Weitere Informationen finden Sie im Abschnitt „Zeichenfolgenliterale“ weiter unten. Weitere Informationen zu den grundlegenden Quellzeichensätzen, zu den universellen Zeichennamen sowie dazu, wie Sie Zeichen aus erweiterten Codepages in Ihrem Quellcode verwenden können, finden Sie unter [Zeichensätze](../cpp/character-sets2.md).  
  
## Zeichenliterale  
 Ein *Zeichenfolgenliteral* besteht aus einem konstanten Zeichen. Es wird durch das Zeichen dargestellt, das von einfachen Anführungszeichen eingeschlossen ist. Es gibt vier Arten von Zeichenliteralen:  
  
-   Schmale Zeichenliterale vom Typ `char`, beispielsweise `'a'`  
  
-   Breite Zeichenliterale vom Typ `wchar_t`, beispielsweise `L'a'`  
  
-   Breite Zeichenliterale vom Typ `char16_t`, beispielsweise `u'a'`  
  
-   Breite Zeichenliterale vom Typ `char32_t`, beispielsweise `U'a'`  
  
 Das Zeichen, das für ein Zeichenliteral verwendet wird, kann jedes Zeichen mit Ausnahme der reservierten Zeichen umgekehrter Schrägstrich \('\\'\), einfaches Anführungszeichen \('\) oder Zeilenumbruch sein. Reservierte Zeichen können mit einer Escapesequenz angegeben werden. Zeichen können mit universellen Zeichennamen angegeben werden, solange der Typ groß genug ist, das Zeichen zu enthalten.  
  
###  <a name="bkmk_Escape"></a> Escapesequenzen  
 Es gibt drei Arten von Escapesequenzen: einfache, oktale und hexadezimale. Escapesequenzen können folgendermaßen aussehen:  
  
|Wert|Escapesequenz|Wert|Escapesequenz|  
|----------|-------------------|----------|-------------------|  
|Zeilenumbruch|\\n|Umgekehrter Schrägstrich|\\\\|  
|Horizontaler Tabulator|\\t|Fragezeichen|? oder \\?|  
|Vertikaler Tabulator|\\v|Einfaches Anführungszeichen|\\'|  
|Rückschritt|\\b|Doppeltes Anführungszeichen|\\"|  
|Wagenrücklauf|\\r|das Nullzeichen|\\0|  
|Seitenvorschub|\\f|Oktal|\\ooo|  
|Warnung \(Glocke\)|\\a|Hexadezimal|\\xhhh|  
  
 Der folgende Code zeigt einige Beispiele für Escapezeichen mit schmalen Zeichenfolgenliteralen. Die gleiche Syntax ist gültig für die anderen Zeichefolgenliteraltypen.  
  
```cpp  
#include <iostream> using namespace std; int main() { char newline = '\n'; char tab = '\t'; char backspace = '\b'; char backslash = '\\'; char nullChar = '\0'; cout << "Newline character: " << newline << "ending" << endl; // Newline character: //  ending cout << "Tab character: " << tab << "ending" << endl; // Tab character : ending cout << "Backspace character: " << backspace << "ending" << endl; // Backspace character : ending cout << "Backslash character: " << backslash << "ending" << endl; // Backslash character : \ending cout << "Null character: " << nullChar << "ending" << endl; //Null character:  ending }  
```  
  
 **Microsoft\-spezifisch**  
  
 Um einen Wert aus einem Zeichenliteral ohne Präfix zu erstellen, konvertiert der Compiler das Zeichen oder die Zeichenfolge zwischen einfachen Anführungszeichen in 8\-Bit\-Werte in einer 32\-Bit\-Ganzzahl. Mehrere Zeichen im Literal belegen entsprechende Bytes nach Bedarf vom höherwertigen zum niederwertigen Byte. Um einen `char`\-Wert zu erstellen, nimmt der Compiler das niederwertige Byte. Um einen `wchar_t`\- oder einen  `char16_t`\-Wert zu erstellen, nimmt der Compiler das niederwertige Wort. Der Compiler warnt, dass das Ergebnis abgeschnitten wird, wenn irgendwelche Bits über dem zugewiesenen Byte oder Word Bits festgelegt sind.  
  
```cpp  
char c0    = 'abcd';    // C4305, C4309, truncates to 'd' wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'  
```  
  
 Eine oktale Escapesequenz ist ein umgekehrter Schrägstrich gefolgt von einer Sequenz von bis 3 Oktalziffern. Eine oktale Escapesequenz, die scheinbar mehr als drei Ziffern enthält, wird als eine 3\-ziffrige oktale Sequenz gefolgt von den weiteren Ziffern als Zeichen behandelt. Dies kann zu überraschenden Ergebnissen führen. Zum Beispiel:  
  
```cpp  
char c1 = '\100';   // '@' char c2 = '\1000';  // C4305, C4309, truncates to '0'   
```  
  
 Eine Escapesequenzen, die scheinbar nicht oktale Zeichen enthält, wird als eine oktale Sequenz bis zu dem letzten oktalen Zeichen gefolgt von den verbleibenden Zeichen ausgewertet. Zum Beispiel:  
  
```cpp  
char c3 = '\009';   // '9' char c4 = '\089';   // C4305, C4309, truncates to '9' char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'  
```  
  
 Eine hexadezimale Escapesequenz ist ein umgekehrter Schrägstrich, gefolgt von dem Zeichen `x`, gefolgt von einer Sequenz von hexadezimalen Zeichen. Eine Escapesequenz, die keine Hexadezimalziffern enthält, verursacht den Compilerfehler C2153 "Hexadezimale Literale müssen mindestens eine hexadezimale Ziffer enthalten". Führende Nullen werden ignoriert. Eine Escapesequenz, die anscheinend hexadezimale und nicht hexadezimale Zeichen beinhaltet, wird als eine hexadezimale Escapesequenz bis zum letzten hexadezimalen Zeichen gefolgt von den nicht hexadezimalen Zeichen ausgewertet.   In einem Schmalzeichenliteral ohne Präfix oder mit dem Präfix u8 ist 0xFF der höchste Hexadezimalwert. In einem Breitzeichenliteral mit dem Präfix L oder u ist 0xFFFF der höchste Hexadezimalwert. In einem Breitzeichenliteral mit dem Präfix U ist 0xFFFFFFFF der höchste Hexadezimalwert.  
  
```cpp  
char c6 = '\x0050'; // 'P' char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'  
```  
  
 Enthält ein Breitzeichenliteral mit dem Präfix `L` mehr als ein Zeichen, wird der Wert des ersten Zeichens übernommen. Nachfolgende Zeichen werden, anders als beim Verhalten des entsprechenden Schmalzeichenliterals ohne Präfix, ignoriert.  
  
```cpp  
wchar_t w1 = L'\100';   // L'@' wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored wchar_t w6 = L'\x0050'; // L'P' wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored  
```  
  
 **Ende Microsoft\-spezifisch**  
  
 Der umgekehrte Schrägstrich \(\\\) ist ein Zeilenfortsetzungszeichen, wenn er am Ende einer Zeile platziert wird. Wenn ein umgekehrter Schrägstrich als Zeichenliteral angezeigt werden soll, müssen Sie zwei umgekehrte Schrägstriche in einer Zeile \(`\\`\) eingeben. Weitere Informationen zum Zeilenfortsetzungszeichen finden Sie unter [Phasen der Übersetzung](../preprocessor/phases-of-translation.md).  
  
###  <a name="bkmk_UCN"></a> Universelle Zeichennamen  
 In Zeichenliteralen und systemeigenen \(nicht unformatierten\) Zeichenfolgenliteralen kann jedes Zeichen durch einen universellen Zeichennamen dargestellt werden.  Ein universeller Zeichennamen wird wie folgt gebildet: durch das Präfix \\U, auf das ein achtstelliger Unicode\-Codepunkt folgt, oder durch das Präfix \\u, auf das ein vierstellige Unicode\-Codepunkt folgt. Alle acht bzw. vier Ziffern müssen vorhanden sein, damit sich ein wohlgeformter universeller Zeichenname ergibt.  
  
```cpp  
char u1 = 'A';          // 'A' char u2 = '\101';       // octal, 'A' char u3 = '\x41';       // hexadecimal, 'A' char u4 = '\u0041';     // \u UCN 'A' char u5 = '\U00000041'; // \U UCN 'A'  
```  
  
 **Ersatzzeichenpaare**  
  
 Mit universellen Zeichennamen können keine Werte codiert werden, die sich im Ersatzcodepunktbereich D800 DFFF befinden. Für Unicode\-Ersatzzeichenpaare geben Sie den universellen Zeichennamen an, indem Sie `\UNNNNNNNN` verwenden, wobei NNNNNNNN ein achtstellige Codepunkt für das Zeichen ist. Der Compiler generiert ggf. ein Ersatzzeichenpaar.  
  
 In C\+\+03 kann in der Sprache nur eine Teilmenge der Zeichen durch deren universelle Zeichennamen dargestellt werden und sind einige universelle Zeichennamen zulässig, die tatsächlich keine gültigen Unicode\-Zeichen darstellen. Dieses Problem wurde in Standard C \+\+ 11 behoben. In C\+\+11 können sowohl für Zeichen\- und Zeichenfolgenliterale als auch für Bezeichner universelle Zeichennamen verwendet werden.  Weitere Informationen zu universellen Zeichennamen finden Sie unter [Zeichensätze](../cpp/character-sets2.md). Weitere Informationen zu Unicode finden Sie unter [Unicode](http://msdn.microsoft.com/library/dd374081\(v=vs.85\).aspx). Weitere Informationen zu Ersatzzeichenpaaren finden Sie im Artikel über [Ersatzzeichenpaare und zusätzliche Zeichen](http://msdn.microsoft.com/library/dd374069\(v=vs.85\).aspx).  
  
## Zeichenfolgenliterale  
 Ein Zeichenfolgenliteral stellt eine Folge von Zeichen dar, die zusammen eine auf NULL endende Zeichenfolge bilden. Die Zeichen müssen zwischen doppelten Anführungszeichen eingeschlossen werden. Es gibt die folgenden Arten von Zeichenfolgenliteralen:  
  
### Schmale Zeichenfolgenliterale  
 Ein Schmalzeichenfolgenliteral ist ein präfixloses, durch doppelte Anführungszeichen getrenntes, nullterminiertes Array des Typs `const` `char`\[`n`\], wobei n die Länge des Arrays in Bytes ist. Ein Schmalzeichenfolgenliteral kann jedes Grafikzeichen außer einem doppelten Anführungszeichen \(`"`\), umgekehrten Schrägstrichen \(`\`\) oder Zeilenumbruchzeichen enthalten. Ein Schmalzeichenfolgenliteral kann auch die oben aufgelisteten Escapesequenzen sowie universelle Zeichennamen enthalten, die in ein Byte passen.  
  
```cpp  
const char *narrow = "abcd"; // represents the string: yes\no const char *escaped = "yes\\no";  
```  
  
 **UTF\-8 codierte Zeichenfolgen**  
  
 Eine UTF\-8 codierte Zeichenfolge ist ein mit dem Präfix u8 versehenes, durch doppelte Anführungszeichen getrenntes, nullterminiertes Array des Typs `const``char`\[`n`\], wobei n die Länge des codierten Arrays in Bytes ist. Ein mit dem Präfix u8 versehenes Zeichenfolgenliteral kann jedes Grafikzeichen außer einem doppelten Anführungszeichen \(`"`\), umgekehrten Schrägstrichen \(`\`\) oder Zeilenumbruchzeichen enthalten. Ein mit dem Präfix u8 versehenes Zeichenfolgenliteral kann auch die Escapesequenzen, die oben aufgelistet sind, sowie jeden universellen Zeichennamen enthalten.  
  
```cpp  
const char* str1 = u8"Hello World"; const char* str2 = u8"\U0001F607 is O:-)";  
```  
  
### Breite Zeichenfolgenliterale  
 Ein breites Zeichenfolgenliteral ist ein mit Null endendes Array einer Konstanten, `wchar_t` dem '`L`' vorangestellt ist und das jedes Schriftzeichen außer das doppelte Anführungszeichen \("\), den umgekehrten Schrägstrich \(\\\) oder die Zeilenendemarke enthält. Ein Breitzeichenfolgenliteral kann die Escapesequenzen, die oben aufgelistet sind, sowie jeden universellen Zeichennamen enthalten.  
  
```cpp  
const wchar_t* wide = L"zyxw"; const wchar_t* newline = L"hello\ngoodbye";  
```  
  
 **char16\_t und char32\_t \(C \+\+ 11\)**  
  
 C \+\+ 11 stellt die portablen `char16_t` \(16\-Bit\-Unicode\) und `char32_t` \(32\-Bit\-Unicode\)\-Zeichentypen vor:  
  
```cpp  
auto s3 = u"hello"; // const char16_t* auto s4 = U"hello"; // const char32_t*  
```  
  
### Unformatierte Zeichenfolgenliterale \(C\+\+11\)  
 Ein unformatiertes Zeichenfolgenliteral ist ein auf NULL endendes Array eines jeden Zeichentyps, das jedes Schriftzeichen, einschließlich des doppelten Anführungszeichens \("\), des umgekehrten Schrägstrichs \(\\\) oder des Zeilenumbruchzeichens enthält. Unformatierte Zeichenfolgenliterale werden häufig in regulären Ausdrücken, die Zeichenklassen verwenden, und in HTML\-Zeichenfolgen und XML\-Zeichenfolgen verwendet. Beispiele finden Sie im folgenden Artikel: [Bjarne Stroustrups FAQ zu C\+\+11](http://go.microsoft.com/fwlink/?LinkId=401172).  
  
```cpp  
// represents the string: An unescaped \ character const char* raw_narrow = R"(An unescaped \ character)"; const wchar_t* raw_wide = LR"(An unescaped \ character)"; const char*       raw_utf8  = u8R"(An unescaped \ character)"; const char16_t* raw_utf16 = uR"(An unescaped \ character)"; const char32_t* raw_utf32 = UR"(An unescaped \ character)";  
```  
  
 Ein Trennzeichen ist eine benutzerdefinierte Sequenz von bis zu 16 Zeichen, die der öffnenden Klammer eines unformatierten Zeichenfolgenliterals unmittelbar vorangestellt wird und dessen schließender Klammer unmittelbar folgt.  Beispielsweise ist in `R"abc(Hello"\()abc"` die Zeichenfolge `abc` die Trennzeichensequenz und `Hello"\(` der Zeichenfolgeninhalt. Sie können ein Trennzeichen verwenden, um unformatierte Zeichenfolgen eindeutig zu machen, die doppelte Anführungszeichen und Klammern enthalten. Dies löst einen Compilerfehler aus:  
  
```cpp  
// meant to represent the string: )” const char* bad_parens = R"()")";  // error C2059  
```  
  
 Durch ein Trennzeichen wird er jedoch behoben:  
  
```cpp  
const char* good_parens = R"xyz()")xyz";  
```  
  
 Sie können ein unformatiertes Zeichenfolgenliteral konstruieren, in dessen Quelle ein Zeilenumbruch \(nicht das Escapezeichen\) enthalten ist:  
  
```cpp  
// represents the string: hello //goodbye const wchar_t* newline = LR"(hello goodbye)";  
```  
  
### std:: Zeichenfolgenliterale \(C\+\+14\)  
 Std:: Zeichenfolgenliterale sind Implementierungen der Standardbibliothek benutzerdefinierter Literale \(siehe unten\), die als "xyx"s dargestellt werden \(mit einem `s` Suffix\). Diese Art von Zeichenfolgenliteral erzeugt ein temporäres Objekt des Typs std::string, std:: wstring, std::u32string oder std::u16string je nach Präfix, das angegeben wird. Wenn kein Präfix, wie oben, verwendet wird, wird ein std::string erstellt. L "xyz"s erzeugt einen std:: wstring. u "xyz"s erzeugt einen [std::u16string](../Topic/u16string.md) und U“xyz"s erzeugt einen [std::u32string](../Topic/u32string.md).  
  
```cpp  
//#include <string> //using namespace std::string_literals; string str{ "hello"s }; string str2{ u8"Hello World" }; wstring str3{ L"hello"s }; u16string str4{ u"hello"s }; u32string str5{ U"hello"s };  
```  
  
 Das S\-Suffix kann auch auf unformatierten Zeichenfolgenliteralen verwendet werden:  
  
```cpp  
u32string str6{ UR"(She said "hello.")"s };  
```  
  
 std::string\-Literale werden in dem Namespace `std::literals::string_literals` in der Headerdatei \< Zeichenfolge \> definiert. Da `std::literals::string_literals` und `std::literals` beide als [inlinenamespaces](../cpp/namespaces-cpp.md) deklariert werden, wird `std::literals::string_literals` automatisch so behandelt, als ob sie direkt zum Namespace `std` gehören.  
  
### Größe von Zeichenfolgenliteralen  
 Für ANSI char\*\-Zeichenfolgen und andere Einzelbyte\-Codierungen \(nicht UTF\-8\) ist die Größe \(in Byte\) eines Zeichenfolgenliterals gleich der Anzahl der Zeichen plus 1 für das abschließende Nullzeichen. Für alle anderen Zeichenfolgentypen ist die Größe nicht streng mit der Anzahl der Zeichen verknüpft. UTF\-8 verwendet bis zu vier char\-Elemente zum Codieren von einigen *Codeeinheiten* und char16\_t oder wchar\_t, codiert als UTF\-16, kann zwei Elemente \(für insgesamt vier Bytes\) verwenden, um eine einzelne *Codeeinheit* zu codieren.   In diesem Beispiel wird die Größe eines Breitzeichenfolgenliterals in Bytes gezeigt:  
  
```cpp  
const wchar_t* str = L"Hello!"; const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);  
```  
  
 Beachten Sie, dass `strlen()` und `wcslen()` nicht die Größe des abschließenden Null\-Zeichens enthalten, dessen Größe gleich der Elementgröße vom Zeichenfolgentyp ist: ein Byte für eine Zeichenfolge char\*, zwei Bytes für wchar\_t\* oder char16\_t\* Zeichenfolgen und vier Bytes auf char32\_t\* Zeichenfolgen.  
  
 Die maximale Länge eines Zeichenfolgenliterals beträgt 65535 Bytes. Diese Begrenzung gilt sowohl für schmale Zeichenfolgenliterale als auch für breite Zeichenfolgenliterale.  
  
### Ändern von Zeichenfolgenliteralen  
 Da Zeichenfolgenliterale \(mit Ausnahme von std::string\-Literale\) Konstanten sind, wird bei dem Versuch, sie zu ändern \(beispielsweise str \[2\] \= 'A'\) ein Compilerfehler ausgelöst.  
  
 **Microsoft\-spezifisch**  
  
 In Visual C\+\+ können Sie ein Zeichenfolgenliteral verwenden, um einen Zeiger auf ein nicht konstantes `char` oder `wchar_t` zu initialisieren. Dies ist in C99\-Code zulässig, in C\+\+98 jedoch veraltet und wurde in C\+\+11 entfernt. Ein Versuch, die Zeichenfolge zu ändern, verursacht eine Zugriffsverletzung, wie in diesem Beispiel:  
  
```cpp  
wchar_t* str = L"hello"; str[2] = L'a'; // run-time error: access violation  
```  
  
 Sie können den Compiler anweisen, einen Fehler auszugeben, wenn ein Zeichenfolgenliteral in einen non\_const\-Zeichenzeiger konvertiert wird, wenn Sie die Compileroption [\/Zc:strictStrings \(Zeichenfolgenliteral\-Typkonvertierung deaktivieren\)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) festlegen. Dies empfiehlt sich für mit den Standards kompatiblen portablen Code. Es ist außerdem empfehlenswert, Zeiger, die mithilfe von Zeichenfolgenliteralen initialisiert werden, mit dem `auto`\-Schlüsselwort zu deklarieren, da es in den richtigen \(const\) Typ auflöst. In diesem Codebeispiel wird ein Versuch abgefangen, zur Kompilierungszeit in ein Zeichenfolgenliteral zu schreiben:  
  
```cpp  
auto str = L"hello"; str[2] = L'a'; // C3892: you cannot assign to a variable that is const.  
```  
  
 In einigen Fällen können identische Zeichenfolgenliterale "zusammengelegt" werden, um Speicherplatz in der ausführbaren Datei zu sparen. Im Zeichenfolgenliteral\-Pooling bewirkt der Compiler, dass alle Verweise auf ein bestimmtes Zeichenfolgenliteral auf die gleiche Position im Arbeitsspeicher zeigen, anstatt dass alle Verweise auf eine separate Instanz des Zeichenfolgenliterals zeigen. Verwenden Sie die [\/GF](../build/reference/gf-eliminate-duplicate-strings.md)\-Compileroption, um Stringpooling zu aktivieren.  
  
 **Ende Microsoft\-spezifisch**  
  
### Verketten von benachbarten Zeichenfolgenliteralen  
 Benachbarte breite oder schmale Zeichenfolgenliterale werden verkettet. Diese Deklaration ist:  
  
```cpp  
char str[] = "12" "34";  
```  
  
 mit dieser Deklaration identisch:  
  
```cpp  
char atr[] = "1234";  
```  
  
 und mit dieser Deklaration identisch:  
  
```cpp  
char atr[] =  "12\ 34";  
```  
  
 Durch die Verwendung eingebetteter hexadezimaler Escapesequenzen für die Angabe von Zeichenfolgenliterale können unerwartete Ergebnisse verursacht werden. Im folgenden Beispiel soll ein Zeichenfolgenliteral erstellt werden, das ASCII 5\-Zeichen enthält, gefolgt von den Zeichen f, i, v und e:  
  
```cpp  
"\x05five"  
```  
  
 Das eigentliche Ergebnis ist ein hexadezimales 5F, also der ASCII\-Code für einen Unterstrich, gefolgt von den Zeichen i, v und e. Um das richtige Ergebnis zu erhalten, können Sie eines der folgenden Elemente verwenden:  
  
```cpp  
"\005five"     // Use octal literal. "\x05" "five"  // Use string splicing.  
```  
  
 std::string\-Literale können mit dem \+\-Operator, der für die definierten [Basic\_string](../standard-library/basic-string-class.md) Typen definiert ist, verkettet werden, da sie std::String\-Datentypen sind. Sie können auch auf die gleiche Weise wie benachbarte Zeichenfolgenliterale verkettet werden. In beiden Fällen müssen die Zeichenfolgencodierung und das Suffix übereinstimmen:  
  
```cpp  
auto x1 = "hello" " " " world"; // OK auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes  
```  
  
### Zeichenfolgenliterale mit universellen Zeichennamen  
 In systemeigenen \(nicht unformatierten\) Zeichenfolgenliteralen können universelle Zeichennamen verwendet werden, um jedes beliebige Zeichen darzustellen, solange der jeweilige universelle Zeichenname als ein oder mehrere Zeichen im string\-Datentyp codiert werden kann.  Beispielsweise kann ein universeller Zeichenname, der ein erweitertes Zeichen darstellt, nicht in einer schmalen Zeichenfolge über die ANSI\-Codepage codiert werden, er kann aber in schmalen Zeichenfolgen in einigen Multibyte\-Codepages oder in UTF\-8\-Zeichenfolgen oder in einer breiten Zeichenfolge codiert werden. In C\+\+11 ist die Unicode\-Unterstützung durch die Zeichenfolgentypen char16\_t\* und char32\_t\* erweitert:  
  
```cpp  
// ASCII smiling face const char*     s1 = ":-)"; // UTF-16 (on Windows) encoded WINKING FACE (U+1F609) const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)"; // UTF-8  encoded SMILING FACE WITH HALO (U+1F607) const char*     s3 = u8"😇 = \U0001F607 is O:-)"; // UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603) const char16_t* s4 = u"😃 = \U0001F603 is :-D"; // UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E) const char32_t* s5 = U"😎 = \U0001F60E is B-)";  
```  
  
## Siehe auch  
 [Zeichensätze](../cpp/character-sets2.md)   
 [Numerisch, Boolean und Zeigerliterale](../cpp/numeric-boolean-and-pointer-literals-cpp.md)   
 [Benutzerdefinierte Literale](../cpp/user-defined-literals-cpp.md)