---
title: Linkertoolwarnung LNK4098
description: Beschreibt, wie nicht kompatible Bibliotheken die Linkertools warnen Linkertoolwarnung LNK4098 und wie/NODEFAULTLIB verwendet wird, um Sie zu beheben.
ms.date: 12/02/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 9d0c7da0614651a98d5ed4f3bd3676c7d837ce67
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682943"
---
# <a name="linker-tools-warning-lnk4098"></a>Linkertoolwarnung LNK4098

> DEFAULTLIB '*Library*' verursacht einen Konflikt mit der Verwendung anderer libs; Verwenden von/NODEFAULTLIB:*Library*

Sie versuchen, eine Verknüpfung mit inkompatiblen Bibliotheken herzustellen.

> [!NOTE]
> Die Laufzeitbibliotheken enthalten nun Direktiven, um das Mischen verschiedener Typen zu verhindern. Diese Warnung wird angezeigt, wenn Sie versuchen, unterschiedliche Typen oder Debug-und nicht-Debugversionen der Lauf Zeit Bibliothek im selben Programm zu verwenden. Wenn Sie z. b. eine Datei für die Verwendung einer Lauf Zeit Bibliothek und eine andere Datei kompiliert haben (z. b. Debug und Retail) und versucht haben, Sie zu verknüpfen, wird diese Warnung angezeigt. Sie sollten alle Quelldateien kompilieren, um dieselbe Lauf Zeit Bibliothek zu verwenden. Weitere Informationen finden Sie unter den Compileroptionen [/MD,/MT,/LD (Lauf Zeit Bibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) .

Sie können den Schalter [/verbose: lib](../../build/reference/verbose-print-progress-messages.md) des Linker verwenden, um herauszufinden, welche Bibliotheken der Linker durchsucht. Wenn die ausführbare Datei z. b. die Multithread-Laufzeitbibliotheken verwendet, sollte die gemeldete Liste LIBCMT. lib enthalten, nicht LIBCMTD. lib, msvcrt. lib oder MSVCRTD. lib. Sie können den Linker anweisen, falsche Laufzeitbibliotheken mithilfe von [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für jede Bibliothek zu ignorieren, die Sie ignorieren möchten.

Die folgende Tabelle zeigt, welche Bibliotheken in Abhängigkeit von der zu verwendenden Lauf Zeit Bibliothek ignoriert werden sollten. Verwenden Sie in der Befehlszeile eine **/NODEFAULTLIB** -Option für jede Bibliothek, die ignoriert werden soll. Trennen Sie in der Visual Studio-IDE die Bibliotheken, die durch Semikolons ignoriert werden sollen, in der Eigenschaft **bestimmte Standardbibliotheken ignorieren** .

| So verwenden Sie diese Lauf Zeit Bibliothek | Diese Bibliotheken ignorieren |
|-----------------------------------|----------------------------|
| Multithreaded (LIBCMT. lib) | msvcrt. lib; LIBCMTD. lib; msvcrtd. lib |
| Multithreaded mithilfe von dll (msvcrt. lib) | LIBCMT. lib; LIBCMTD. lib; msvcrtd. lib |
| Multithreaded Debuggen (libcmtd. lib) | LIBCMT. lib; msvcrt. lib; msvcrtd. lib |
| Debuggen von Multithreaded mithilfe von dll (msvcrtd. lib) | LIBCMT. lib; msvcrt. lib; LIBCMTD. lib |

Wenn Sie z. b. diese Warnung erhalten haben und eine ausführbare Datei erstellen möchten, die die nicht-Debug-DLL-Version der Laufzeitbibliotheken verwendet, können Sie die folgenden Optionen für den Linker verwenden:

```cmd
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```
