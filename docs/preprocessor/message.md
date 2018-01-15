---
title: Nachricht | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs: C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad91fdc0fb024fe87c2096f91962f715c0835262
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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