---
title: Kompilieren und Binden von Multithreadprogrammen
ms.date: 11/04/2016
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
ms.openlocfilehash: 3d98f5341de1374c9119e2a4303c94fcfb005e29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558885"
---
# <a name="compiling-and-linking-multithread-programs"></a>Kompilieren und Binden von Multithreadprogrammen

Bounce.c-Programm wird in eingeführt [Beispiel C-Multithreadprogramm](sample-multithread-c-program.md).

-Programme kompiliert werden standardmäßig mit Multithreading.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Zum Kompilieren und verknüpfen das Multithreadprogramm Bounce.c aus in der Entwicklungsumgebung

1. Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.

1. In der **Projekttypen** Bereich, klicken Sie auf **Win32**.

1. In der **Vorlagen** Bereich, klicken Sie auf **Win32-Konsolenanwendung**, und nennen Sie das Projekt.

1. Fügen Sie die Datei mit dem C-Quellcode zum Projekt hinzu.

1. Auf der **erstellen** im Menü Erstellen Sie das Projekt, indem Sie auf die **erstellen** Befehl.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Zum Kompilieren und verknüpfen das Multithreadprogramm Bounce.c über die Befehlszeile

1. Kompilieren Sie und binden Sie das Programm:

    ```
    CL BOUNCE.C
    ```

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)