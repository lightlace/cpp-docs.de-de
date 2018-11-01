---
title: Schwerwiegender Fehler C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: f05f79ea78958a7d7a64f24bdce2d1151b93cdfb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596234"
---
# <a name="fatal-error-c1510"></a>Schwerwiegender Fehler C1510

Die Sprachressourcendatei "clui.dll" kann nicht geöffnet werden.

Der Compiler kann die Language-Ressourcen-DLL nicht laden.

Es gibt zwei häufige Ursachen für dieses Problem. Wenn Sie die 32-Bit-Compiler und Tools zu verwenden, kann dieser Fehler bei großen Projekten angezeigt wird, die mehr als 2 GB Arbeitsspeicher bei der ein Link zu verwenden. Eine mögliche Lösung auf 64-Bit-Windows-Systemen ist das systemeigene 64-Bit-oder cross-Compiler und Tools, um Ihren Code zu generieren. Diese nutzt die größeren Speicherplatz für 64-Bit-apps zur Verfügung. Wenn Sie einen 32-Bit-Compiler verwenden müssen, weil Sie auf einem 32-Bit-System ausgeführt werden, können Sie in einigen Fällen die Menge an Arbeitsspeicher zur Verfügung, an den Linker auf 3 GB erhöhen. Weitere Informationen finden Sie unter [4-GB-Optimierung: BCDEdit "und" Datei "Boot.ini"](https://msdn.microsoft.com/library/vs/alm/bb613473) und [BCDEdit/set Increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) Befehl.

Die andere häufige Ursache ist eine beschädigte oder unvollständige Installation von Visual Studio. In diesem Fall führen Sie das Installationsprogramm erneut aus, um reparieren oder installieren Sie Visual Studio an.
