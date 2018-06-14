---
title: Empfohlene Tags für Dokumentationskommentare (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b25ad029a59c4b23bcab093b3742f16f7ca9175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328619"
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Empfohlene Tags für Dokumentationskommentare (Visual C++)
Der Visual C++-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und erstellt für jede Kompiliereinheit eine XDC-Datei, und die „xdcmake.exe“ verarbeitet die XDC-Dateien zu einer XML-Datei. Die Verarbeitung der XML-Datei zum Erstellen der Dokumentation muss an Ihrem Standort implementiert werden.  
  
 Tags werden auf der Basis von Konstrukten wie Typen und Typmember verarbeitet.  
  
 Tags müssen Typen oder Membern unmittelbar vorangestellt werden.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht für einen Namespace oder außerhalb der Definition für Eigenschaften und Ereignisse angewendet werden. Dokumentationskommentare müssen auf die Klassendeklarationen angewendet werden.  
  
 Der Compiler verarbeitet alle Tags, die gültige XML sind. Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit:  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<exception>](../ide/exception-visual-cpp.md)1|[\<include>](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<param>](../ide/param-visual-cpp.md)1|[\<paramref>](../ide/paramref-visual-cpp.md)1|  
|[\<permission>](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<see>](../ide/see-visual-cpp.md)1|[\<seealso>](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. Der Compiler überprüft die Syntax.  
  
 Im aktuellen Release unterstützt der Visual C++-Compiler `<paramref>` nicht. Dies ist ein Tag, das von anderen Visual Studio-Compilern unterstützt wird. Möglicherweise unterstützt Visual C++ `<paramref>` in einem zukünftigen Release.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)