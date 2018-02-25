---
title: '##define-Direktive (C/C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#define'
dev_langs:
- C++
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d06a24d969f0ae7545f1b9ec0401e098a2bcf54
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="define-directive-cc"></a>#define-Anweisung (C/C++)
Die `#define` erstellt eine *Makro*, dies ist die Zuordnung eines Bezeichners oder parametrisierten Bezeichners zu einer tokenzeichenkette darstellt. Nachdem das Makro definiert wurde, kann der Compiler die Tokenzeichenkette für jedes Vorkommen des Bezeichners in der Quelldatei ersetzen.  
  
## <a name="syntax"></a>Syntax  
 `#define` *Bezeichner* *-Token-String*abonnieren  
  
 `#define` *Bezeichner* `(` *Bezeichner*opt`,`*...*  `,` *Bezeichner*opt`)`*-Token-String*abonnieren  
  
## <a name="remarks"></a>Hinweise  
 Die `#define` Richtlinie weist den Compiler zu ersetzen, *-Token-String* für jedes Auftreten der *Bezeichner* in der Quelldatei. Die *Bezeichner* wird ersetzt, nur, wenn sie ein Token bildet. D. h. *Bezeichner* wird nicht ersetzt werden, wenn er in einem Kommentar, der in einer Zeichenfolge oder als Teil eines längeren Bezeichners angezeigt wird. Weitere Informationen finden Sie unter [Token](../cpp/tokens-cpp.md).  
  
 Die *-Token-String* Argument besteht aus einer Reihe von Token, z. B. Schlüsselwörter, Konstanten oder vollständige-Anweisungen. Müssen mindestens ein Leerzeichen trennen *-Token-String* aus *Bezeichner*. Diese Leerstelle und alle weiteren Leerstellen nach dem letzten Token des Texts werden nicht als Teil des ersetzten Texts betrachtet.  
  
 Ein `#define` ohne eine *-Token-String* entfernt Vorkommen der *Bezeichner* aus der Quelldatei. Die *Bezeichner* bleibt definiert und getestet werden kann, mithilfe der `#if defined` und `#ifdef` Direktiven.  
  
 Durch das zweite Syntaxformat wird ein funktionsähnliches Makro mit Parametern definiert. Dieses Formular akzeptiert eine optionale Liste von Parametern, die in Klammern angegeben sein müssen. Nachdem das Makro definiert, die jeder nachfolgende Vorkommen ist *Bezeichner*( *Bezeichner*opt,..., *Bezeichner*opt) wird mit einer Version von ersetzt die  *Token-String* Arguments mit tatsächlichen Argumenten für die formalen Parameter ersetzt.  
  
 Formale Parameternamen angezeigt werden, *-Token-String* , markieren Sie die Speicherorte, in denen tatsächliche Werte ersetzt werden. Jeder Parametername kann mehrmals *-Token-String*, und die Namen können in beliebiger Reihenfolge angezeigt werden. Die Anzahl von Argumenten im Aufruf muss mit der Anzahl von Parametern in der Makrodefinition übereinstimmen. Mit der großzügigen Verwendung von Klammern wird sichergestellt, dass komplexe tatsächliche Argumente richtig interpretiert werden.  
  
 Die formalen Parameter in der Liste werden durch Kommas getrennt. Jeder Name in der Liste muss eindeutig sein und die Liste muss in Klammern eingeschlossen werden. Keine Leerzeichen trennen können *Bezeichner* und die öffnende Klammer. Verwenden der Verkettung Zeile – platzieren Sie einen umgekehrten Schrägstrich (`\`) unmittelbar vor dem Zeilenumbruchzeichen – für lange Anweisungen in mehreren Quellzeilen. Erstreckt sich der Gültigkeitsbereich des Namens eines formaler Parameter in die neue Zeile, die beendet *-Token-String*.  
  
 Wenn ein Makro im zweiten Syntaxformat definiert wurde, geben nachfolgende Textinstanzen, auf die eine Argumentliste folgt, einen Makro-Aufruf an. Die tatsächlichen Argumente, die eine Instanz von folgt *Bezeichner* in der Quelldatei mit der entsprechenden formalen Parameter in der Makrodefinition verglichen werden. Jede formaler Parameter in *-Token-String* , keine Zeichenfolgenoperators vorangestellt (`#`), zeichenoperatoren (`#@`), oder Einfügen eines Tokens (`##`)-Operator, oder nicht gefolgt von einer `##` Operator ist durch das entsprechende tatsächliche Argument ersetzt. Alle Makros im tatsächlichen Argument werden erweitert, bevor die Anweisung den formalen Parameter ersetzt. (Die Operatoren werden in beschrieben [Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md).)  
  
 Die folgenden Beispiele von Makros mit Argumenten veranschaulichen das zweite Format der `#define`-Syntax:  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 Argumente mit Nebeneffekten können dazu führen, dass Makros unerwartete Ergebnisse erzeugen. Ein bestimmten formaler Parameter erscheinen auf den mehr als einmal in *-Token-String*. Wenn der formale Parameter durch einen Ausdruck mit Nebeneffekten ersetzt wird, dann wird der Ausdruck samt seinen Nebeneffekten evtl. mehrmals ausgewertet. (Siehe Beispiele unter [Tokeneinfügenden Operator (##)](../preprocessor/token-pasting-operator-hash-hash.md).)  
  
 Die `#undef`-Direktive führt dazu, dass die Präprozessordefinition eines Bezeichners übergangen wird. Finden Sie unter [#undef-Direktive](../preprocessor/hash-undef-directive-c-cpp.md) für Weitere Informationen.  
  
 Im Falle der Name des Makros definierende *-Token-String* (auch als Ergebnis einer anderen makroerweiterung), wird er nicht erweitert.  
  
 Ein zweites `#define` für ein Makro mit demselben Namen generiert eine Warnung, es sei denn, die zweite Tokensequenz ist identisch mit der ersten.  
  
 **Microsoft-spezifisch**  
  
 Mit Microsoft C/C++ können Sie ein Makro neu definieren, wenn die neue Definition mit der ursprünglichen Definition syntaktisch identisch ist. Das bedeutet, dass die beiden Definitionen über unterschiedliche Parameternamen verfügen können. Dieses Verhalten unterscheidet sich von [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C, wo die beiden Definitionen lexikalisch gleich sind.  
  
 Beispielsweise sind die folgenden beiden Makros identisch, abgesehen von den Parameternamen. [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C lässt keine solche Neudefinition, aber Microsoft C/C++-wird ohne Fehler kompiliert.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 Andererseits sind die folgenden beiden Makros nicht identisch und generieren in Microsoft C/C++ eine Warnung.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **Ende Microsoft-spezifisch**  
  
 In diesem Beispiel wird die `#define`-Direktive veranschaulicht:  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 Die erste Anweisung definiert den Bezeichner `WIDTH` als die ganzzahlige Konstante 80 und definiert `LENGTH` hinsichtlich `WIDTH` und der ganzzahligen Konstante 10. Jedes Vorkommen von `LENGTH` wird ersetzt durch (`WIDTH + 10`). Im Gegenzug wird jedes Vorkommen von `WIDTH + 10` durch den Ausdruck (`80 + 10`) ersetzt. Die Klammern um `WIDTH + 10` sind wichtig, da sie die Interpretation in Anweisungen steuern, z. B.:  
  
```  
var = LENGTH * 20;  
```  
  
 Nach der Vorverarbeitungsphase wird die Anweisung:  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 zu 1800 ausgewertet. Ohne Klammern wird das Ergebnis:  
  
```  
var = 80 + 10 * 20;  
```  
  
 die 280 ergibt.  
  
 **Microsoft-spezifisch**  
  
 Definieren von Makros und Konstanten mit der [/d](../build/reference/d-preprocessor-definitions.md) Compileroption hat dieselbe Wirkung wie die Verwendung einer `#define` -präprozessdirektive am Anfang der Datei. Maximal 30 Makros können mit der /D-Option definiert werden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)