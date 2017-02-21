---
title: "bad_exception-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.bad_exception"
  - "bad_exception"
  - "std::bad_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_exception-Klasse"
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# bad_exception-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse beschreibt eine Ausnahme, die über einen unerwarteten Handler ausgelöst werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Hinweise  
 [Unerwarteter](../Topic/%3Cexception%3E%20functions.md#unexpected) löst eine `bad_exception` anstatt beendet oder anstelle der Aufruf einer anderen Funktion angegeben, die mit [Set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) Wenn `bad_exception` ist in der Throw-Liste einer Funktion enthalten.  
  
 Der Rückgabewert von **Was** ist eine implementierungsdefinierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.  
  
 Eine Liste der von geerbten Membern der `bad_exception` Klasse, finden Sie unter [Exception-Klasse](../standard-library/exception-class1.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) für ein Beispiel für die Verwendung von [Unerwarteter](../Topic/%3Cexception%3E%20functions.md#unexpected) Auslösen einer `bad_exception`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Ausnahme>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
[Exception-Klasse](../standard-library/exception-class1.md)
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

