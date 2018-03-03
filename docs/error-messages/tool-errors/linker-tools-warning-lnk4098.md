---
title: Linkertoolwarnung Lnk4098 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4098
dev_langs:
- C++
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b199c19417d7d3be866109fff7361fb4ead959d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4098"></a>Linkertoolwarnung LNK4098
DEFAULTLIB 'Bibliothek' steht in Konflikt mit anderen Bibliotheken verwenden. NODEFAULTLIB verwenden  
  
 Sie versuchen, eine Verknüpfung mit nicht kompatiblen Bibliotheken.  
  
> [!NOTE]
>  Die Laufzeitbibliotheken enthalten jetzt die Direktive, um zu verhindern, dass das Mischen von anderen Typen. Sie erhalten diese Warnung an, wenn Sie versuchen, verschiedene Arten verwenden oder das Debuggen und nicht-Debugversionen der Laufzeitbibliothek im selben Programm. Z. B. Wenn Sie eine Datei kompiliert, um eine Art von Laufzeit-Bibliothekscode und ein anderes-Datei, um eine andere Art (z. B. Singlethreaded gegenüber multithreaded) verwenden, und es wurde versucht, sie verknüpfen verwenden, wird diese Warnung angezeigt. Sie sollten alle Quelldateien zum Verwenden der gleichen Laufzeit-Bibliothek zu kompilieren. Finden Sie unter der [Use Run-Time Library](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **/MT**, **/ld**) Compileroptionen für Weitere Informationen.  
  
 Sie können des Linkers [/verbose: lib](../../build/reference/verbose-print-progress-messages.md) wechseln, um zu bestimmen, welche Bibliotheken vom Linker gesucht wird. Wenn LNK4098 und möchten eine ausführbare Datei erstellen, die z. B. die Singlethread verwendet, erhalten Sie nicht-Debug-Laufzeitbibliotheken, verwenden Sie die **/verbose: lib** Option aus, um herauszufinden, welche Bibliotheken der Linker sucht. Der Linker sollte LIBC.lib und nicht "LIBCMT.lib", MSVCRT.lib, LIBCD.lib, LIBCMTD.lib oder MSVCRTD.lib als gesuchte Bibliotheken ausgeben. Sie können feststellen, dass den Linker die falsche Laufzeitbibliotheken zu ignorieren, indem Sie mithilfe von [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für jede Bibliothek, die Sie ignorieren möchten.  
  
 Die folgende Tabelle zeigt, welche Bibliotheken ignoriert werden soll, abhängig von der Laufzeitbibliothek verwendet werden sollen.  
  
|Um diese Laufzeit-Bibliothek verwendet|Diese Bibliotheken ignorieren|  
|-----------------------------------|----------------------------|  
|Singlethread-(libc.lib)|"LIBCMT.lib", msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Multithreaded ("LIBCMT.lib")|libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Multithreaded-DLL (msvcrt.lib) verwenden|libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Debuggen von einem einzelnen Thread (libcd.lib)|libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|Debuggen von mehreren Threads (libcmtd.lib)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|Debuggen von Multithreaded-DLL (msvcrtd.lib) verwenden|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 Beispielsweise, wenn Sie diese Warnung empfangen und eine ausführbare Datei zu erstellen, die nicht-Debug, Singlethread-Version der Laufzeitbibliotheken verwendet, werden sollen, können die folgenden Optionen mit dem Linker Sie:  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```