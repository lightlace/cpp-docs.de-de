---
title: "#import-Attribute (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import-Direktive, Attribute"
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# #import-Attribute (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enthält Links zu Attributen, die mit der \#import\-Direktive verwendet werden.  
  
 **Microsoft\-spezifisch**  
  
 Die folgenden Attribute stehen für die \#import\-Direktive zur Verfügung.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[auto\_rename](../preprocessor/auto-rename.md)|Benennt für C\+\+ reservierte Wörter um, indem dem Variablennamen zwei Unterstriche \(\_\_\) angefügt werden, um potenzielle Namenskonflikte zu vermeiden.|  
|[auto\_search](../preprocessor/auto-search.md)|Gibt an, dass, wenn auf eine Typbibliothek mit \#import verwiesen wird und diese selbst auf eine andere Typbibliothek verweist, der Compiler einen impliziten \#import für die andere Typbibliothek ausführen kann.|  
|[embedded\_idl](../preprocessor/embedded-idl.md)|Gibt an, dass die Typbibliothek in die TLH\-Datei geschrieben wird und der vom Attribut generierte Code beibehalten wird.|  
|[exclude](../preprocessor/exclude-hash-import.md)|Schließt Elemente aus den Headerdateien der Typbibliothek aus, die generiert werden.|  
|[high\_method\_prefix](../preprocessor/high-method-prefix.md)|Gibt an, welches Präfix beim Benennen von Eigenschaften und Methoden der oberen Ebene verwendet werden soll.|  
|[high\_property\_prefixes](../preprocessor/high-property-prefixes.md)|Gibt alternative Präfixe für drei Eigenschaftenmethoden an.|  
|[implementation\_only](../preprocessor/implementation-only.md)|Unterdrückt die Generierung der TLH\-Headerdatei \(die primäre Headerdatei\).|  
|[include\(\)](../preprocessor/include-parens.md)|Deaktiviert den automatische Ausschluss.|  
|[inject\_statement](../preprocessor/inject-statement.md)|Fügt das Argument als Quelltext in den Header der Typbibliothek ein.|  
|[named\_guids](../preprocessor/named-guids.md)|Weist den Compiler an, die GUID\-Variablen im alten Stil zu definieren und zu initialisieren, und zwar in der Form **LIBID\_MyLib**, **CLSID\_MyCoClass**, **IID\_MyInterface** und **DIID\_MyDispInterface**.|  
|[no\_auto\_exclude](../preprocessor/no-auto-exclude.md)|Deaktiviert den automatische Ausschluss.|  
|[no\_dual\_interfaces](../preprocessor/no-dual-interfaces.md)|Ändert die Art, mit der der Compiler Wrapperfunktionen für Methoden der dualen Schnittstelle generiert.|  
|[no\_implementation](../preprocessor/no-implementation.md)|Unterdrückt die Generierung des TLI\-Headers, der die Implementierungen der Wrappermemberfunktionen enthält.|  
|[no\_namespace](../preprocessor/no-namespace.md)|Gibt an, dass der Name des Namespaces nicht vom Compiler generiert wird.|  
|[no\_registry](../preprocessor/no-registry.md)|Weist den Compiler an, in der Registrierung nicht nach Typbibliotheken zu suchen.|  
|[no\_search\_namespace](../preprocessor/no-search-namespace.md)|Hat dieselbe Funktionalität wie das [no\_namespace](../preprocessor/no-namespace.md)\-Attribut, wird jedoch in Typbibliotheken verwendet, damit Sie die \#import\-Direktive mit dem [auto\_search](../preprocessor/auto-search.md)\-Attribut verwenden.|  
|[no\_smart\_pointers](../preprocessor/no-smart-pointers.md)|Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.|  
|[raw\_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Weist den Compiler an, Wrapperfunktionen auf niedriger Ebene für Disp\-Schnittstellenmethoden und \-eigenschaften zu generieren, die **IDispatch::Invoke** aufrufen und den `HRESULT`\-Fehlercode zurückgeben.|  
|[raw\_interfaces\_only](../preprocessor/raw-interfaces-only.md)|Unterdrückt die Generierung von Fehlerbehandlungs\-Wrapperfunktionen und [Eigenschaft](../cpp/property-cpp.md)\-Deklarationen, die diese Wrapperfunktionen verwenden.|  
|[raw\_method\_prefix](../preprocessor/raw-method-prefix.md)|Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.|  
|[raw\_native\_types](../preprocessor/raw-native-types.md)|Deaktiviert die Verwendung COM\-Unterstützungsklassen in den Wrapperfunktionen auf hoher Ebene und erzwingt stattdessen die Verwendung von Datentypen auf niedriger Ebene.|  
|[raw\_property\_prefixes](../preprocessor/raw-property-prefixes.md)|Gibt alternative Präfixe für drei Eigenschaftenmethoden an.|  
|[Umbenennen](../preprocessor/rename-hash-import.md)|Umgeht Probleme mit Namenskonflikten.|  
|[rename\_namespace](../preprocessor/rename-namespace.md)|Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.|  
|[rename\_search\_namespace](../preprocessor/rename-search-namespace.md)|Hat dieselbe Funktionalität wie das [rename\_namespace](../preprocessor/rename-namespace.md)\-Attribut, wird jedoch in Typbibliotheken verwendet, damit Sie die \#import\-Direktive mit dem [auto\_search](../preprocessor/auto-search.md)\-Attribut verwenden.|  
|[tlbid](../preprocessor/tlbid.md)|Ermöglicht das Laden anderer Bibliotheken als der primären Typbibliothek.|  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)