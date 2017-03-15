---
title: "#define-Direktive (C/C++)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#define-Direktive"
  - "#define-Direktive, Syntax"
  - "define-Direktive (#define)"
  - "define-Direktive (#define), Syntax"
  - "Präprozessor, Direktiven"
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# #define-Direktive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit `#define` wird ein *Makro* erstellt, das die Zuordnung eines Bezeichners oder eines parametrisierten Bezeichners zu einer Tokenzeichenkette darstellt.  Nachdem das Makro definiert wurde, kann der Compiler die Tokenzeichenkette für jedes Vorkommen des Bezeichners in der Quelldatei ersetzen.  
  
## Syntax  
 `#define` *identifier* *token\-string*opt  
  
 `#define` *identifier*`(` *identifier*opt`,` *...* `,` *identifier*opt `)` *token\-string*opt  
  
## Hinweise  
 Die `#define`\-Direktive weist den Compiler an, die *token\-string* für jedes Vorkommen von *identifier* in der Quelldatei zu ersetzen.  Der *identifier* wird nur ersetzt, wenn er ein Token bildet.  Der *identifier* wird also nicht ersetzt, wenn er in einem Kommentar, in einer Zeichenfolge oder als Teil eines längeren Bezeichners erscheint.  Weitere Informationen finden Sie unter [C\+\+\-Tokens](../cpp/tokens-cpp.md).  
  
 Das *token\-string*\-Argument besteht aus einer Reihe von Token, z. B. Schlüsselwörter, Konstanten oder vollständigen Anweisungen.  *token\-string* und *identifier* müssen durch mindestens ein Leerzeichen voneinander getrennt werden.  Diese Leerstelle und alle weiteren Leerstellen nach dem letzten Token des Texts werden nicht als Teil des ersetzten Texts betrachtet.  
  
 Durch `#define` ohne *token\-string* werden die Vorkommen von *identifier* aus der Quelldatei entfernt.  Der *identifier* bleibt definiert und kann mithilfe der Direktiven `#if defined` und `#ifdef` überprüft werden.  
  
 Durch das zweite Syntaxformat wird ein funktionsähnliches Makro mit Parametern definiert.  Dieses Formular akzeptiert eine optionale Liste von Parametern, die in Klammern angegeben sein müssen.  Nachdem das Makro definiert wurde, werden nachfolgende Vorkommen von *identifier*\( *identifier*opt, ..., *identifier*opt \) mit einer Version des *token\-string*\-Arguments ersetzt, das die tatsächlichen Argumente enthält, die durch formale Parameter ersetzt werden.  
  
 Formale Parameternamen werden in *token\-string* angezeigt, um die Speicherorte zu markieren, an denen tatsächliche Werte ersetzt werden.  Jeder Parametername kann mehrmals in *token\-string* angezeigt werden, und die Namen können in beliebiger Reihenfolge angegeben werden.  Die Anzahl von Argumenten im Aufruf muss mit der Anzahl von Parametern in der Makrodefinition übereinstimmen.  Mit der großzügigen Verwendung von Klammern wird sichergestellt, dass komplexe tatsächliche Argumente richtig interpretiert werden.  
  
 Die formalen Parameter in der Liste werden durch Kommas getrennt.  Jeder Name in der Liste muss eindeutig sein und die Liste muss in Klammern eingeschlossen werden.  *identifier* und die öffnende Klammer können nicht durch Leerzeichen getrennt werden.  Verwenden Sie für lange Direktive in mehreren Quellzeilen die Zeilenverkettung, d. h. setzen Sie einen umgekehrten Schrägstrich \(`\`\) direkt vor dem Zeilenumbruchzeichen.  Der Gültigkeitsbereich eines formalen Parameternamens wird um die neue Zeile erweitert, die mit *token\-string* endet.  
  
 Wenn ein Makro im zweiten Syntaxformat definiert wurde, geben nachfolgende Textinstanzen, auf die eine Argumentliste folgt, einen Makro\-Aufruf an.  Die tatsächlichen Argumente, die auf eine Instanz von *identifier* in der Quelldatei folgen, stimmen mit den entsprechenden formalen Parametern in der Makrodefinition überein.  Jeder formale Parameter in *token\-string*, dem nicht ein Zeichenfolgenoperator \(`#`\), Zeichenoperator \(`#@`\) oder Operator zum Einfügen eines Tokens \(`##`\) vorangestellt ist bzw. auf den kein `##`\-Operator folgt, wird durch das entsprechende tatsächliche Argument ersetzt.  Alle Makros im tatsächlichen Argument werden erweitert, bevor die Direktive den formalen Parameter ersetzt. \(Die Operatoren werden unter [Präprozessor\-Operatoren](../preprocessor/preprocessor-operators.md) beschrieben\).  
  
 Die folgenden Beispiele von Makros mit Argumenten veranschaulichen das zweite Format der `#define`\-Syntax:  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 Argumente mit Nebeneffekten können dazu führen, dass Makros unerwartete Ergebnisse erzeugen.  Ein angegebener formaler Parameter wird möglicherweise mehrmals in *token\-string* angezeigt.  Wenn der formale Parameter durch einen Ausdruck mit Nebeneffekten ersetzt wird, dann wird der Ausdruck samt seinen Nebeneffekten evtl. mehrmals ausgewertet. \(Weitere Informationen bieten die Beispiele unter [Operator zum Einfügen eines Tokens \(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)\).  
  
 Die `#undef`\-Direktive führt dazu, dass die Präprozessordefinition eines Bezeichners übergangen wird.  Weitere Informationen finden Sie unter [Die \#undef\-Direktive](../preprocessor/hash-undef-directive-c-cpp.md).  
  
 Wenn der Name des definierten Makros in *token\-string* auftritt \(auch als Ergebnis einer anderen Makroerweiterung\), wird er nicht erweitert.  
  
 Ein zweites `#define` für ein Makro mit demselben Namen generiert eine Warnung, es sei denn, die zweite Tokensequenz ist identisch mit der ersten.  
  
 **Microsoft\-spezifisch**  
  
 Mit Microsoft C\/C\+\+ können Sie ein Makro neu definieren, wenn die neue Definition mit der ursprünglichen Definition syntaktisch identisch ist.  Das bedeutet, dass die beiden Definitionen über unterschiedliche Parameternamen verfügen können.  Dieses Verhalten unterscheidet sich von [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C, wo die beiden Definitionen lexikalisch gleich sind.  
  
 Beispielsweise sind die folgenden beiden Makros identisch, abgesehen von den Parameternamen.  [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C lässt keine solche Neudefinition zu, bei Microsoft C\/C\+\+ hingegen wird ohne Fehler kompiliert.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 Andererseits sind die folgenden beiden Makros nicht identisch und generieren in Microsoft C\/C\+\+ eine Warnung.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **END Microsoft\-spezifisch**  
  
 In diesem Beispiel wird die `#define`\-Direktive veranschaulicht:  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 Die erste Anweisung definiert den Bezeichner `WIDTH` als die ganzzahlige Konstante 80 und definiert `LENGTH` hinsichtlich `WIDTH` und der ganzzahligen Konstante 10.  Jedes Vorkommen von `LENGTH` wird ersetzt durch \(`WIDTH + 10`\).  Im Gegenzug wird jedes Vorkommen von `WIDTH + 10` durch den Ausdruck \(`80 + 10`\) ersetzt.  Die Klammern um `WIDTH + 10` sind wichtig, da sie die Interpretation in Anweisungen steuern, z. B.:  
  
```  
var = LENGTH * 20;  
```  
  
 Nach der Vorverarbeitungsphase wird die Anweisung:  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 zu 1800 ausgewertet.  Ohne Klammern wird das Ergebnis:  
  
```  
var = 80 + 10 * 20;  
```  
  
 zu 280 ausgewertet.  
  
 **Microsoft\-spezifisch**  
  
 Das Definieren von Makros und Konstanten mit der Compileroption [\/D](../build/reference/d-preprocessor-definitions.md) hat denselben Effekt wie die Verwendung einer `#define`\-Präprozessdirektive am Anfang der Datei.  Maximal 30 Makros können mit der \/D\-Option definiert werden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)