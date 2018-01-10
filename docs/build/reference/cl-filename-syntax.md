---
title: "Syntax für Dateinamen bei CL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fc9ce614cb67bef1904e8dc464402f362b0cbde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cl-filename-syntax"></a>Syntax für Dateinamen bei CL
CL akzeptiert Dateinamen, die FAT-, HPFS- oder NTFS-Namenskonventionen entsprechen. Jeder Dateiname kann einen vollständigen oder teilweisen Pfad umfassen. Ein vollständiger Pfad enthält einen Laufwerksnamen sowie einen oder mehrere Verzeichnisnamen. CL akzeptiert Dateinamen getrennt durch Backslash (\\) oder Schrägstriche (/). Dateinamen, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden. Ein partieller Pfad lässt den Servernamen weg, den CL als das aktuelle Laufwerk ansieht. Wenn Sie einen Pfad angeben, nimmt CL an, dass die Datei im aktuellen Verzeichnis ist.  
  
 Die Dateierweiterung bestimmt, wie Dateien verarbeitet werden. C- und C++-Dateien, die die Erweiterung .c, .cxx oder .cpp haben, werden kompiliert. Andere Dateien, einschließlich .obj-Dateien, Bibliotheken (.lib) und Moduldefinitionsdateien (.def)-Dateien, werden unverarbeitet an den Linker übergeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)