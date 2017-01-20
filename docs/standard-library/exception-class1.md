---
title: "exception-Klasse"
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
  - "std.exception"
  - "exception"
  - "std::exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception-Klasse"
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# exception-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse dient als Basisklasse für alle Ausnahmen, die durch spezifische Ausdrücke und die C\+\+\-Standardbibliothek ausgelöst werden.  
  
## Syntax  
  
```  
class exception {  
public:  
    exception();  
    exception(const char * const &message);  
    exception(const char * const &message, int);  
    exception(const exception &right);  
    exception& operator=(const exception &right);  
    virtual ~exception();  
    virtual const char *what() const;  
};  
```  
  
## Hinweise  
 Insbesondere ist diese Basisklasse der Stamm der Standardausnahmeklassen, die in [\<stdexcept\>](../standard-library/stdexcept.md) definiert werden.  Der C\-Zeichenfolgenwert, der von `what` zurückgegeben wird, wird links nicht angegeben vom Standardkonstruktor, jedoch wird der Konstruktoren für bestimmte abgeleitete Klassen als Implementierung\-definierte C\-Zeichenfolge definiert werden.  Keine der Memberfunktionen lösen alle Ausnahmen aus.  
  
 Der `int`\-Parameter ermöglicht, um anzugeben, dass kein Speicher belegt werden soll.  Der Wert `int` wird ignoriert.  
  
> [!NOTE]
>  Die Konstruktoren `exception(const char * const &message)` und `exception(const char * const &message, int)` sind Microsoft\-Erweiterungen der C\+\+\-Standardbibliothek.  
  
## Beispiel  
 Beispiele für die Verwendung von den Standardausnahmeklassen, die von der `exception`\-Klasse erben, finden Sie in den Klassen, die in [\<stdexcept\>](../standard-library/stdexcept.md) definiert werden.  
  
## Anforderungen  
 **Header:** \<exception\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)