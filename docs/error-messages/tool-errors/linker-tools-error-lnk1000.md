---
title: Linkertoolfehler Lnk1000 | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1000
dev_langs:
- C++
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a01db36200995813ec4b6862e9ddd04c6f069ba
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238681"
---
# <a name="linker-tools-error-lnk1000"></a>Linkertoolfehler LNK1000

> Unbekannter Fehler; Dokumentation für die Optionen für technischen support

Notieren Sie die Umstände des Fehlers, und wiederholen Sie dann das Problem zu isolieren und einen reproduzierbaren Testfall zu erstellen. Informationen zum Überprüfen und diese Fehler melden, finden Sie unter [zum Melden eines Problems mit dem Visual C++-Toolsets oder Dokumentation](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md).

Dieser Fehler kann ausgegeben werden, wenn Sie die standardmäßigen Headerdateien (z. B. Windows.h) und Ihre eigenen Dateien kombinieren. Schließen Sie einen vorkompilierten Header, aus, wenn alle, zuerst, dann die Standardheader eigene Headerdateien folgen.