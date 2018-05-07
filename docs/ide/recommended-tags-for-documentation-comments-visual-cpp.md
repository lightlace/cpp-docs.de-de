---
title: Empfohlene Tags für Dokumentationskommentare (Visual C++) | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Empfohlene Tags für Dokumentationskommentare (Visual C++)
Visual C++-Compiler verarbeitet Dokumentationskommentare im Code und erstellt eine XDC-Datei für jede Kompiliereinheit und xdcmake.exe verarbeitet der XDC-Dateien in eine XML-Datei. Verarbeiten der XML-Datei zum Erstellen von Dokumentation ist ein Detail, die an Ihrem Standort implementiert werden muss.  
  
 Tags werden verarbeitet, auf Konstrukte wie Typen und Typmember.  
  
 Tags müssen Typen oder Member unmittelbar vorangestellt sein.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht mit einem Namespace oder auf Out abweichenden Definition für Eigenschaften und Ereignisse angewendet werden; Dokumentationskommentare müssen auf die Klassendeklarationen.  
  
 Der Compiler verarbeitet alle Tags, die gültige XML sind. Die folgenden Tags stellen häufig verwendete Funktionalität in der Dokumentation für die Benutzer bereit:  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<Ausnahme >](../ide/exception-visual-cpp.md)1|[\<umfassen >](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<Param >](../ide/param-visual-cpp.md)1|[\<Paramref >](../ide/paramref-visual-cpp.md)1|  
|[\<Berechtigung >](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<finden Sie unter >](../ide/see-visual-cpp.md)1|[\<Seealso >](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. Compilerfehler überprüft die Syntax.  
  
 In der aktuellen Version der Visual C++-Compiler unterstützt keine `<paramref>`, ein Tag, das von anderen Visual Studio-Compiler unterstützt wird. Visual C++ unterstützt möglicherweise `<paramref>` in einer zukünftigen Version.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)