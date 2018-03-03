---
title: SAL-Anmerkungen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __z annotation
- ref annotation
- _opt annotation
- __checkreturn annotatioin
- __deref_opt annotation
- deref_opt annotation
- __deref annotation
- __in annotation
- annotations [C++]
- z annotation
- _inout annotation
- __ref annotation
- full annotation
- _in annotation
- _ref annotation
- __out annotation
- _ecount annotation
- SAL annotations
- __opt annotation
- inout annotation
- in annotation
- _CA_SHOULD_CHECK_RETURN
- __bcount annotation
- _full annotation
- _bcount annotation
- deref annotation
- part annotation
- _out annotation
- __nz annotation
- __part annotation
- opt annotation
- __full annotation
- _nz annotation
- _z annotation
- out annotation
- __ecount annotation
- __inout annotation
- SAL annotations, _CA_SHOULD_CHECK_RETURN
- _deref_opt annotation
- _deref annotation
- nz annotation
- _part annotation
- ecount annotation
- bcount annotation
ms.assetid: 81893638-010c-41a0-9cb3-666fe360f3e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79e10e9b93beb811f42e15574014df6a464aadb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sal-annotations"></a>SAL-Anmerkungen
Wenn Sie die Headerdateien der Bibliothek untersuchen, fallen Ihnen unter Umständen einige ungewöhnliche Anmerkungen auf, z. B. `_In_z` und `_Out_z_cap_(_Size)`. Dies sind Beispiele für die Microsoft-Quellcodeanmerkungssprache (Source-Code Annotation Language, SAL). Mit den darin verfügbaren Anmerkungen kann beschrieben werden, wie eine Funktion ihre Parameter verwendet, z. B. die getroffenen Annahmen und die Garantien für den Abschluss. In der Headerdatei \<sal.h> sind die Anmerkungen definiert.  
  
 Weitere Informationen zur Verwendung von SAL-Anmerkungen in Visual Studio finden Sie unter [Verwenden von SAL-Anmerkungen zum Reduzieren von C/C++-Codefehlern](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)