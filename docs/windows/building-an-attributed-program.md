---
title: Erstellen eines attributierten Programms | Microsoft-Dokumentation
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
ms.openlocfilehash: 7909884a355ccad5e1bf9d18a38dd3e4690296ee
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42587506"
---
# <a name="building-an-attributed-program"></a>Erstellen eines attributierten Programms

Nachdem Sie Visual C++-Attribute in Ihren Quellcode einfügen, sollten Sie die Visual C++-Compiler, um eine Bibliothek und IDL-Datei für Sie zu generieren. Die folgenden Linkeroptionen können Sie TLB-Datei und IDL-Dateien:

- [/ IDLOUT](../build/reference/idlout-name-midl-output-files.md)

- [/ IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/ MIDL](../build/reference/midl-specify-midl-command-line-options.md)

- [/ TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)

Einige Projekte enthalten mehrere unabhängige IDL-Dateien. Diese werden verwendet, um zwei oder mehr .tlb-Dateien erstellen und binden sie optional in den Ressourcenblock. Dieses Szenario ist nicht aktuell in Visual C++ unterstützt.

Darüber hinaus gibt der Visual C++-Linker alle IDL-Attribut-Informationen in eine einzelne MIDL-Datei. Es werden keine Möglichkeit, zwei Typbibliotheken aus einem einzelnen Projekt zu generieren.

## <a name="see-also"></a>Siehe auch

[Konzepte](../windows/attributed-programming-concepts.md)