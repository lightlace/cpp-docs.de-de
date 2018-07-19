---
title: Varargs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7b71cd426bc89570f9d394f3e38dc7a002f6e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380507"
---
# <a name="varargs"></a>VarArgs
Wenn Parameter über Varargs (z. B. mit den Auslassungspunkten Argumente) übergeben werden, gilt im Wesentlichen die normale Parameter übergeben, einschließlich Überlaufs die fünfte und nachfolgende Argumente. Es wird erneut die aufgerufene Dump-Argumenten, deren Adresse akzeptiert haben. Nur Gleitkommawerte werden die ganze Zahl und die Gleitkommaregister enthalten, wenn von der aufgerufene den Wert in der Ganzzahlregister erwartet.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)