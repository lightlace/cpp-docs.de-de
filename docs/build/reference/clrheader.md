---
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 5974606448dad103c8f12a126b8d17c688927c88
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837163"
---
# <a name="clrheader"></a>/CLRHEADER

Anzeigen von CLR-spezifischen Informationen.

## <a name="syntax"></a>Syntax

> /CLRHEADER *Datei*

### <a name="arguments"></a>Argumente

*datei*<br/>
Eine mit [/clr](clr-common-language-runtime-compilation.md) erstellte Builddatei.

## <a name="remarks"></a>Anmerkungen

**/CLRHEADER** zeigt Informationen über die in jedem verwalteten Programm verwendeten .NET-Header an. Die Ausgabe zeigt den Speicherort und die Größe in Byte des .NET-Headers und der Abschnitte im Header.

Für Dateien, die mit der [/GL](gl-whole-program-optimization.md)-Compileroption erstellt wurden, kann nur die Option [/HEADERS](headers.md) DUMPBIN verwendet werden.

Wenn **/CLRHEADER** auf eine Datei angewendet wird, die mit /clr kompiliert wurde, enthält die Dumpbin-Ausgabe einen Abschnitt **clr Header:** . Der Wert von **flags** gibt an, welche /clr-Option verwendet wurde:

- 0  -- /clr (das Image enthält möglicherweise nativen Code).

Sie können auch programmgesteuert prüfen, ob ein Image für die Common Language Runtime erstellt wurde.  Weitere Informationen finden Sie unter [Vorgehensweise: Bestimmen, ob ein Image nativ oder CLR ist](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet und werden in Visual Studio 2017 und höher nicht unterstützt. Code, der "pure" oder "safe" sein muss, sollte nach C# portiert werden.

## <a name="see-also"></a>Siehe auch

- [DUMPBIN-Optionen](dumpbin-options.md)
