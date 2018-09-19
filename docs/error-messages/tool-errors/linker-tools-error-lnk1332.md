---
title: Linkertoolfehler Lnk1332 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1332
dev_langs:
- C++
helpviewer_keywords:
- LNK1332
ms.assetid: b31d5ca0-c27f-4177-896b-2637dccbde24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b256c61b9e9de6bf19e754054de1f55fcdec5f0b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094519"
---
# <a name="linker-tools-error-lnk1332"></a>Linkertoolfehler LNK1332

erkannt\<Anzahl > Windows-Runtime-Typen in einem Modul importiert und in einem anderen Modul definiert

Wenn sie das aktuelle Ziel erstellt, der Linker erkannt <`count`> Windows-Runtime-Typen, von denen jedes in einem Modul importiert und auch in einem anderen Modul definiert ist.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Korrigieren Sie jeden LNK2039 Fehler im Build gemäß dem Vorschlag in der Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2039](../../error-messages/tool-errors/linker-tools-error-lnk2039.md)<br/>
[Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)