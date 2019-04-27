---
title: Linkertoolfehler LNK1000
ms.date: 06/18/2018
f1_keywords:
- LNK1000
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
ms.openlocfilehash: b0e6eb3ba44216e9300506eb84adb61a6529903d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255460"
---
# <a name="linker-tools-error-lnk1000"></a>Linkertoolfehler LNK1000

> Unbekannter Fehler Dokumentation für die Optionen für technischen support

Notieren Sie die Umstände des Fehlers, und versuchen Sie dann das Problem isolieren und einen reproduzierbaren Testfall zu erstellen. Weitere Informationen zum Überprüfen und diese Fehler zu melden, finden Sie unter [wie Melden eines Problems mit dem Visual C++-Toolset oder Dokumentation](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).

Sie erhalten diesen Fehler, wenn Sie die standardmäßigen Headerdateien (z. B. Windows.h) und Ihre eigenen Dateien kombinieren. Enthalten Sie einen vorkompilierten Header, aus, wenn alle, erste und dann die standard-Header, Ihren eigenen Headerdateien folgen.