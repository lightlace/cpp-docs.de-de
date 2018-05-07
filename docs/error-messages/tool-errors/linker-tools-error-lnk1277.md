---
title: Linkertoolfehler Lnk1277 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec8f00793fcda748c60d9d8ea775611e3d025cd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1277"></a>Linkertoolfehler LNK1277
Objektdatensatz wurde in Pgd (Dateiname) nicht gefunden.  
  
 Bei Verwendung [PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), der Pfad einer LIB, "def" oder obj-Eingabedateien wurde der Pfad auf dem stellten während/LTCG: PGINSTRUMENT unterscheiden. Dies kann durch eine Änderung in der LIB-Umgebungsvariablen nach/LTCG: PGINSTRUMENT erläutert werden. Der vollständige Pfad zu den Eingabedateien ist in die PGD-Datei gespeichert.  
  
 / LTCG: PGOPTIMIZE erfordert, dass die Eingaben für die/LTCG: PGINSTRUMENT-Phase identisch sein.  
  
 Um diese Warnung zu beheben, führen Sie eine der folgenden:  
  
-   Ausführen von/LTCG: PGINSTRUMENT, wiederholen alle Testläufe und führen Sie die/LTCG: PGOPTIMIZE.  
  
-   Ändern Sie die LIB-Umgebungsvariable, war der bei der Ausführung von/LTCG: PGINSTRUMENT.  
  
 Es wird nicht empfohlen, dass Sie mithilfe von/LTCG: PGUPDATE LNK1277 arbeiten.