---
title: Eigenständige Attribute | Microsoft Docs
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
ms.openlocfilehash: 59846b1ca031cc02c85cb6ace23f96e8c5cc9f37
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890429"
---
# <a name="stand-alone-attributes"></a>Eigenständige Attribute
Ein eigenständiges Attribut kann nicht ausgeführt werden, auf ein C++-Schlüsselwort jedoch eher wie eine Codezeile ist. Eigenständiges Attribut-Anweisungen erfordern ein Semikolon am Ende der Zeile.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[cpp_quote](../windows/cpp-quote.md)|Gibt die angegebene Zeichenfolge, ohne die Anführungszeichen in der Headerdatei.|  
|[Benutzerdefinierte](../windows/custom-cpp.md)|Sie können Ihr eigenes Attribut definieren.|  
|[db_command](../windows/db-command.md)|Erstellt einen OLE DB-Befehl.|  
|[emitidl](../windows/emitidl.md)|Bestimmt, ob alle nachfolgenden IDL-Attribute verarbeitet und in der generierten IDL-Datei abgelegt werden.|  
|[idl_module](../windows/idl-module.md)|Gibt einen Einstiegspunkt in eine DLL-Datei an.|  
|[idl_quote](../windows/idl-quote.md)|Ermöglicht es Ihnen IDL-Konstrukte zu verwenden, die nicht in der aktuellen Version von Visual C++ unterstützt werden, und lassen sie die pass-through an der generierten IDL-Datei.|  
|[import](../windows/import.md)|Gibt eine andere IDL, ODL oder .h-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL-Datei verweisen möchten.|  
|[importidl](../windows/importidl.md)|Fügt die angegebenen IDL-Datei in der generierten IDL-Datei|  
|[importlib](../windows/importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|  
|[include](../windows/include-cpp.md)|Gibt einen oder mehrere Headerdateien, in der generierten IDL-Datei eingeschlossen werden sollen.|  
|[includelib](../windows/includelib-cpp.md)|Bewirkt, dass eine IDL oder .h-Datei, in der generierten IDL-Datei eingeschlossen werden sollen.|  
|[library_block](../windows/library-block.md)|Fügt ein Konstrukt in der IDL-Datei bibliotheksblock vor.|  
|[Modul](../windows/module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|  
|[no_injected_text](../windows/no-injected-text.md)|Verhindert, dass den Compiler Code aufgrund der Verwendung des Attributs injiziert.|  
|[pragma](../windows/pragma.md)|Gibt die angegebene Zeichenfolge, ohne die Anführungszeichen in der generierten IDL-Datei aus.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)