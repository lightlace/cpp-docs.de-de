---
title: Linkertoolwarnung LNK4098 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4098
dev_langs:
- C++
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2068534d51ae1350510a349f875c1977299edb1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019151"
---
# <a name="linker-tools-warning-lnk4098"></a>Linkertoolwarnung LNK4098

Standardbibliothek "Library" steht in Konflikt mit anderen Bibliotheken verwenden; NODEFAULTLIB: Bibliothek verwenden

Sie möchten mit nicht kompatiblen Bibliotheken verknüpfen.

> [!NOTE]
>  Die Run-Time-Bibliotheken enthalten nun Anweisungen, um zu verhindern, mischen verschiedene Arten. Sie erhalten diese Warnung, wenn Sie versuchen, verschiedene Protokolltypen verwenden, oder das Debuggen und die nichtdebug-Versionen der Laufzeit-Bibliothek im selben Programm. Wenn Sie eine Datei kompiliert um eine Art von Laufzeit-Bibliothek und eine weitere-Datei, um eine andere Art (z. B. Singlethread-im Vergleich zu mehreren Threads) zu verwenden und versucht, sie verknüpfen, werden Sie z. B. diese Warnung angezeigt. Sie sollten alle Quelldateien, die Verwendung die gleiche Laufzeit-Bibliothek kompilieren. Finden Sie unter den [Use Run-Time Library](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **"/ MT"**, **/ld**) Compileroptionen für Weitere Informationen.

Sie können des Linkers [/verbose: lib](../../build/reference/verbose-print-progress-messages.md) wechseln, um zu bestimmen, welche Bibliotheken der Linker sucht. Wenn Sie LNK4098 erhalten und möchten eine ausführbare Datei zu erstellen, die z. B. die Single-Thread verwendet, nicht-Debug-Laufzeitbibliotheken, verwenden Sie die **/verbose: lib** Option, um herauszufinden, welche Bibliotheken der Linker sucht. Der Linker sollte als auf die durchsuchten Bibliotheken LIBC.lib und nicht "LIBCMT.lib", "Msvcrt.lib", LIBCD.lib, "LIBCMTD.lib" oder "MSVCRTD.lib" ausgeben werden. Sie können den Linker an, die falsche Laufzeit-Bibliotheken mit ignorieren anweisen [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für jede Bibliothek, die Sie ignorieren möchten.

Die folgende Tabelle zeigt, welche Bibliotheken ignoriert werden sollen, abhängig von der Laufzeitbibliothek verwendet werden sollen.

|Verwenden Sie diese Laufzeit-Bibliothek|Diese Bibliotheken ignorieren|
|-----------------------------------|----------------------------|
|Singlethread-(libc.lib)|"LIBCMT.lib", "Msvcrt.lib", libcd.lib, "LIBCMTD.lib", "MSVCRTD.lib"|
|Multithreaded ("LIBCMT.lib")|libc.lib, msvcrt.lib, libcd.lib, "LIBCMTD.lib", "MSVCRTD.lib"|
|Multithreaded-DLL ("Msvcrt.lib") verwenden|libc.lib, libcmt.lib, libcd.lib, "LIBCMTD.lib", "MSVCRTD.lib"|
|Singlethread-Debug (libcd.lib)|libc.lib, libcmt.lib, "Msvcrt.lib", "LIBCMTD.lib", "MSVCRTD.lib"|
|Debuggen von Multithreadanwendungen ("LIBCMTD.lib")|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, "MSVCRTD.lib"|
|Debuggen von Multithreaded-DLL ("MSVCRTD.lib") verwenden|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, "LIBCMTD.lib"|

Z. B. Wenn Sie diese Warnung erhalten, und eine ausführbare Datei zu erstellen, die die nichtdebug-Singlethread-Version der Runtime-Bibliotheken verwendet werden sollen, können Sie die folgenden Optionen mit dem Linker:

```
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```