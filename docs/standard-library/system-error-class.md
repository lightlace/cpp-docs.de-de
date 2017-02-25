---
title: "system_error-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::system_error"
  - "std.system_error"
  - "std::system_error"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error-Klasse"
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# system_error-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt die Basisklasse für alle Ausnahmen, die ausgelöst wird, um eine Low-Level Systemfehler zu melden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Rückgabewert von `what` in der Klasse [Ausnahme](../standard-library/exception-class1.md) aus erstellt wird `_Message` und das gespeicherte Objekt vom Typ [Error_code](../standard-library/error-code-class.md) (entweder `code` oder `error_code(_Errval, _Errcat)`).  
  
 Die Memberfunktion `code` Gibt das gespeicherte [Error_code](../standard-library/error-code-class.md) Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< System_error >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\< System_error >](../standard-library/system-error.md)

