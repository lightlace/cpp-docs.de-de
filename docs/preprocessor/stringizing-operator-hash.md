---
title: Zeichenfolgenoperator (#) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df61a50b9522c6631ca0b5f32d5c438369632d01
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="stringizing-operator-"></a>Zeichenfolgenoperator (#)
Der Nummernzeichen- oder "Zeichenfolgenoperator" (**#**) konvertiert Makroparameter in Zeichenfolgenliterale, ohne die Parameterdefinition zu erweitern. Er wird nur mit Makros verwendet, die Argumente akzeptieren. Wenn er einem formalen Parameter in der Makrodefinition voransteht, ist das tatsächliche Argument, das vom Makroaufruf übergeben wird, in Anführungszeichen eingeschlossen und wird als Zeichenfolgenliteral behandelt. Das Zeichenfolgenliteral ersetzt dann jedes Vorkommen einer Kombination des Zeichenfolgenoperators und des formalen Parameters innerhalb der Makrodefinition.  
  
> [!NOTE]
>  Die Erweiterung von Microsoft C (Version 6.0 und früher) für den ANSI C-Standard, die bisher formale Makroargumente in Zeichenfolgenliteralen und Zeichenkonstanten erweiterte, wird nicht mehr unterstützt. Code, der auf diese Erweiterung baute umgeschrieben werden mithilfe des Zeichenfolgenoperators (**#**) Operator.  
  
Das Leerzeichen vor dem ersten Token des tatsächlichen Arguments und nach dem letzten Token des tatsächlichen Arguments wird ignoriert. Jedes Leerzeichen zwischen den Token im tatsächlichen Argumente wird im resultierenden Zeichenfolgenliteral auf ein einzelnes Leerzeichen reduziert. Wenn also ein Kommentar zwischen zwei Token im tatsächlichen Argument auftritt, wird das Leerzeichen auf einen einzelnes Leerzeichen reduziert. Das sich ergebende Zeichenfolgenliteral wird automatisch mit allen angrenzenden Zeichenfolgenliteralen verkettet, von denen es nur durch ein Leerzeichen getrennt ist.  
  
Wenn darüber hinaus ein Zeichen im Argument enthalten ist, normalerweise eine Escapesequenz, die bei der Verwendung in einem Zeichenfolgenliteral erfordert (z. B. das Anführungszeichen (**"**) oder umgekehrten Schrägstrich (**\\**) Zeichen), die erforderliche Escapezeichen wird automatisch vor dem Zeichen eingefügt.  
  
Die Visual C++-Zeichenfolgenoperator verhält sich nicht ordnungsgemäß, wenn sie mit Zeichenfolgen verwendet wird, die Escapesequenzen enthalten. In diesem Fall generiert der Compiler [Compiler Fehler C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel zeigt eine Makrodefinition, welche den Zeichenfolgenoperator und eine Hauptfunktion umfasst, die das Makro aufruft:  
  
Solche Aufrufe würden während der Vorverarbeitung erweitert und den folgenden Code ergeben:  
  
```cpp  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```cpp  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
```Output  
In quotes in the printf function call  
"In quotes when printed to the screen"  
"This: \"  prints an escaped double quote"  
```  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel zeigt, wie ein Makroparameter erweitert werden kann:  
  
```cpp  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)