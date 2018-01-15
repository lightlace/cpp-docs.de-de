---
title: "Includedateien für Multithreading | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f71b52bca5f636d80f2d55cc5e9ffc3e217d90a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="include-files-for-multithreading"></a>Includedateien für Multithreading
Standard-Includedateien C-Laufzeitbibliotheksfunktionen deklarieren, wie sie in den Bibliotheken implementiert werden. Bei Verwendung der [Komplette Optimierung](../build/reference/ox-full-optimization.md) (/ Ox) oder [Fastcall-Aufrufkonvention](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) auswählen, nimmt der Compiler an, dass alle Funktionen mit dem Register Aufrufkonvention aufgerufen werden soll. Die Run-Time Library-Funktionen im C-Aufrufkonvention kompiliert wurden, und die Deklarationen in der standardmäßigen Includedateien den Compiler aufzufordern, richtige externe Verweise auf diese Funktionen zu generieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)