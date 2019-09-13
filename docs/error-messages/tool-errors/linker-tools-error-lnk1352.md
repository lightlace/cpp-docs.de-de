---
title: Linker-Tools-Fehler LNK1352
description: Linkertoolfehler LNK1352 tritt auf, wenn versucht wird, einen nicht unterstützten Abschnitt zusammenzuführen.
ms.date: 09/10/2019
f1_keywords:
- LNK1352
helpviewer_keywords:
- LNK1352
ms.openlocfilehash: 38f773bfd669529dfb1ada9c7bb59e6f0962c9c7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908393"
---
# <a name="linker-tools-error-lnk1352"></a>Linker-Tools-Fehler LNK1352

> "*section_name_1*" und "*section_name_2*" können nicht in verschiedenen Abschnitten zusammengeführt werden.

## <a name="remarks"></a>Hinweise

Der Linker hat eine nicht zulässige Abschnitts Zusammenführung erkannt, da *section_name_1* und *section_name_2* im gleichen Abschnitt zusammengeführt werden müssen. Dieser Fehler tritt beispielsweise auf, wenn der Linker einen Versuch erkennt, den `.stls` Abschnitt und den `.tls` Abschnitt in verschiedenen Abschnitten zusammenzuführen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Aktivieren Sie die [/Merge](../../build/reference/merge-combine-sections.md) -Option in der Linkerbefehlszeile für dieses Problem.

## <a name="see-also"></a>Siehe auch

[Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
