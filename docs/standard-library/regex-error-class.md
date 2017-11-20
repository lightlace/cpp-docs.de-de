---
title: regex_error-Klasse | Microsoft-Dokumente
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: a0336bce168edc8b4c50639b1e3ace4f82e7c971
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="regexerror-class"></a>regex_error-Klasse
Meldet ein ungültiges basic_regex-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class regex_error  
 : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;

 
 };  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse beschreibt ein Ausnahmeobjekt, das ausgelöst wurde, um einen Fehler bei der Erstellung oder Verwendung eines `basic_regex` -Objekts zu melden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<regex >  
  
 **Namespace:** std  
  
##  <a name="code"></a> regex_error::code  
 Gibt den Fehlercode zurück.  
  
```  
regex_constants::error_code code() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt den Wert zurück, der an den Konstruktor des Objekts übergeben wurde.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_error_code.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
##  <a name="regex_error"></a> regex_error::regex_error  
 Erstellt das Objekt.  
  
```  
regex_error(regex_constants::error_code error);
```  
  
### <a name="parameters"></a>Parameter  
 `error`  
 Der Fehlercode.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor erstellt ein Objekt, das den Wert `error`enthält.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__regex__regex_error_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
## <a name="see-also"></a>Siehe auch  
[\<regex>](../standard-library/regex.md)  
[regex_constants-Klasse](../standard-library/regex-constants-class.md)  
[\<regex>-Funktionen](../standard-library/regex-functions.md)  
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)  
[\<regex>-Operatoren](../standard-library/regex-operators.md)  
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)  
[regex_traits-Klasse](../standard-library/regex-traits-class.md)  
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)  
