---
title: Schwerwiegender Fehler C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: 33c17a3099f4aed99cc26579d0e65c4a350b4268
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501095"
---
# <a name="fatal-error-c1510"></a>Schwerwiegender Fehler C1510

Die Sprachressourcendatei "clui.dll" kann nicht geöffnet werden.

Der Compiler kann die Sprachressourcen-dll nicht laden.

Es gibt zwei Häufige Gründe für dieses Problem. Wenn Sie den 32-Bit-Compiler und-Tools verwenden, wird dieser Fehler möglicherweise für große Projekte angezeigt, die während einer Verknüpfung mehr als 2 GB Arbeitsspeicher verwenden. Eine mögliche Lösung auf 64-Bit-Windows-Systemen ist die Verwendung des systemeigenen 64-Bit-oder Cross-Compilers und der Tools, um Ihren Code zu generieren. Dies nutzt den größeren Speicherplatz, der für 64-Bit-apps verfügbar ist. Wenn Sie einen 32-Bit-Compiler verwenden müssen, da Sie auf einem 32-Bit-System ausgeführt werden, können Sie in einigen Fällen die für den Linker verfügbare Menge an Arbeitsspeicher auf 3 GB erhöhen. Weitere Informationen finden [Sie unter 4-Gigabyte-Optimierung: Bcdedit und Boot. ini](/windows/win32/memory/4-gigabyte-tuning) und der [bcdedit/set erstelleuserva](/windows-hardware/drivers/devtest/bcdedit--set) -Befehl.

Die andere häufige Ursache ist eine fehlerhafte oder unvollständige Visual Studio-Installation. Führen Sie in diesem Fall den Installer erneut aus, um Visual Studio zu reparieren oder neu zu installieren.
