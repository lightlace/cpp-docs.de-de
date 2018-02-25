---
title: _SCL_SECURE_NO_WARNINGS | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 285e54a2eab4d116df81c3e10c597c6dbb6dd9cb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS
Ein Aufruf einer der potenziell unsicheren Methoden in der C++-Standardbibliothek führt zu einer [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Um diese Warnung zu deaktivieren, definieren Sie das Makro **_SCL_SECURE_NO_WARNINGS** in Ihrem Code:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## <a name="remarks"></a>Hinweise  
 Weitere Methoden zum Deaktivieren der Warnung C4996 sind u.a.:  
  
-   Mithilfe der Compileroption [/D (Präprozessordefinitionen)](../build/reference/d-preprocessor-definitions.md):  
  
 ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
```  
  
-   Mithilfe der Compileroption [/w](../build/reference/compiler-option-warning-level.md):  
  
 ```  
    cl /wd4996 [other compiler options] myfile.cpp  
```  
  
-   Mithilfe der Anweisung [#pragma warning](../preprocessor/warning.md):  
  
 ```  
 #pragma warning(disable:4996)  
```  
  
 Sie können auch manuell ändern die Ebene der Warnung C4996 mit der **/w\<l >\< n>**  -Compileroption. Um beispielsweise die Warnung C4996 auf Stufe 4 festzulegen:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](../build/reference/compiler-option-warning-level.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)

