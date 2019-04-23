---
title: Empfohlene Tags für Dokumentationskommentare (C++-Dokumentationskommentare)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 2a6a2c3983c10579a6cd96b69be81aa7df8b8ee7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027895"
---
# <a name="recommended-tags-for-documentation-comments"></a>Empfohlene Tags für Dokumentationskommentare

Der MSVC-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und erstellt eine XDC-Datei für jede Kompiliereinheit und xdcmake.exe verarbeitet die XDC-Dateien in eine XML-Datei. Die Verarbeitung der XML-Datei zum Erstellen der Dokumentation muss an Ihrem Standort implementiert werden.

Tags werden auf der Basis von Konstrukten wie Typen und Typmember verarbeitet.

Tags müssen Typen oder Membern unmittelbar vorangestellt werden.

> [!NOTE]
>  Dokumentationskommentare können nicht für einen Namespace oder außerhalb der Definition für Eigenschaften und Ereignisse angewendet werden. Dokumentationskommentare müssen auf die Klassendeklarationen angewendet werden.

Der Compiler verarbeitet alle Tags, die gültige XML sind. Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit:

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<code>](code-visual-cpp.md)|[\<example>](example-visual-cpp.md)|
|[\<exception>](exception-visual-cpp.md)1|[\<include>](include-visual-cpp.md)1|[\<list>](list-visual-cpp.md)|
|[\<para>](para-visual-cpp.md)|[\<param>](param-visual-cpp.md)1|[\<paramref>](paramref-visual-cpp.md)1|
|[\<permission>](permission-visual-cpp.md)1|[\<remarks>](remarks-visual-cpp.md)|[\<returns>](returns-visual-cpp.md)|
|[\<see>](see-visual-cpp.md)1|[\<seealso>](seealso-visual-cpp.md)1|[\<summary>](summary-visual-cpp.md)|
|[\<value>](value-visual-cpp.md)|||

1. Der Compiler überprüft die Syntax.

In der aktuellen Version der MSVC-Compiler unterstützt keine `<paramref>`, ein Tag, das von anderen Visual Studio-Compiler unterstützt wird. Möglicherweise unterstützt Visual C++ `<paramref>` in einem zukünftigen Release.

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](xml-documentation-visual-cpp.md)