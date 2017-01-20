---
title: "Zeichenfolgenoperator (#)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "#"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#-Präprozessoroperator"
  - "Argumente [C++], Konvertieren in Zeichenfolgen"
  - "Makros [C++], Konvertieren von Parametern in Zeichenfolgen"
  - "Präprozessor"
  - "Präprozessor, Operatoren"
  - "Zeichenfolgenliterale, Konvertieren von Makroparametern in"
  - "Zeichenfolgenoperator"
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Zeichenfolgenoperator (#)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Nummernzeichen\- oder Zeichenfolgenoperator \(**\#**\) konvertiert Makroparameter in Zeichenfolgenliterale, ohne die Parameterdefinition zu erweitern.  Er wird nur mit Makros verwendet, die Argumente akzeptieren.  Wenn er einem formalen Parameter in der Makrodefinition voransteht, ist das tatsächliche Argument, das vom Makroaufruf übergeben wird, in Anführungszeichen eingeschlossen und wird als Zeichenfolgenliteral behandelt.  Das Zeichenfolgenliteral ersetzt dann jedes Vorkommen einer Kombination des Zeichenfolgenoperators und des formalen Parameters innerhalb der Makrodefinition.  
  
> [!NOTE]
>  Die Erweiterung von Microsoft C \(Version 6.0 und früher\) für den ANSI C\-Standard, die bisher formale Makroargumente in Zeichenfolgenliteralen und Zeichenkonstanten erweiterte, wird nicht mehr unterstützt.  Code, der auf diese Erweiterung baute, sollte mithilfe des Zeichenfolgenoperators \(**\#**\) umgeschrieben werden.  
  
 Das Leerzeichen vor dem ersten Token des tatsächlichen Arguments und nach dem letzten Token des tatsächlichen Arguments wird ignoriert.  Jedes Leerzeichen zwischen den Token im tatsächlichen Argumente wird im resultierenden Zeichenfolgenliteral auf ein einzelnes Leerzeichen reduziert.  Wenn also ein Kommentar zwischen zwei Token im tatsächlichen Argument auftritt, wird das Leerzeichen auf einen einzelnes Leerzeichen reduziert.  Das sich ergebende Zeichenfolgenliteral wird automatisch mit allen angrenzenden Zeichenfolgenliteralen verkettet, von denen es nur durch ein Leerzeichen getrennt ist.  
  
 Wenn darüber hinaus ein Zeichen, das im Argument enthalten ist, normalerweise eine Escapesequenz erfordert, wenn es in einem Zeichenfolgenliteral verwendet wird \(z. B. das Anführungszeichen \(**"**\) oder der umgekehrte Schrägstrich \(**\\**\)\), wird das erforderliche Escapezeichen automatisch vor dem Zeichen eingefügt.  
  
 Der Zeichenfolgenoperator von Visual C\+\+ verhält sich nicht in allen Fällen erwartungsgemäß. Weitere Informationen finden Sie unter [16.3.2 Der \#\-Operator](../misc/16-3-2-the-hash-operator.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Makrodefinition, welche den Zeichenfolgenoperator und eine Hauptfunktion umfasst, die das Makro aufruft:  
  
 Solche Aufrufe würden während der Vorverarbeitung erweitert und den folgenden Code ergeben:  
  
```  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
  **In Anführungszeichen im printf\-Funktionsaufruf**  
**"In Anführungszeichen, wenn auf dem Bildschirm ausgegeben"**  
**"This: \\" druckt ein doppeltes Anführungszeichen mit Escapezeichen"**   
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Makroparameter erweitert werden kann:  
  
```  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)