---
title: Schwerwiegender Fehler C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: 2b7f6fd878f0d0ba6cde19a3a316a01c390e954a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228563"
---
# <a name="fatal-error-c1382"></a>Schwerwiegender Fehler C1382

die PCH-Datei 'Datei' wurde neu erstellt wurde, da "Obj" generiert wurde. Erstellen Sie dieses Objekt neu.

Bei Verwendung ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md), der Compiler hat eine PCH-Datei, die neuer als eine CIL-OBJ-Datei, die auf diese Seite verweist. Die Informationen in der CIL-OBJ-Datei ist nicht aktuell. Erstellen Sie das Objekt neu.

C1382 kann auch auftreten, wenn Sie mit der Kompilierung **"/ Yc"**, aber auch mehrere Codedateien an den Compiler übergeben.  Um zu beheben, verwenden Sie keine **"/ Yc"** bei mehreren Quellcodedateien für den Compiler übergeben.  Weitere Informationen finden Sie unter ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md).