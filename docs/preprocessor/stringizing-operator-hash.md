---
title: Zeichenfolgenoperator (#) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bbb1aa7db586a4b45084883491c8869b434eb8b
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538446"
---
# <a name="stringizing-operator-"></a>Zeichenfolgenoperator (#)
Das Nummernzeichen oder "Zeichenfolgenoperator" (**#**) konvertiert Makroparameter in Zeichenfolgenliterale, ohne die Parameterdefinition zu erweitern. Er wird nur mit Makros verwendet, die Argumente akzeptieren. Wenn er einem formalen Parameter in der Makrodefinition voransteht, ist das tatsächliche Argument, das vom Makroaufruf übergeben wird, in Anführungszeichen eingeschlossen und wird als Zeichenfolgenliteral behandelt. Das Zeichenfolgenliteral ersetzt dann jedes Vorkommen einer Kombination des Zeichenfolgenoperators und des formalen Parameters innerhalb der Makrodefinition.  
  
> [!NOTE]
> Die Erweiterung von Microsoft C (Version 6.0 und früher) für den ANSI C-Standard, die bisher formale Makroargumente in Zeichenfolgenliteralen und Zeichenkonstanten erweiterte, wird nicht mehr unterstützt. Code, der auf diese Erweiterung baute umgeschrieben werden mithilfe des Zeichenfolgenoperators (**#**) Operator.  
  
Das Leerzeichen vor dem ersten Token des tatsächlichen Arguments und nach dem letzten Token des tatsächlichen Arguments wird ignoriert. Jedes Leerzeichen zwischen den Token im tatsächlichen Argumente wird im resultierenden Zeichenfolgenliteral auf ein einzelnes Leerzeichen reduziert. Wenn also ein Kommentar zwischen zwei Token im tatsächlichen Argument auftritt, wird das Leerzeichen auf einen einzelnes Leerzeichen reduziert. Das sich ergebende Zeichenfolgenliteral wird automatisch mit allen angrenzenden Zeichenfolgenliteralen verkettet, von denen es nur durch ein Leerzeichen getrennt ist.  
  
Wenn ein Zeichen im Argument enthalten sind, in der Regel eine Escapesequenz, die bei der Verwendung in einem Zeichenfolgenliteral erfordert darüber hinaus (z. B. das Anführungszeichen (**"**) oder umgekehrten Schrägstrich (**\\**) Zeichen), wird die erforderliche Escapezeichen automatisch vor dem Zeichen eingefügt.  
  
Der Zeichenfolgenoperator von Visual C++ verhält sich nicht ordnungsgemäß, wenn er mit Zeichenfolgen, die Escapesequenzen enthalten, verwendet wird. In diesem Fall generiert der Compiler [Compilerfehler C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).  
  
## <a name="examples"></a>Beispiele  

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