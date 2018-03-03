---
title: "Empfohlene Tags für Dokumentationskommentare (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c1b0e762ec2167a988e8e18f3dce932214716c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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