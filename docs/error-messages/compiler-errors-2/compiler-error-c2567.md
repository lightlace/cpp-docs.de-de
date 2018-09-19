---
title: Compilerfehler C2567 | Microsoft-Dokumentation
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
ms.openlocfilehash: cb09aacc1b81e9f0e0c9c96a496eccc89a061f37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104234"
---
# <a name="compiler-error-c2567"></a>Compilerfehler C2567

kann nicht zum Öffnen der Metadaten in 'Datei', Datei möglicherweise verschoben oder gelöscht wurden

Eine Datei mit Metadaten, die in der Quelle verwiesen wurde (mit `#using`) wurde nicht gefunden im gleichen Verzeichnis des Compiler-Back-End-Prozesses durch den Compiler-Front-End-Prozess vorlag. Finden Sie unter [#using-Direktive](../../preprocessor/hash-using-directive-cpp.md) für Weitere Informationen.

C2567 verursacht werden, wenn Sie mit der Kompilierung **/c** klicken Sie auf einem Computer, und versuchen Sie dann auf einen Link-zeitcodegenerierung auf einem anderen Computer. Weitere Informationen finden Sie unter [/LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md)).

Es möglicherweise, dass es sich bei Ihrem Computer kein weiterer Speicher haben.

Um diesen Fehler zu beheben, stellen Sie sicher, dass die Metadatendatei im gleichen Verzeichnis für alle Phasen des Buildprozesses ist.