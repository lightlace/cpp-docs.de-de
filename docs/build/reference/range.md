---
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: c631057e47e1a52a58d2b1304133dfdfc008ae14
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810964"
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

[DUMPBIN-Optionen](dumpbin-options.md)
