---
title: 4.4 OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1779b75774a2177a0d6a4f0661406e28b479a7ee
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
Die `OMP_NESTED` Umgebungsvariable aktiviert oder geschachtelte Parallelität deaktiviert, es sei denn, geschachtelte Parallelität aktiviert oder werden, durch Aufrufen deaktiviert der `o` **Mp_set_nested** Bibliotheksroutine. Wenn auf festgelegt **"true"**, geschachtelte Parallelität aktiviert ist; Wenn sie, um festgelegt ist **"false"**, geschachtelte Parallelität deaktiviert ist. Der Standardwert ist **"false"**.  
  
 Beispiel:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>Referenz:  
  
-   `omp_set_nested` funktionieren, finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf der Seite "40".