---
title: Includedateien für Multithreading | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62b94f4a7a394b78cb7c6f23275709e4aeacc774
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685800"
---
# <a name="include-files-for-multithreading"></a>Includedateien für Multithreading
Standard-Includedateien C-Laufzeitbibliotheksfunktionen deklarieren, wie sie in den Bibliotheken implementiert werden. Bei Verwendung der [Komplette Optimierung](../build/reference/ox-full-optimization.md) (/ Ox) oder [Fastcall-Aufrufkonvention](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) auswählen, nimmt der Compiler an, dass alle Funktionen mit dem Register Aufrufkonvention aufgerufen werden soll. Die Run-Time Library-Funktionen im C-Aufrufkonvention kompiliert wurden, und die Deklarationen in der standardmäßigen Includedateien den Compiler aufzufordern, richtige externe Verweise auf diese Funktionen zu generieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)