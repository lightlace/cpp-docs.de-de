---
title: – BEREICH | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e7525b8c1872616182141d624bff8f94571952
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712191"
---
# <a name="range"></a>/RANGE

Ändert die Ausgabe des Dumpbin bei Verwendung mit anderen Dumpbin-Optionen, z. B./RAWDATA oder DISASM an.

## <a name="syntax"></a>Syntax

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>Parameter

*vaMin*<br/>
Die virtuelle Adresse, an der Sie der Dumpbin beginnen soll.

*vaMax*<br/>
(Optional) Die virtuelle Adresse, an der Sie der Dumpbin enden soll. Wenn nicht angegeben ist, wechseln an das Ende der Datei Dumpbin.

## <a name="remarks"></a>Hinweise

Um die virtuellen Adressen für ein Bild anzuzeigen, verwenden Sie die Map-Datei für das Image (RVA + Basis), die **DISASM** oder **/Headers** Option von Dumpbin oder das Disassemblyfenster in Visual Studio-Debugger.

## <a name="example"></a>Beispiel

In diesem Beispiel **/range** wird verwendet, um die Anzeige des Ändern der **DISASM** Option. In diesem Beispiel ist der Startwert wird als Dezimalzahl ausgedrückt, und der Endwert als hexadezimale Zahl angegeben ist.

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)