---
title: Schwerwiegender Fehler C1060 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1961784efc61c3c31f87c76cd2bdfe00fe954c5d
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820699"
---
# <a name="fatal-error-c1060"></a>Schwerwiegender Fehler C1060

Kein verfügbarer Speicher mehr im Heap

Das Betriebssystem oder die Laufzeitbibliothek können keine Speicheranforderung füllen.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Versuchen Sie zum Beheben dieses Fehlers die folgenden Lösungen 

1. Wenn der Compiler auch Fehler gibt [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) und [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), verwenden Sie die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) -Compileroption verwenden, um die maximale speicherzuweisung zu senken. Mehr Heapspeicher ist für Ihre Anwendung verfügbar, wenn Sie die verbleibende Speicherzuweisung reduzieren.

     Wenn die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) -Option bereits festgelegt ist, versuchen Sie es zu entfernen. Der Heap-Speicher ist möglicherweise erschöpft, weil die in der Option angegebene maximale Speicherzuweisung zu hoch ist. Der Compiler verwendet eine Standardgrenze, wenn Sie entfernen die [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) Option.

1. Wenn Sie auf einer 64-Bit-Plattform kompilieren, verwenden Sie das 64-Bit-Compilertoolset. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren ein 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. Auf 32-Bit-Windows, versuchen Sie es mit der [/3 GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) Switch "Boot.ini".

1. Vergrößern Sie die Windows-Auslagerungsdatei.

1. Schließen Sie andere ausgeführte Programme.

1. Löschen Sie überflüssige Includedateien.

1. Entfernen Sie unnötige globale Variablen, indem Sie beispielsweise Speicher dynamisch belegen, anstatt ein umfangreiches Array zu deklarieren.

1. Entfernen Sie nicht benötigte Deklarationen.

9. Teilen Sie die aktuelle Datei in kleinere Dateien auf.