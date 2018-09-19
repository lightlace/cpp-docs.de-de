---
title: Linkertoolfehler Lnk2027 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 022e363af575e29e3085dcaec21257fa7e4ab5f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116843"
---
# <a name="linker-tools-error-lnk2027"></a>Linkertoolfehler LNK2027

nicht aufgelöster Modulverweis 'Modul'

Eine Datei, die an den Linker übergeben hat eine Abhängigkeit für ein Modul, die weder mit angegeben wurde **ASSEMBLYMODULE** noch direkt an den Linker übergeben.

Führen Sie eine der folgenden Schritte aus, um LNK2027 zu beheben:

- Übergeben Sie keine an den Linker die Datei, die das Modul abhängig ist.

- Geben Sie das Modul mit **ASSEMBLYMODULE**.

- Wenn das Modul eine sichere NETMODULE-Datei ist, übergeben Sie das Modul direkt an dem Linker an.

Weitere Informationen finden Sie unter [ASSEMBLYMODULE (Hinzufügen einer MSIL-Modul zur Assembly)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) und [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md).