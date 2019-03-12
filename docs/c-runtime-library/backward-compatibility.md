---
title: Abwärtskompatibilität
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: f672f0601a9d20a726f90963265d08ec212dedce
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744471"
---
# <a name="backward-compatibility"></a>Abwärtskompatibilität

Um Kompatibilität zwischen Produktversionen bereitzustellen, ordnet die Bibliothek „OLDNAMES.LIB“ alte Namen neuen Namen zu. Beispielsweise wird `open` `_open` zugeordnet. Sie müssen nur dann eine explizite Verknüpfung mit OLDNAMES.LIB herstellen, wenn Sie mit Befehlszeilenoptionen in folgenden Kombinationen kompilieren:

- `/Zl`(Standardbibliotheknamen von Objektdatei unterdrücken) und `/Ze` (die Standardeinstellung – Microsoft-Erweiterungen verwenden)

- `/link`(Linker-Steuerelement), `/NOD` („no default library“-Suche) und`/Ze`

Weitere Informationen zu Compilerbefehlszeilenoptionen finden Sie unter [Compilerreferenz](../build/reference/compiler-options.md).

## <a name="see-also"></a>Siehe auch

[Kompatibilität](../c-runtime-library/compatibility.md)
