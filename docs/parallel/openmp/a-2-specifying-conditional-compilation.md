---
title: Angeben der bedingten Kompilierung a. 2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93557eaae2c8661697f7bda383b50f2e1ba9e2cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a2---specifying-conditional-compilation"></a>A.2   Angeben der bedingten Kompilierung
Die folgenden Beispiele veranschaulichen die Verwendung von bedingten Kompilierung mithilfe der OpenMP-Makro `_OPENMP` ([Abschnitt 2.2](../../parallel/openmp/2-2-conditional-compilation.md) auf Seite "8"). Mit der OpenMP-Kompilierung der `_OPENMP` Makro definiert wird.  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 Der definierte Präprozessoroperator ermöglicht mehrere Makros in einer einzelnen Anweisung getestet werden.  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```