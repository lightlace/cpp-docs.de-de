---
title: "Tokeneinfügender Operator (##) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '##'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3a8c2cef3560a6823314a4edb2cba78994864ce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="token-pasting-operator-"></a>Tokeneinfügender Operator (##)
Die doppelten Nummernzeichen oder "Token-Pasting"-Operator (**##**), die den "Zusammenführen" Operator bezeichnet wird, wird in objektähnlichen und funktionsähnlichen Makros verwendet. Er ermöglicht die Verknüpfung separater Token zu einem Token und kann daher nicht der erste oder letzte Token in der Makrodefinition sein.  
  
 Wenn ein formaler Parameter in einer Makrodefinition dem Operator „token-pasting“ voran- oder nachgestellt ist, wird der formale Parameter sofort durch das nicht erweiterte tatsächliche Argument ersetzt. Die Makroerweiterung wird nicht vor der Ersetzung für das Argument ausgeführt.  
  
 Anschließend wird jedes Vorkommen des Token-Pasting-Operators in *-Token-String* wird entfernt, und die Token vorausgehende und folgende es verkettet werden. Das daraus resultierende Token muss ein gültiges Token sein. Ist dies der Fall, wird das Token auf eine mögliche Ersetzung überprüft, falls es einen Makronamen darstellt. Der Bezeichner steht für den Namen, unter dem die verketteten Token vor der Ersetzung im Programm bekannt sind. Jedes Token stellt ein an anderer Stelle definiertes Token dar, entweder im Programm oder in der Compilerbefehlszeile. Leerzeichen, die dem Operator vor- oder nachgestellt sind, sind optional.  
  
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
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)