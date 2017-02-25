---
title: "&lt;exception&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<exception>"
  - "std::<exception>"
  - "std.<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception-Header"
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;exception&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert einige Typen und Funktionen, die mit der Behandlung von Ausnahmen in Beziehung stehen. Ausnahmebehandlung wird ist in Situationen verwendet, in denen das System von einem Fehler wiederhergestellt werden kann. Sie stellt eine Methode bereit, mit der die Steuerung von einer Funktion zum Programm zurückgegeben werden kann. Das Ziel der Integration der Ausnahmebehandlung ist, die Stabilität des Programms bei Bereitstellung einer Methode zur geordneten Wiederherstellung von einem Fehler zu erhöhen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[exception_ptr](../Topic/%3Cexception%3E%20typedefs.md#exception_ptr)|Ein Typ, der einen Zeiger auf eine Ausnahme beschreibt.|  
|[terminate_handler](../Topic/%3Cexception%3E%20typedefs.md#terminate_handler)|Ein Typ, der einen Zeiger auf eine Funktion beschreibt, die zur Verwendung als `terminate_handler` geeignet ist.|  
|[unexpected_handler](../Topic/%3Cexception%3E%20typedefs.md#unexpected_handler)|Ein Typ, der einen Zeiger auf eine Funktion beschreibt, die zur Verwendung als `unexpected_handler` geeignet ist.|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[current_exception](../Topic/%3Cexception%3E%20functions.md#current_exception)|Erhält einen Zeiger auf die aktuelle Ausnahme.|  
|[get_terminate](../Topic/%3Cexception%3E%20functions.md#get_terminate)|Ruft die aktuelle `terminate_handler`-Funktion ab.|  
|[get_unexpected](../Topic/%3Cexception%3E%20functions.md#get_unexpected)|Ruft die aktuelle `unexpected_handler`-Funktion ab.|  
|[make_exception_ptr](../Topic/%3Cexception%3E%20functions.md#make_exception_ptr)|Erstellt ein `exception_ptr`-Objekt, das eine Kopie einer Ausnahme enthält.|  
|[rethrow_exception](../Topic/%3Cexception%3E%20functions.md#rethrow_exception)|Löst eine Ausnahme aus, die als Parameter übergeben wird.|  
|[set_terminate](../Topic/%3Cexception%3E%20functions.md#set_terminate)|Richtet ein neues `terminate_handler`-Element ein, das bei Beendigung des Programms aufgerufen wird.|  
|[set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected)|Richtet ein neues `unexpected_handler` ein, das bei einer unerwarteten Ausnahme auftritt.|  
|[Beenden](../Topic/%3Cexception%3E%20functions.md#terminate)|Ruft einen terminate-Handler auf.|  
|[uncaught_exception](../Topic/%3Cexception%3E%20functions.md#uncaught_exception)|Gibt **"true"** nur, wenn eine ausgelöste Ausnahme gerade verarbeitet wird.|  
|[Unerwarteter](../Topic/%3Cexception%3E%20functions.md#unexpected)|Ruft einen unerwarteten Handler auf.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[Bad_exception-Klasse](../standard-library/bad-exception-class.md)|Die Klasse beschreibt eine Ausnahme, die von `unexpected_handler` ausgelöst werden kann.|  
|[Exception-Klasse](Exception%20Class.xml)|Die Klasse dient als Basisklasse für alle Ausnahmen, die durch spezifische Ausdrücke und die C++-Standardbibliothek ausgelöst werden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

