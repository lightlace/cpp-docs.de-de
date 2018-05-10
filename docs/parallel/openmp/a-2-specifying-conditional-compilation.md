---
title: Angeben der bedingten Kompilierung a. 2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d54245a2df2f38bed2674a3bb3923f8212d35459
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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