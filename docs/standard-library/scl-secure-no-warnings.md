---
title: "_SCL_SECURE_NO_WARNINGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _SCL_SECURE_NO_WARNINGS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Aufrufen unsicheren möglicherweise eine der Methoden in der C\+\+\-Standardbibliothek führt unter [Compilerwarnung \(Stufe 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  Um diese Warnung zu deaktivieren, definieren Sie Makro\- **\_SCL\_SECURE\_NO\_WARNINGS** im Code:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## Hinweise  
 Andere Möglichkeiten, die Warnung enthält C4996 zu deaktivieren:  
  
-   Mit der Compileroption [\/D \(Präprozessordefinitionen\)](../build/reference/d-preprocessor-definitions.md):  
  
    ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
    ```  
  
-   Mit der Compileroption [\/w](../build/reference/compiler-option-warning-level.md):  
  
    ```  
    cl /wd4996 [other compiler options] myfile.cpp  
    ```  
  
-   Verwenden der [\#Pragmawarnung](../preprocessor/warning.md)\-Direktiven:  
  
    ```  
    #pragma warning(disable:4996)  
    ```  
  
 Außerdem können den Umfang des Warnens von C4996 mit der Compileroption **\/w\<l\>\<n\>** manuell ändern.  Beispielsweise Warnung C4996 auf Ebene 4 festlegen:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Weitere Informationen finden Sie unter [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../build/reference/compiler-option-warning-level.md).  
  
## Siehe auch  
 [Sichere Bibliotheken: C\+\+\-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)