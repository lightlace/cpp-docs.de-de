---
title: Includedateien für Multithreading
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
ms.openlocfilehash: 79b5c56eecfaf28743eec4ba6b4cee56156d6e2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212895"
---
# <a name="include-files-for-multithreading"></a>Includedateien für Multithreading

Standard-Includedateien Funktionen der C-Laufzeitbibliothek zu deklarieren, wie sie in den Bibliotheken implementiert sind. Bei Verwendung der [Komplette Optimierung](../build/reference/ox-full-optimization.md) (/ Ox) oder [Fastcall-Aufrufkonvention](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) auswählen, nimmt der Compiler an, dass alle Funktionen mit der Registrierung, die Aufrufkonvention aufgerufen werden soll. Die Funktionen der Laufzeitbibliothek kompiliert wurden, verwenden die C-Aufrufkonvention, und die Deklarationen in den Standardincludedateien teilen dem Compiler zum richtigen externen Verweise auf diese Funktionen zu generieren.

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)
