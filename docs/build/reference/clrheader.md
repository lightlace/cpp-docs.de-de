---
title: /CLRHEADER
ms.date: 11/04/2016
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: e35cf79cdaa10c9632e1c588e2b49f45cfbef283
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330852"
---
# <a name="clrheader"></a>/CLRHEADER

Anzeigen von CLR-spezifische Informationen.

## <a name="syntax"></a>Syntax

> / CLRHEADER *Datei*

### <a name="arguments"></a>Argumente

*datei*<br/>
Eine Bilddatei mit erstellten ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Hinweise

**/ CLRHEADER** werden Informationen über die verwendeten in verwalteten Programmen angezeigt. Die Ausgabe zeigt den Speicherort und die Größe in Bytes, die .NET Header und die Abschnitte in der Kopfzeile an.

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

Wenn **"/ CLRHEADER"** wird verwendet, auf eine Datei, die mit "/ CLR" kompiliert wurde, wird eine **Clr-Header:** Abschnitt in der Ausgabe von Dumpbin. Der Wert des **Flags** gibt an, welche Option "/ CLR" verwendet wurde:

- 0 – "/ CLR" (Image darf nativen Code).

Sie können auch programmgesteuert überprüfen, ob ein Bild für die common Language Runtime erstellt wurde.  Weitere Informationen finden Sie unter [wie: bestimmen, ob ein Bild nativ oder CLR ist](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Code, der "rein" oder "sicher" sein muss portiert werden soll, um C#.

## <a name="see-also"></a>Siehe auch

- [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)
