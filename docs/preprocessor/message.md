---
title: Nachricht | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs:
- C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47b9fd580d1ebabf4352104fe49f1d3c982a49e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="message"></a>message
Sendet ein Zeichenfolgenliteral an die Standardausgabe, ohne die Kompilierung zu beenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein typisches Einsatzgebiet von der **Nachricht** Pragma zum Zeitpunkt der Kompilierung Meldungen angezeigt werden.  
  
 Die *Messagestring* Parameter kann ein Makro, das ein Zeichenfolgenliteral erweitert, und Sie können diese Makros in eine beliebige Kombination mit Zeichenfolgenliteralen verkettet werden.  
  
 Wenn Sie ein vordefiniertes Makro im Verwenden der **Nachricht** Pragma sollte das Makro eine Zeichenfolge zurückgegeben, andernfalls müssen Sie die Ausgabe des Makros in eine Zeichenfolge konvertiert.  
  
 Das folgende Codefragment verwendet den **Nachricht** Pragma verwenden, um Nachrichten während der Kompilierung anzuzeigen:  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)