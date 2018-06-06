---
title: -CLRHEADER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6cda2f03e8a0473d2c45f54c96ca97b043d80d5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704440"
---
# <a name="clrheader"></a>/CLRHEADER

Zeigen Sie CLR-spezifische Informationen.

## <a name="syntax"></a>Syntax

> / CLRHEADER *Datei*

### <a name="arguments"></a>Argumente

|||
|-|-|
*datei*| Eine Bilddatei mit erstellten ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Hinweise

**/ CLRHEADER** zeigt Informationen über die .NET-Header, die in jeder verwalteten Anwendung verwendet. Die Ausgabe zeigt den Speicherort und die Größe in Bytes, die .NET Header und die Abschnitte in der Kopfzeile an.

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in den Dateien erstellt wird, mit der [/GL](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

Wenn **CLRHEADER** wird verwendet, auf eine Datei, die mit "/ CLR" kompiliert wurde, wird eine **Clr-Header:** Abschnitt in der Dumpbin-Ausgabe. Der Wert der **Flags** gibt an, welche Option "/ CLR" verwendet wurde:

- 0 – "/ CLR" (Image darf nativen Code).

Sie können auch programmgesteuert überprüfen, wenn ein Bild für die common Language Runtime erstellt wurde.  Weitere Informationen finden Sie unter [wie: bestimmen, ob ein Bild systemeigen oder CLR ist](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden. Code, der "rein" oder "sicheren" sein muss, sollten zu C#-portiert werden.

## <a name="see-also"></a>Siehe auch

- [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)
