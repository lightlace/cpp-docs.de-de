---
title: exception-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e9aac8e51764a50cd674c389b370ae0fa1a54415
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="exception-class"></a>exception-Klasse
Die Klasse dient als Basisklasse für alle Ausnahmen, die durch spezifische Ausdrücke und die C++-Standardbibliothek ausgelöst werden.  
  
## <a name="syntax"></a>Syntax  
```  
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };  
``` 
## <a name="remarks"></a>Hinweise  
 Diese Basisklasse bildet den Stamm der Standard Ausnahmeklassen, die in [\<stdexcept>](../standard-library/stdexcept.md) definiert sind. Der Wert der C-Zeichenfolge, der durch `what` zurückgegeben wird, wird vom Standardkonstruktor nicht angegeben, kann aber von den Konstruktoren für bestimmte abgeleitete Klassen als durch die Implementierung definierte C-Zeichenfolge angegeben werden. Keine der Memberfunktionen löst irgendeine Ausnahme aus.  
  
 Der Parameter `int` ermöglicht es anzugeben, dass kein Speicher zugewiesen werden soll. Der Wert von `int` wird ignoriert.  
  
> [!NOTE]
>  Die Konstruktoren `exception(const char* const &message)` und `exception(const char* const &message, int)` sind Microsoft-Erweiterungen der C++-Standardbibliothek.  
  
## <a name="example"></a>Beispiel  
 Beispiele für die Verwendung von Standard Ausnahmeklassen, die von der `exception`-Klasse erben, finden Sie in allen unter [ \<stdexcept >](../standard-library/stdexcept.md) definierten Klassen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<exception>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




