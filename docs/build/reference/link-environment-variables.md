---
title: LINK-Umgebungsvariablen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67b36afce92140c4f205f8e5a4a46dfc7ac2d300
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="link-environment-variables"></a>LINK-Umgebungsvariablen

Das LINK-Tool verwendet die folgenden Umgebungsvariablen:  
  
-   LINK und \_LINK\_, falls definiert. Das LINK-Tool stellt voran, die Optionen und Argumente, die in der Umgebungsvariablen LINK definiert und fügt die Optionen und Argumente definiert, der \_LINK\_ -Umgebungsvariable für die Befehlszeilenargumente vor der Verarbeitung.  
  
-   LIB, falls definiert. Die LINK-Tools verwenden den LIB-Pfad an, bei der Suche nach einem Objekt, Bibliothek oder anderen Datei angegeben, in der Befehlszeile oder durch die [/BASE](../../build/reference/base-base-address.md) Option. Der LIB-Pfad wird auch verwendet, um nach einer in einem Objekt genannten PDB-Datei zu suchen. Die LIB-Variable kann mehrere durch Semikolons getrennte Pfadangaben enthalten. Ein Pfad muss auf das Unterverzeichnis \lib der Visual C++-Installation zeigen.  
  
-   PATH, wenn das Tool CVTRES ausführen muss und die Datei nicht im selben Verzeichnis wie LINK findet. (LINK benötigt CVTRES, um eine RES-Datei zu verknüpfen.) PATH muss auf das Unterverzeichnis \bin der Visual C++-Installation zeigen.  
  
-   TMP zum Angeben eines Verzeichnisses beim Verknüpfen von OMF oder RES-Dateien  
  
## <a name="see-also"></a>Siehe auch  

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
[Optionen des Linkers](../../build/reference/linker-options.md)   
[Erstellen von C/C++-Code in der Befehlszeile](../../build/building-on-the-command-line.md)  
[Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
