---
title: Linkertoolfehler Lnk1277 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3606207afc197dc26ac0540d476b74f52c0dc0a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1277"></a>Linkertoolfehler LNK1277
Objektdatensatz wurde in Pgd (Dateiname) nicht gefunden.  
  
 Bei Verwendung [PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), der Pfad einer LIB, "def" oder obj-Eingabedateien wurde der Pfad auf dem stellten während/LTCG: PGINSTRUMENT unterscheiden. Dies kann durch eine Änderung in der LIB-Umgebungsvariablen nach/LTCG: PGINSTRUMENT erläutert werden. Der vollständige Pfad zu den Eingabedateien ist in die PGD-Datei gespeichert.  
  
 / LTCG: PGOPTIMIZE erfordert, dass die Eingaben für die/LTCG: PGINSTRUMENT-Phase identisch sein.  
  
 Um diese Warnung zu beheben, führen Sie eine der folgenden:  
  
-   Ausführen von/LTCG: PGINSTRUMENT, wiederholen alle Testläufe und führen Sie die/LTCG: PGOPTIMIZE.  
  
-   Ändern Sie die LIB-Umgebungsvariable, war der bei der Ausführung von/LTCG: PGINSTRUMENT.  
  
 Es wird nicht empfohlen, dass Sie mithilfe von/LTCG: PGUPDATE LNK1277 arbeiten.