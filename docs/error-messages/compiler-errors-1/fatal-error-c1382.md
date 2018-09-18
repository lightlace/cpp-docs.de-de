---
title: Schwerwiegender Fehler C1382 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a5a6ce312c5ef886ef25e8de46e6d3376eded2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030644"
---
# <a name="fatal-error-c1382"></a>Schwerwiegender Fehler C1382

die PCH-Datei 'Datei' wurde neu erstellt wurde, da "Obj" generiert wurde. Erstellen Sie dieses Objekt neu.

Bei Verwendung ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md), der Compiler hat eine PCH-Datei, die neuer als eine CIL-OBJ-Datei, die auf diese Seite verweist. Die Informationen in der CIL-OBJ-Datei ist nicht aktuell. Erstellen Sie das Objekt neu.

C1382 kann auch auftreten, wenn Sie mit der Kompilierung **"/ Yc"**, aber auch mehrere Codedateien an den Compiler übergeben.  Um zu beheben, verwenden Sie keine **"/ Yc"** bei mehreren Quellcodedateien für den Compiler übergeben.  Weitere Informationen finden Sie unter ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md).