---
title: Erstellen eines attributierten Programms | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d87f95b456e3f99598f48e6ffa8ad29806aa168
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862276"
---
# <a name="building-an-attributed-program"></a>Erstellen eines attributierten Programms
Nachdem Sie Visual C++-Attribute in Ihren Quellcode einfügen, sollten Sie die Visual C++-Compiler, mit der eine Bibliothek und IDL-Datei für Sie erstellt. Die folgenden Linkeroptionen können Sie TLB- und IDL-Dateien erstellen:  
  
-   [/ IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [/ IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [/ MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [/ TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 Einige Projekte enthalten mehrere unabhängige IDL-Dateien. Diese werden verwendet, um zwei oder mehr .tlb-Dateien erzeugen und binden sie optional in den Ressourcenblock. Dieses Szenario wird derzeit nicht in Visual C++ unterstützt.  
  
 Darüber hinaus wird der Visual C++-Linker alle IDL-bezogene Attributinformationen in eine einzelne MIDL-Datei ausgeben. Es werden keine Möglichkeit, zwei Typbibliotheken aus einem einzelnen Projekt generieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../windows/attributed-programming-concepts.md)