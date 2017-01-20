---
title: "Tokeneinf&#252;gender Operator (##)"
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
  - "##"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "##-Präprozessoroperator"
  - "Präprozessor, Operatoren"
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Tokeneinf&#252;gender Operator (##)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der double\-number\-sign\- oder "token\-pasting"\-Operator \(**\#\#**\), der gelegentlich als "zusammenführender" Operator bezeichnet wird, wird in objektähnlichen und funktionsähnlichen Makros verwendet.  Er ermöglicht die Verknüpfung separater Token zu einem Token und kann daher nicht der erste oder letzte Token in der Makrodefinition sein.  
  
 Wenn ein formaler Parameter in einer Makrodefinition dem Operator "token\-pasting" voran\- oder nachgestellt ist, wird der formale Parameter sofort durch das nicht erweiterte tatsächliche Argument ersetzt.  Die Makroerweiterung wird nicht vor der Ersetzung für das Argument ausgeführt.  
  
 Anschließend wird jedes Vorkommen des token\-pasting\-Operators in *token\-string* entfernt und die voran\- oder nachgestellten Token werden verkettet.  Das daraus resultierende Token muss ein gültiges Token sein.  Ist dies der Fall, wird das Token auf eine mögliche Ersetzung überprüft, falls es einen Makronamen darstellt.  Der Bezeichner steht für den Namen, unter dem die verketteten Token vor der Ersetzung im Programm bekannt sind.  Jedes Token stellt ein an anderer Stelle definiertes Token dar, entweder im Programm oder in der Compilerbefehlszeile.  Leerzeichen, die dem Operator vor\- oder nachgestellt sind, sind optional.  
  
 In diesem Beispiel wird die Verwendung der Zeichenfolgenoperatoren und Operatoren zum Einfügen eines Tokens beim Festlegen der Programmausgabe veranschaulicht:  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 Beim Aufrufen eines Makros mit einem numerischen Argument wie  
  
```  
paster( 9 );  
```  
  
 gibt das Makro  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 aus, das zu Folgendem wird:  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## Beispiel  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
  **token9 \= 9**   
## Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)