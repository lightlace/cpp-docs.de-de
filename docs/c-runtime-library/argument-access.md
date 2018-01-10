---
title: Argumentzugriff | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.arguments
dev_langs: C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97db036822687936f3f8e4084c065c8ec64ca23e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="argument-access"></a>Argumentzugriff
Die Makros `va_arg`, `va_end` und `va_start` bieten Zugriff auf Funktionsargumente, wenn die Anzahl der Argumente eine Variable ist. Diese Makros sind in STDARG.H für die Kompatibilität mit ANSI-C und in VARARGS.H für die Kompatibilität mit UNIX System V definiert.  
  
### <a name="argument-access-macros"></a>Makros für den Argumentzugriff  
  
|Makro|Mit|  
|-----------|-------------------------------|  
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Argument aus der Liste abrufen|  
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Zeiger zurücksetzen|  
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Zeiger auf den Anfang der Liste der Argumente festlegen|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)