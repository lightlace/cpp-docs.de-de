---
title: "Building an Attributed Program | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tlb files"
  - "MIDL"
  - "MIDL, linker output"
  - "IDL files"
  - "tlb files, building attributed programs"
  - ".tlb files, building attributed programs"
  - "IDL files, building"
  - "attributes [C++], building type libraries and .idl files"
  - ".tlb files"
  - ".idl files, building"
  - "type libraries, linker options for building"
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Building an Attributed Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie den Quellcode in Visual C\+\+\-Attribute einfügen, sollten Sie den Visual C\+\+\-Compiler eine Typbibliothek und IDL\-Datei für Sie vorlegen.  Folgende Linkeroptionen unterstützen Sie dabei, .tlb\- und IDL\-Dateien zu erstellen:  
  
-   [\/IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [\/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [\/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [\/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 Einige Projekte enthalten unabhängige .idl für mehrere Dateien.  Diese werden verwendet, um zwei oder mehr TLB\-Dateien erstellen und sie in den Ressourcen optional Datenbindungsausdrücken binden.  Dieses Szenario wird nicht nur in Visual C\+\+ unterstützt.  
  
 Darüber hinaus gibt der Visual C\+\+\-Linker alle IDL\-verknüpfte Attributinformationen für eine einzelne MIDL\-Datei aus.  Es gibt keine Möglichkeit, zwei Typbibliotheken aus einem einzelnen Projekt zu generieren.  
  
## Siehe auch  
 [Concepts](../windows/attributed-programming-concepts.md)