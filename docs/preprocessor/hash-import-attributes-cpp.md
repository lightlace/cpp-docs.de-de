---
title: '#<a name="import-attributes-c--microsoft-docs"></a>Importieren Sie die Attribute (C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fd11326e33ff783b3868215794f9803e97d41c55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="import-attributes-c"></a>#import-Attribute (C++)
Enthält Links zu Attributen, die mit der #import-Direktive verwendet werden.  
  
 **Microsoft-spezifisch**  
  
 Die folgenden Attribute stehen für die #import-Anweisung zur Verfügung.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[auto_rename](../preprocessor/auto-rename.md)|Benennt für C++ reservierte Wörter um, indem dem Variablennamen zwei Unterstriche (__) angefügt werden, um potenzielle Namenskonflikte zu vermeiden.|  
|[auto_search](../preprocessor/auto-search.md)|Gibt an, dass, wenn auf eine Typbibliothek mit #import verwiesen wird und diese selbst auf eine andere Typbibliothek verweist, der Compiler einen impliziten #import für die andere Typbibliothek ausführen kann.|  
|[embedded_idl](../preprocessor/embedded-idl.md)|Gibt an, dass die Typbibliothek in die TLH-Datei geschrieben wird und der vom Attribut generierte Code beibehalten wird.|  
|[Ausschließen](../preprocessor/exclude-hash-import.md)|Schließt Elemente aus den Headerdateien der Typbibliothek aus, die generiert werden.|  
|[high_method_prefix](../preprocessor/high-method-prefix.md)|Gibt an, welches Präfix beim Benennen von Eigenschaften und Methoden der oberen Ebene verwendet werden soll.|  
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|Gibt alternative Präfixe für drei Eigenschaftenmethoden an.|  
|[implementation_only](../preprocessor/implementation-only.md)|Unterdrückt die Generierung der TLH-Headerdatei (die primäre Headerdatei).|  
|[include()](../preprocessor/include-parens.md)|Deaktiviert den automatische Ausschluss.|  
|[inject_statement](../preprocessor/inject-statement.md)|Fügt das Argument als Quelltext in den Header der Typbibliothek ein.|  
|[named_guids](../preprocessor/named-guids.md)|Teilt dem Compiler mit definieren und initialisieren die GUID-Variablen im alten Stil des Formulars **LIBID_MyLib**, **CLSID_MyCoClass**, **IID_MyInterface**, und **DIID _MyDispInterface**.|  
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|Deaktiviert den automatische Ausschluss.|  
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|Ändert die Art, mit der der Compiler Wrapperfunktionen für Methoden der dualen Schnittstelle generiert.|  
|[no_implementation](../preprocessor/no-implementation.md)|Unterdrückt die Generierung des TLI-Headers, der die Implementierungen der Wrappermemberfunktionen enthält.|  
|[no_namespace](../preprocessor/no-namespace.md)|Gibt an, dass der Name des Namespaces nicht vom Compiler generiert wird.|  
|[no_registry](../preprocessor/no-registry.md)|Weist den Compiler an, in der Registrierung nicht nach Typbibliotheken zu suchen.|  
|[no_search_namespace](../preprocessor/no-search-namespace.md)|Hat die gleiche Funktion wie die [No_namespace](../preprocessor/no-namespace.md) -Attribut jedoch auf Typbibliotheken, mit denen Sie die #import-Direktive mit dient der [Auto_search](../preprocessor/auto-search.md) Attribut.|  
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.|  
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Weist den Compiler an, Wrapperfunktionen auf niedriger Ebene für Disp-Schnittstellenmethoden und Eigenschaften, die aufrufen generieren **IDispatch:: Invoke** und Zurückgeben der `HRESULT` Fehlercode.|  
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|Unterdrückt die Generierung des Fehlerbehandlungs-Wrapperfunktionen und [Eigenschaft](../cpp/property-cpp.md) Deklarationen, die diese Wrapperfunktionen verwenden.|  
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.|  
|[raw_native_types](../preprocessor/raw-native-types.md)|Deaktiviert die Verwendung COM-Unterstützungsklassen in den Wrapperfunktionen auf hoher Ebene und erzwingt stattdessen die Verwendung von Datentypen auf niedriger Ebene.|  
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|Gibt alternative Präfixe für drei Eigenschaftenmethoden an.|  
|[rename](../preprocessor/rename-hash-import.md)|Umgeht Probleme mit Namenskonflikten.|  
|[rename_namespace](../preprocessor/rename-namespace.md)|Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.|  
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|Hat die gleiche Funktion wie die [Rename_namespace](../preprocessor/rename-namespace.md) -Attribut jedoch auf Typbibliotheken, mit denen Sie die #import-Direktive mit dient der [Auto_search](../preprocessor/auto-search.md) Attribut.|  
|[tlbid](../preprocessor/tlbid.md)|Ermöglicht das Laden anderer Bibliotheken als der primären Typbibliothek.|  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)