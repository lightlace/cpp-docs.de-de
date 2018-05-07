---
title: Compilerfehler C2567 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05f89362f36a6ba576e9829153f0d8931c4975c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2567"></a>Compilerfehler C2567
Öffnen Sie die Metadaten in "File" kann nicht ausgeführt werden, Datei möglicherweise verschoben oder gelöscht wurden  
  
 Eine Datei mit Metadaten, die in der Quelle verwiesen wurde (mit `#using`) wurde nicht gefunden im gleichen Verzeichnis durch den Compiler-Back-End-Prozess durch den Compiler-front-End-Prozess vorlag. Finden Sie unter [#using-Direktive](../../preprocessor/hash-using-directive-cpp.md) für Weitere Informationen.  
  
 C2567 verursacht werden, wenn beim Kompilieren mit **/c** auf einem Computer, und versuchen Sie, einen Link-zeitcodegenerierung auf einem anderen Computer. Weitere Informationen finden Sie unter [/LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md)).  
  
 Es kann auch bedeuten, dass es sich bei Ihrem Computer kein weiterer Speicher wurde.  
  
 Um diesen Fehler zu beheben, stellen Sie sicher, dass die Metadatendatei im gleichen Verzeichnis für alle Phasen des Buildprozesses wird.