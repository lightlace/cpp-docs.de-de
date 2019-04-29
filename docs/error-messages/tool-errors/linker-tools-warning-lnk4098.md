---
title: Linkertoolwarnung LNK4098
ms.date: 03/26/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 66cf1a1bc75405ffc9bae8158bfc8682776a8228
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408094"
---
# <a name="linker-tools-warning-lnk4098"></a>Linkertoolwarnung LNK4098

> DEFAULTLIB "*Bibliothek*" verursacht einen Konflikt mit anderen Bibliotheken; verwenden Sie die/NODEFAULTLIB:*Bibliothek*

Sie versuchen, eine Verknüpfung mit nicht kompatiblen Bibliotheken herstellen.

> [!NOTE]
> Die Run-Time-Bibliotheken enthalten nun Anweisungen, um zu verhindern, mischen verschiedene Arten. Sie erhalten diese Warnung, wenn Sie versuchen, verschiedene Protokolltypen verwenden, oder das Debuggen und die nichtdebug-Versionen der Laufzeit-Bibliothek im selben Programm. Z. B., wenn Sie eine Datei für eine bestimmte Art von Laufzeit-Bibliothek zu verwenden und eine andere Datei mit einer anderen Art kompiliert (z. B. im Vergleich zu im Einzelhandel Debuggen) und versucht haben, verknüpfen, erhalten Sie diese Warnung. Sie sollten alle Quelldateien, die Verwendung die gleiche Laufzeit-Bibliothek kompilieren. Weitere Informationen finden Sie unter den [/MD, / MT, / ld (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) Compileroptionen.

Sie können des Linkers [/verbose: lib](../../build/reference/verbose-print-progress-messages.md) wechseln, um herauszufinden, welche Bibliotheken der Linker sucht. Z. B. wenn die ausführbare Datei der mehrerer Threads und nicht-Debug-Laufzeitbibliotheken verwendet wird, sollte die angegebenen Liste "LIBCMT.lib", und nicht "LIBCMTD.lib", "Msvcrt.lib" oder "MSVCRTD.lib" enthalten. Sie können den Linker an, die falsche Laufzeit-Bibliotheken mit ignorieren anweisen [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für jede Bibliothek, die Sie ignorieren möchten.

Die folgende Tabelle zeigt, welche Bibliotheken ignoriert werden sollen, abhängig von der Laufzeitbibliothek verwendet werden sollen. Verwenden Sie in der Befehlszeile eine **/NODEFAULTLIB** Option für jede Bibliothek ignoriert werden sollen. In der Visual Studio-IDE, trennen Sie die Bibliotheken durch Semikolons getrennt im ignorieren der **bestimmte Standardbibliotheken ignorieren** Eigenschaft.

| Verwenden Sie diese Laufzeit-Bibliothek | Diese Bibliotheken ignorieren |
|-----------------------------------|----------------------------|
| Multithreaded ("LIBCMT.lib") | msvcrt.lib; libcmtd.lib; msvcrtd.lib |
| Multithreaded-DLL ("Msvcrt.lib") verwenden | libcmt.lib; libcmtd.lib; msvcrtd.lib |
| Debuggen von Multithreadanwendungen ("LIBCMTD.lib") | libcmt.lib; msvcrt.lib; msvcrtd.lib |
| Debuggen von Multithreaded-DLL ("MSVCRTD.lib") verwenden | libcmt.lib; msvcrt.lib; libcmtd.lib |

Beispielsweise wird durch eine ausführbare Datei erstellt werden soll, wenn Sie diese Warnung erhalten, die nicht-Debug,-DLL-Version der Runtime-Bibliotheken verwendet, können Sie die folgenden Optionen verwenden, mit dem Linker:

```cmd
/NODEFAULTLIB:libcmt.lib NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```