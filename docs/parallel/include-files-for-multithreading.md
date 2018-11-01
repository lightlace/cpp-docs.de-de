---
title: Includedateien für Multithreading | Microsoft-Dokumentation
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
ms.openlocfilehash: 64ba6ec639151ca659e3bd075f691176ef4edbdd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422323"
---
# <a name="include-files-for-multithreading"></a>Includedateien für Multithreading

Standard-Includedateien Funktionen der C-Laufzeitbibliothek zu deklarieren, wie sie in den Bibliotheken implementiert sind. Bei Verwendung der [Komplette Optimierung](../build/reference/ox-full-optimization.md) (/ Ox) oder [Fastcall-Aufrufkonvention](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) auswählen, nimmt der Compiler an, dass alle Funktionen mit der Registrierung, die Aufrufkonvention aufgerufen werden soll. Die Funktionen der Laufzeitbibliothek kompiliert wurden, verwenden die C-Aufrufkonvention, und die Deklarationen in den Standardincludedateien teilen dem Compiler zum richtigen externen Verweise auf diese Funktionen zu generieren.

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)