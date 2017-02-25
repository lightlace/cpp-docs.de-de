---
title: "Interface Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], reference topics"
  - "interface attributes"
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interface Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Attribute gelten für [Schnittstelle \(oder \_\_interface\)](../cpp/interface.md) C\+\+ das Schlüsselwort.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[async\_uuid](../windows/async-uuid.md)|Gibt das UUID an, das den MIDL\-Compiler, weist die synchronen und asynchronen Versionen einer COM\-Schnittstelle zu definieren.|  
|[custom](../windows/custom-cpp.md)|Ermöglicht Ihnen definierten Attribute besitzen.|  
|[dispinterface](../windows/dispinterface.md)|Platziert eine Schnittstelle in der IDL\-Datei als Dispatchschnittstelle.|  
|[dual](../windows/dual.md)|Platziert eine Schnittstelle in der IDL\-Datei als duale Schnittstelle.|  
|["export"](../windows/export.md)|Bewirkt, dass eine Datenstruktur, in die IDL\-Datei abgelegt werden.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext\-ID an, die der Benutzer Informationen über dieses Element in der Hilfedatei können.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek fest.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, durch die das zugehörige Element beschrieben wird.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in einem .hlp oder CHM\-Datei an.|  
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL an, der verwendet wird, um Zeichenfolgen Dokumente Lokalisierung \(Discovery\) auszuführen.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, in einem benutzerorientierten Browser jedoch nicht angezeigt werden sollte.|  
|[library\_block](../windows/library-block.md)|Platziert ein Konstrukt innerhalb des Library\-Blocks der .idl\-Datei.|  
|[local](../windows/local-cpp.md)|Ermöglicht es Ihnen, den MIDL\-Compiler als Header Steuerelement\-Generator verwenden, wenn Sie im Header des Schnittstellen verwendet werden.  Wenn in einer einzelnen Funktion verwendet werden, legt eine lokale Prozedur fest, für die keine Stubs generiert werden.|  
|[nicht erweiterbar](../windows/nonextensible.md)|Gibt an, dass die `IDispatch` nur die Implementierung der Eigenschaften und Methoden enthält, die in der Beschreibung der aufgelisteten Schnittstellen und nicht mit zusätzlichen Member zur Laufzeit erweitert werden kann.  Dieses Attribut ist nur gültig für eine duale Schnittstelle.|  
|[odl](../windows/odl.md)|Identifiziert eine Schnittstelle während eine Schnittstelle der Objektbeschreibungssprache \(ODL\).|  
|[object](../windows/object-cpp.md)|Identifiziert eine benutzerdefinierte Schnittstelle.|  
|[oleautomation](../windows/oleautomation.md)|Gibt an, dass eine Schnittstelle mit Automatisierung kompatibel ist.|  
|[pointer\_default](../windows/pointer-default.md)|Gibt die Standardzeiger Attribut für alle Zeiger für Zeiger mit Ausnahme der obersten Ebene angezeigt, die in den Parameterlisten enthalten sein.|  
|[PTR](../windows/ptr.md)|Legt einen Zeiger als vollständiger Zeiger fest.|  
|[restricted](../windows/restricted.md)|Legt fest, welche Member der Bibliothek nicht willkürlich aufgerufen werden können.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Stellt die eindeutige ID für die Bibliothek bereit|  
  
 Sie müssen diese Regeln zum Definieren einer Schnittstelle beachten:  
  
-   Standardaufrufkonvention ist [\_\_stdcall](../cpp/stdcall.md).  
  
-   Ein GUID\-Element wird angegeben, wenn Sie kein angeben.  
  
-   Keine überladene Methoden sind nicht zulässig.  
  
 Wenn nicht angegeben [uuid](../windows/uuid-cpp-attributes.md) des Attributs und das Verwenden desselben Namens der Schnittstellen im jeweils anderen Attribut festgelegt wurde, wird das gleiche GUID generiert.  
  
## Siehe auch  
 [Attributes by Usage](../windows/attributes-by-usage.md)