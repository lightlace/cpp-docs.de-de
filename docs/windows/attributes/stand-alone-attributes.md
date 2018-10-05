---
title: Eigenständige Attribute (C++-COM-) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b46b5c3b4750957c548becfcc5143f5eed858f71
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791261"
---
# <a name="stand-alone-attributes"></a>Eigenständige Attribute
Ein eigenständiges Attribut kann nicht ausgeführt werden, auf ein C++-Schlüsselwort jedoch eher wie eine einzige Zeile Code. Eigenständige Attribut-Anweisungen erfordern ein Semikolon am Ende der Zeile.
  
|Attribut|Beschreibung|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten Headerdatei an.|
|[Benutzerdefinierte](custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|
|[db_command](db-command.md)|Erstellt einen OLE DB-Befehl.|
|[emitidl](emitidl.md)|Bestimmt, ob alle nachfolgenden IDL-Attribute verarbeitet und in der generierten IDL-Datei platziert werden.|
|[idl_module](idl-module.md)|Gibt einen Einstiegspunkt in einer DLL an.|
|[idl_quote](idl-quote.md)|Ermöglicht es Ihnen, die IDL-Konstrukte verwenden, die in der aktuellen Version von Visual C++ nicht unterstützt werden, und lassen sie die an der generierten IDL-Datei übergeben.|
|[import](import.md)|Gibt eine andere IDL, ODL oder h-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL-Datei verweisen möchten.|
|[importidl](importidl.md)|Fügt die angegebene IDL-Datei in der generierten IDL-Datei|
|[importlib](importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|
|[include](include-cpp.md)|Gibt einen oder mehrere Headerdateien, die in der generierten IDL-Datei eingeschlossen werden.|
|[includelib](includelib-cpp.md)|Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.|
|[library_block](library-block.md)|Fügt ein Konstrukt in bibliotheksblock der IDL-Datei an.|
|[Modul](module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|
|[no_injected_text](no-injected-text.md)|Verhindert, dass den Compiler Einfügen von Code durch Verwendung des Attributs.|
|[pragma](pragma.md)|Gibt die angegebene Zeichenfolge verwendet werden, ohne die Anführungszeichen in der generierten IDL-Datei aus.|
  
## <a name="see-also"></a>Siehe auch

[Attribute nach Verwendung](attributes-by-usage.md)