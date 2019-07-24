---
title: Linkertoolfehler LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 57d0c101358f84816c8d0cf96eb5137833df0b48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298739"
---
# <a name="linker-tools-error-lnk2039"></a>Linkertoolfehler LNK2039

Importieren von Ref-Klasse\<Typ >' in another.obj definiert ist; es muss sich entweder importiert oder definiert werden, jedoch nicht beide

Die Ref-Klasse ' <`type`>' wurde in der angegebenen OBJ-Datei importiert, aber auch in einer anderen OBJ-Datei definiert ist. Diese Bedingung kann es sich um Laufzeitfehler oder anderes unerwartetes Verhalten verursachen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie, ob "`type`" muss in der OBJ-Datei definiert werden, und überprüfen Sie, ob sie aus der winmd-Datei importiert werden muss.

1. Entfernen Sie die Definition oder den Import.

## <a name="see-also"></a>Siehe auch

[Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Linkertoolfehler LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)