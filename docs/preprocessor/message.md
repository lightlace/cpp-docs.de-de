---
title: "Meldung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "message_CPP"
  - "vc-pragma.message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message-Pragma"
  - "Pragmas, Meldung"
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Meldung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sendet ein Zeichenfolgenliteral an die Standardausgabe, ohne die Kompilierung zu beenden.  
  
## Syntax  
  
```  
  
#pragma message( messagestring )  
```  
  
## Hinweise  
 Eine typische Verwendung des **message**\-Pragmas ist es, zur Kompilierungszeit Informationsmeldungen anzuzeigen.  
  
 Der *messagestring*\-Parameter kann ein Makro sein, das zu einem Zeichenfolgenliteral erweitert wird, und diese Makros können in beliebiger Kombination mit Zeichenfolgenliteralen verkettet werden.  
  
 Wenn Sie ein vordefiniertes Makro im **message**\-Pragma verwenden, muss das Makro eine Zeichenfolge zurückgeben. Andernfalls müssen Sie die Ausgabe des Makros in eine Zeichenfolge konvertieren.  
  
 Das folgende Codefragment verwendet das **message**\-Pragma, um Meldungen während der Kompilierung anzuzeigen:  
  
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
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)