---
title: Eigenständige Attribute | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6562a1de8baa9a5805f044233b97bf8dd8840638
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613757"
---
# <a name="stand-alone-attributes"></a>Eigenständige Attribute
Ein eigenständiges Attribut kann nicht ausgeführt werden, auf ein C++-Schlüsselwort jedoch eher wie eine einzige Zeile Code. Eigenständige Attribut-Anweisungen erfordern ein Semikolon am Ende der Zeile.
  
|Attribut|Beschreibung|
|---------------|-----------------|
|[cpp_quote](../windows/cpp-quote.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten Headerdatei an.|
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|
|[emitidl](../windows/emitidl.md)|Bestimmt, ob alle nachfolgenden IDL-Attribute verarbeitet und in der generierten IDL-Datei platziert werden.|
|[idl_module](../windows/idl-module.md)|Gibt einen Einstiegspunkt in einer DLL an.|
|[idl_quote](../windows/idl-quote.md)|Ermöglicht es Ihnen, die IDL-Konstrukte verwenden, die in der aktuellen Version von Visual C++ nicht unterstützt werden, und lassen sie die an der generierten IDL-Datei übergeben.|
|[import](../windows/import.md)|Gibt eine andere IDL, ODL oder h-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL-Datei verweisen möchten.|
|[importidl](../windows/importidl.md)|Fügt die angegebene IDL-Datei in der generierten IDL-Datei|
|[importlib](../windows/importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|
|[include](../windows/include-cpp.md)|Gibt einen oder mehrere Headerdateien, die in der generierten IDL-Datei eingeschlossen werden.|
|[includelib](../windows/includelib-cpp.md)|Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.|
|[library_block](../windows/library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[Modul](../windows/module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|
|[no_injected_text](../windows/no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|
|[pragma](../windows/pragma.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten IDL-Datei aus.|
  
## <a name="see-also"></a>Siehe auch
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)