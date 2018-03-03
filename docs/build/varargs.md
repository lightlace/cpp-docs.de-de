---
title: Varargs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3d22a5c3f20480d1e904ec8e087114385ba7ee9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="varargs"></a>VarArgs
Wenn Parameter über Varargs (z. B. mit den Auslassungspunkten Argumente) übergeben werden, gilt im Wesentlichen die normale Parameter übergeben, einschließlich Überlaufs die fünfte und nachfolgende Argumente. Es wird erneut die aufgerufene Dump-Argumenten, deren Adresse akzeptiert haben. Nur Gleitkommawerte werden die ganze Zahl und die Gleitkommaregister enthalten, wenn von der aufgerufene den Wert in der Ganzzahlregister erwartet.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)