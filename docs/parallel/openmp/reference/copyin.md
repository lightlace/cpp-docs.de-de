---
title: Copyin | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27afaee16a87ddf428570f7854212eed34634d38
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059328"
---
# <a name="copyin"></a>copyin
Ermöglicht die Threads der master-Thread-Wert, für den Zugriff auf eine [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) Variable.  
  
## <a name="syntax"></a>Syntax  
  
```  
copyin(var)  
```  
  
## <a name="parameters"></a>Parameter
  
*var*<br/>
Die `threadprivate` Variable, die mit dem Wert der Variablen in der master-Thread initialisiert wird, wie sie vor dem das parallele Konstrukt vorhanden ist.  
  
## <a name="remarks"></a>Hinweise  
 `copyin` gilt für die folgenden Anweisungen:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.7 Copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Threadprivate](../../../parallel/openmp/reference/threadprivate.md) ein Beispiel der Verwendung von `copyin`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)