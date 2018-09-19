---
title: Linkertoolfehler Lnk2039 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac4fdde90911427a1a193bfb6f3a950a7bdcf180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081792"
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