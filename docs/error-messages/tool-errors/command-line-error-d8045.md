---
title: Befehlszeilenfehler D8045 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8045
dev_langs:
- C++
helpviewer_keywords:
- D8045
ms.assetid: 01c8808c-bac1-4b4d-8a90-b595f95e9318
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6838202178e8012df61d17e2434461d6f4858bf3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022785"
---
# <a name="command-line-error-d8045"></a>Befehlszeilenfehler D8045

C-Datei 'File', mit der Option "/ CLR" kann nicht kompiliert werden.

Nur C++-Quellcodedateien übergeben werden können, um eine Kompilierung, die verwendet **"/ CLR"**.  Verwendung **/TP** zum Kompilieren einer .c-Datei als .cpp-Datei; finden Sie unter [/TC, / TP, / TC, / TP (Typ der Quelldatei angeben)](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) für Weitere Informationen.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

D8045 kann auch auftreten, wenn Sie mit Visual C++ ATL-Anwendungen kompilieren. Finden Sie unter [Vorgehensweise: Migrieren auf/CLR](../../dotnet/how-to-migrate-to-clr.md) für Weitere Informationen.