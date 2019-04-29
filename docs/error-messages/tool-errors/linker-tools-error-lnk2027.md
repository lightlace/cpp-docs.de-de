---
title: Linkertoolfehler LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: e74912780bab3056ead36ae3705f0910805228e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299009"
---
# <a name="linker-tools-error-lnk2027"></a>Linkertoolfehler LNK2027

nicht aufgelöster Modulverweis 'Modul'

Eine Datei, die an den Linker übergeben hat eine Abhängigkeit für ein Modul, die weder mit angegeben wurde **ASSEMBLYMODULE** noch direkt an den Linker übergeben.

Führen Sie eine der folgenden Schritte aus, um LNK2027 zu beheben:

- Übergeben Sie keine an den Linker die Datei, die das Modul abhängig ist.

- Geben Sie das Modul mit **ASSEMBLYMODULE**.

- Wenn das Modul eine sichere NETMODULE-Datei ist, übergeben Sie das Modul direkt an dem Linker an.

Weitere Informationen finden Sie unter [ASSEMBLYMODULE (Hinzufügen einer MSIL-Modul zur Assembly)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) und [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md).